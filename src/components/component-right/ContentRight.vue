<template>
    <div class="content">
            <AddEmployee/>
            <Fillter/>
            <Employee/>
        </div>
</template>

<script>
import AddEmployee from './AddEmployee.vue'
import Fillter from './Fillter.vue'
import Employee from './Employee.vue'
export default {
  name: 'ContentRight',
  components: {
    AddEmployee,
    Fillter,
    Employee
  }
}
</script>