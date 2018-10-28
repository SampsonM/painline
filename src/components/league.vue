<template>
  <div class="league">
    <div class="buttons"> 
      <button @click="toggleBoard">People</button>
      <button @click="toggleBoard">Rail</button>
    </div>

    <div v-if="board" class="people">
      <Chart label="people" :chartData="users"></Chart>
    </div>

    <div v-if="!board" class="rail">
      <Chart label="trains" :chartData="mock.trains"></Chart>
    </div>

  </div>
</template>
<script>
import mock from '../assets/mock.json'
import LeegTable from './table'
import Chart from './chart'
import db from './firebaseInit.js'

export default {
  name: 'league',
  data() {
    return {
      board: true,
      mock,
      users: []
    }
  },
  components: {
    LeegTable,
    Chart
  },
  methods: {
    toggleBoard() {
      this.board = !this.board;
    }
  },
  created() {
    db.collection('users').get()
      .then(snapshot => {
        snapshot.forEach((doc, i) => {
          const user = {
            'id': doc.id,
            'name': doc.data().name,
            'points': doc.data().points
          }

          this.users.push(user);
        })
      })
  }
}
</script>
<style lang="scss" scoped>
.buttons {
  display: flex;
  flex-direction: row;
  width: 600px;
}
.league {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100vw;
  background: rgb(56, 56, 56);
}

button {
  color: red;
  background: blue;
  width: 50px;
  height: 20px;
}

.people {
  width: 100%;
  height: 400px;
}
.rail {
  width: 100%;
  height: 400px;
}
</style>
