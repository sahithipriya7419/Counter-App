<template>
    <main>
      <h1>Counter App</h1>
      <p>Dorothy weight: </p>
      <p class="count">{{count}}</p>
      <div class="buttonContainer">
		<template v-if="maxLim()">
			<button disabled>Increase</button>
		</template>
		<template v-else>
			<button @click="addCount()">Increase</button>
		</template>
		<template v-if="minLim()">
			<button disabled>Decrease</button>
		</template>
		<template v-else>
			<button @click="decCount()">Decrease</button>
		</template>
        <button @click="resetCount()">Reset</button>
      </div>
    </main>
</template>

<script>
export default {
  name:"App",
  data()
  {
    return{
      count:0
    }
  },
  methods:{
    addCount()
    {
      this.count++
    },
    decCount()
    {
      this.count--    
    },
    resetCount()
    {
      this.count=0
    },
	maxLim()
	{
		if(this.count>19)
		{
			return true
		}
		return false
	},
	minLim()
	{
		if(this.count<1)
		{
			return true
		}
		return false
	}
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;900&display=swap');

* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}
html {
	font-family: 'Roboto', sans-serif;
}
main {
	height: 100vh;
	width: 100%;
	background-image: url('./assets/bg.jpg');
	background-position: center;
	background-size: cover;
	display: flex;
	justify-content: flex-start;
	flex-direction: column;
	align-items: center;
}
h1 {
	font-size: 65px;
	margin: 20px 0;
	color: #cad5e2;
	text-transform: uppercase;
	font-weight: 900;
	text-align: center;
}
p {
	font-size: 28px;
	margin: 20px 0;
	color: #8d3daf;
}
.buttonContainer {
	display: flex;
	flex-direction: column;
}
button {
	padding: 15px 100px;
	margin: 20px 0;
	font-size: 18px;
	text-transform: uppercase;
	border-radius: 25px;
	outline: none;
	border: none;
	background-color: #8d3daf;
	color: #fff;
	transition: all 0.5s ease;
	cursor: pointer;
}
button:hover {
	/* transform: translateY(-5px); */
	transform: scale(1.04);
	color: #f8dc81;
}
.count {
	color: #f8dc81;
}
</style>