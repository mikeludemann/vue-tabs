<template>
	<div class="home">
		<img alt="Vue logo" src="../assets/logo.png">
		<HelloWorld msg="Welcome to Your Vue.js App"/>
		<Tabs/>
	</div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import Tabs from '@/components/tabs.vue';

export default {
	name: 'Home',
	components: {
		HelloWorld,
		Tabs
	}
}
</script>
