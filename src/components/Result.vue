<template>
	<div id='result'>
		<div id='title'>{{ results[resultIndex].title }}</div>
		<div id='description'>
			{{ results[resultIndex].description }}
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Result',
		props: ['results', 'correctAnswers'],
		computed: {
			resultIndex() {
				let resultIndex = 0;

				this.results.forEach((result, index) => {
					if (result.minimum <= this.correctAnswers && result.maximum >= this.correctAnswers) {
						resultIndex = index;
					};
				});

				return resultIndex;
			}
		}
	};
</script>