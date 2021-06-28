<template>
<div id="backg">
  <br>
  <h1>{{ msg }}</h1>
  <form action="">
  <label for="">First Name: </label><input type="text" v-model= "firstname" placeholder="Enter Here"><br>
  <label for="">Favorite Color: </label>
  <select v-model= "color">
    <option disabled hidden selected>Pick One</option>
    <option value="red">red</option>
    <option value="blue">blue</option>
    <option value="green">green</option>
    <option value="pink">pink</option>
    <option value="yellow">yellow</option>
  </select><br>
  <label for="">Do you like Pizza: </label>
  <input type="radio" v-model="pizza" name="pizza" value="true" @change="pizza=true"> <span id="primary-text-color">yes</span>
  <input type="radio" v-model="pizza" name="pizza" value="false" @change="pizza=false"> <span id="primary-text-color">no</span><br>
  <input v-if="pizza==true" type="text" v-model="toppings" placeholder="favorite toppings">
  <input v-if="pizza==false" type="textarea" v-model="dont" placeholder="Why don't you like pizza?">
  </form>      

<h2>Result</h2>  
<div id="result">
  <p id="secondary-text-color">Hey <!--[first name]--> <span id="secondary-text-color">{{ firstname }}</span>,<br>
  I also like <!-- [color] -->  <span :style="{color:color}">  {{ color }}</span>. I’m <span v-if="pizza==true" id="secondary-text-color">glad</span> <span v-else id="secondary-text-color">sad</span> that you <span v-if="pizza==true" id="secondary-text-color">do</span> <span v-else id="secondary-text-color">don't</span> like pizza,
<span v-if="pizza==true" id="secondary-text-color">because I like <i id="secondary-text-color"> "{{ toppings }}"</i>  too.<br></span>
<span v-if="pizza==false" id="secondary-text-color">it’s my favorite food. <br> You said: <i id="secondary-text-color">"{{ dont }}"</i>, but I don’t agree.<br> Pizza is awesome.</span></p>
</div>
<!-- <button @click="doSomething()">do something </button>  <br> <br> --> <br>
</div>  
</template>    

<script>
export default {
  data() {
    return {
    msg: "Bader Rutter Test!",
    pizza: null,
    color: null,
    firstname: null,
    toppings: null,
    dont: null,
    selected: true
    }
  }
}
</script>

<style scoped>
#primary-text-color, * {
  color: white;
}
#secondary-text-color {
  color: #5ed3eb;
}
#tertiary-text-color {
  color: bisque;
}
input {
  color: #2e3947;
}
option {
  color: #2e3947;
}
select {
  color: #2e3947;
}
a {
  color: slategray;
}
#backg {
  background-color: #2e3947;
  width: 75%;
}

</style>
