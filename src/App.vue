<template>
  <header>
    <nav id="nav">
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li class="has-child">
          <router-link to="#">Sequences</router-link>
          <div class="menu-submenu">
            <ul>
              <li><router-link to="#" @click="createSequence()">Create New Sequence</router-link></li>
              <li><router-link to="#">Sequence List</router-link></li>
            </ul>
          </div>
        </li>
        <li><router-link to="#">Support</router-link></li>
        <li><router-link to="#">Contact</router-link></li>
      </ul>
    </nav>
  </header>
  <router-view/>
</template>

<script>
export default {
  name: 'app',
  data: () => ({
    showSequenceMenu: false
  }),
  methods: {
    createSequence() {
      console.log('test');
    }
  }
}
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
header {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #EAEAEA;
}
#nav { 
	margin: 0 auto;
	padding: 0;
	box-sizing: border-box;
}
#nav * {
	margin: 0;
	padding: 0;
	box-sizing: border-box;
}
#nav ul {
	list-style: none;
	display: flex;
	align-items: center;
}
#nav ul li {
	margin: 0 5px; /* adjust */
	padding: 5px; /* adjust */
}
#nav ul li a {
	color: #222;
	text-decoration: none;
}
#nav ul li:last-child {
	margin-left: auto;
}
#nav ul li:hover {
	background: #FFF;
	color: #222;
}
#nav ul li.has-child > a:after {
	color: #444;
	content: ' ▾';
}
#nav ul li:hover .menu-submenu {
	display: flex;
}
#nav .menu-submenu {
	display: none;
	position: relative; /* added */
}
#nav .menu-submenu ul {
	position: absolute;
	top: 5px; /* modified; adjust; needs to match the padding of the ".menu ul li" */
	left: -5px; /* added; adjust; needs to match the padding of the ".menu ul li" (negative) */
	display: flex;
	flex-direction: column;
}
#nav .menu-submenu ul li {
	width: 100%; /* added */
	padding: 5px; /* adjust */
	white-space: nowrap; /* added */
	background: #EAEAEA;
	z-index: 10;
	text-align: left;
}
#nav .menu-submenu ul li:hover {
  background: #FFF;
	color: #222;
}
</style>