<template>
  <div id="app">
    <div class="playerOneTab">
      <h4>{{playerOneName}}</h4>
      <input type="text" v-model="playerOneName" />
      <br />
      <button class="btnOne" :disabled="winWalidate" @click="btnFun1">Click</button>
    </div>
    <div class="result">
      <h4>
        <span id="resOne">{{result1}}</span>
        <span>:</span>
        <span id="resTwo">{{result2}}</span>
      </h4>
      <h4>{{winScore}}</h4>
      <input type="number" placeholder="Win score" v-model="winScore" />
      <br />
      <button class="refresh" @click="refreshFun">refresh</button>
    </div>
    <div class="playerTwoTab">
      <h4>{{playerTwoName}}</h4>
      <input type="text" v-model="playerTwoName" />
      <br />
      <button class="btnTwo" :disabled="winWalidate" @click="btnFun2">Click</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      result1: 0,
      result2: 0,
      playerOneName: "Player 1",
      playerTwoName: "Player 2",
      winScore: 5,
      winWalidate: false
    };
  },
  methods: {
    btnFun1() {
      this.result1++;
      if (this.result1 == this.winScore) {
        alert(`${this.playerOneName} won`);
        this.winWalidate = true;
      }
    },
    btnFun2() {
      this.result2++;
      if (this.result2 == this.winScore) {
        alert(`${this.playerTwoName} won`);
        this.winWalidate = true;
      }
    },
    refreshFun() {
      location.reload();
    }
  }
};
</script>

<style>
#app {
  display: grid;
  grid-template-columns: auto auto auto;
  text-align: center;
  font-family: "MuseoModerno", cursive;
  margin-top: 10%;
}
.playerOneTab {
  text-align: center;
  display: inline-block;
}
.playerTwoTab {
  text-align: center;
  display: inline-block;
}
.btnOne {
  margin-top: 20px;
}
.btnTwo {
  margin-top: 20px;
}
</style>
