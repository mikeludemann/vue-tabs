<template lang="html">

	<section class="tabs">
		<div class="tab">
			<div class="tablinks">Cologne</div>
			<div class="tablinks">Berlin</div>
			<div class="tablinks">Munich</div>
		</div>
		<div class="tabcontents">
			<div class="tabcontent">
				<h3>Cologne</h3>
				<p>Cologne is a city of Germany.</p>
			</div>
			<div class="tabcontent">
				<h3>Berlin</h3>
				<p>Berlin is the capital of Germany.</p> 
			</div>
			<div class="tabcontent">
				<h3>Munich</h3>
				<p>Munich is a city of Germany.</p>
			</div>
		</div>
		<div class="tab--vertical">
			<div class="tablinks">Cologne</div>
			<div class="tablinks">Berlin</div>
			<div class="tablinks">Munich</div>
		</div>
		<div class="tabcontents">
			<div class="tabcontent">
				<h3>Cologne</h3>
				<p>Cologne is a city of Germany.</p>
			</div>
			<div class="tabcontent">
				<h3>Berlin</h3>
				<p>Berlin is the capital of Germany.</p> 
			</div>
			<div class="tabcontent">
				<h3>Munich</h3>
				<p>Munich is a city of Germany.</p>
			</div>
		</div>
	</section>

</template>

<script lang="js">

	export default {
		name: 'Tabs',
		props: [],
		mounted () {
			
				const tabsLink = document.querySelectorAll('.tablinks');
				const tabsContent = document.querySelectorAll('.tabcontent');

				const entries = function*(iterable) {

					let i = 0;

					for (let item of iterable) {

						yield [i++, item];

					}

				}

				const showBlock = index => {

					for (const [blockIndex, block] of entries(tabsContent)) {

						block.style.display = blockIndex === index ? 'block' : 'none';

					}

				}

				showBlock(0);

				for (const [tabIndex, tab] of entries(tabsLink)) {

					tab.addEventListener('click', ev => {

						ev.preventDefault(); 

						showBlock(tabIndex);

					});

				}
		},
		data () {
			return {

			}
		},
		methods: {

		},
		computed: {

		}
}


</script>

<style scoped lang="scss">
.tabs {

}

.tab {
	overflow: auto;
	border: 1px solid #ccc;
	background-color: #f1f1f1;
	white-space: nowrap;
	width: 100%;
}

.tab div {
	background-color: inherit;
	display: inline-block;
	border: none;
	outline: none;
	cursor: pointer;
	padding: 14px 16px;
	transition: 0.3s;
}

.tab div:hover {
	background-color: #ddd;
}

.tab--vertical {
	overflow: auto;
		float: left;
		border: 1px solid #ccc;
		background-color: #f1f1f1;
		width: 30%;
		height: auto;
}

.tab--vertical div {
	display: block;
	background-color: inherit;
	color: black;
	padding: 22px 16px;
	width: 100%;
	border: none;
	outline: none;
	text-align: left;
	cursor: pointer;
	transition: 0.3s;
	font-size: 17px;
}

.tab--vertical div:hover {
	background-color: #ddd;
}

.tabcontent {
	display: none;
	padding: 6px 12px;
	-webkit-animation: fadeEffect 1s;
	animation: fadeEffect 1s;
}

@-webkit-keyframes fadeEffect {
	from {
		opacity: 0;
	}
	to {
		opacity: 1;
	}
}

@keyframes fadeEffect {
	from {
		opacity: 0;
	}
	to {
		opacity: 1;
	}
}
</style>
