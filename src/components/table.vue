<template>
    <td class="table" :v-for="obj in mock">
      <tr>{{obj.name}}</tr>
      <tr>{{obj.points}}</tr>
    </td>
</template>
<script>
export default {
  name: 'time',
  data() {
    return {}
  },
  props: ['mock']
}
</script>
<style lang="scss" scoped>
.table {
  tr {
    background: #f00;
  }
}
</style>
