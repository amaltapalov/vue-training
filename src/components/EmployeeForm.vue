<template>
  <div id="employee-form">
    <form v-on:submit="handleSubmit">
      <label>Employee name</label>
      <input
        v-model="employee.name"
        ref="first"
        @focus="clearStatus"
        @keypress="clearStatus"
        :class="{'hase-error' : submitting && invalidName}"
        type="text"
      />
      <label>Employee Email</label>
      <input
        v-model="employee.email"
        type="text"
        :class="{'has-error' : submitting && invalidEmail}"
        @focus="clearStatus"
      />
      <p v-if="error && submitting" class="error-message">! Please fill out all fields</p>
      <p v-if="success" class="success-message">✅ Employee successfully added</p>
      <button>Add Employee</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "EmployeeForm",
  data() {
    return {
      submitting: false,
      error: false,
      success: false,
      employee: {
        name: "",
        email: ""
      }
    };
  },
  methods: {
    handleSubmit(event) {
      event.preventDefault();
      this.submitting = true;
      this.clearStatus();
      // Error handling
      if (this.invalidName || this.invalidEmail) {
        this.error = true;
        return;
      }

      // Success handling
      this.$emit("add:employee", this.employee);

      //  set focus on first field after success
      this.$refs.first.focus();
      this.employee = {
        name: "",
        email: ""
      };
      this.error = false;
      this.success = true;
      this.submitting = false;
    },
    clearStatus() {
      this.success = false;
      this.error = false;
    }
  },
  computed: {
    invalidName() {
      return this.employee.name === "";
    },
    invalidEmail() {
      return this.employee.email === "";
    }
  }
};
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}
form {
  margin-bottom: 2rem;
}

[class*="-message"] {
  font-weight: 500;
}

.error-message {
  color: #d33c40;
}

.success-message {
  color: #32a95d;
}
</style>
