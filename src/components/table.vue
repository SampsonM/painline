<template>
  <div>
    <td class="leaugetable" v-for="person in mock">
      <tr>{{person.name}}</tr>
      <tr>{{person.points}}</tr>
    </td>
  </div>
</template>
<script>
export default {
  name: 'leaugetable',
  data() {
    return {}
  },
  props: ['mock']
}
</script>
<style lang="scss" scoped>
.leaugetable {
  display: flex;
  flex-direction: row;
  border-top: 1px solid #fafafa;
  max-width: 600px;

  tr {
    background: #f00;
    width: 100%;
    padding: 5px;
    border-bottom: 1px solid #fafafa;
  }
}

@media only screen and (min-width: 600px) {
  .leaugetable {
    border: 1px solid #fafafa;
    margin: 0 auto;
  }
}
</style>
