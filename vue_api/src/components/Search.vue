<template>
    <header>
        <form v-on:submit.prevent="processUserInput">
          <img class="logo" src="../assets/logo.png" alt="logo">
          <span>
          <label>Search All Movies:</label>
            <input type="text" placeholder="Search" v-model="userInput">
            <button type="submit">Search</button>
            </span>
            <img class="logo" src="../assets/logo.png" alt="logo">
        </form>
    </header>
</template>

<script>
export default {
  name: "Search",
  data: function() {
    return {
      userInput: ""
    };
  },
  methods: {
    processUserInput: function() {
      this.$emit("process-user-input", this.userInput);
      this.userInput = "";
    }
  }
};
</script>

<style>

label {
  color: white;
}

input {
  margin: 15px;
  height: 10px;
  padding: 5px;
}

button {
  cursor: pointer;
  width: 75px;
  color: #35495e;
  font-weight: bold;
  background-color: #41b883;
  border-radius: 5px;
  padding: 3px;
}

form {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 10px;
  background-color:cadetblue;
  align-items: baseline;
}

.logo {
  text-align: center;
}

</style>
