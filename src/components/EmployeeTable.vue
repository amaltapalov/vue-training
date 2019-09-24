<template>
  <div id="employee-table">
    <EmployeeForm @add:employee="addEmployee" />
    <table>
      <thead>
        <tr>
          <th>Employee name</th>
          <th>Employee email</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td>{{ employee.name }}</td>
          <td>{{ employee.email }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import EmployeeForm from "./EmployeeForm";
export default {
  name: "EmployeeTable",
  components: {
    EmployeeForm
  },
  props: {
    employees: Array
  },
  methods: {
    addEmployee: function(employee) {
      const lastId =
        this.employees.length > 0
          ? this.employees[this.employees.length - 1].id
          : 0;
      const id = lastId + 1;
      const newEmployee = { ...employee, id };

      this.employees = [...this.employees, employee];
    }
  }
};
</script>

<style scoped></style>