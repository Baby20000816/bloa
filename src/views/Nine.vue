<template>
	<div class="container">
		<div class="search">
			<video controls="" autoplay="" name="media">
				<source src="http://sc1.111ttt.cn:8282/2018/1/03m/13/396131232171.m4a" type="audio/mp4">
			</video>
		</div>
	</div>
</template>
<script>
	export default {
		data() {
			return {
				currentIndex: 0,
				timer: null
			}
		},
		created: function() {
			/* 动画自动播放 */
			this.$nextTick(() => {
				this.timer = setInterval(() => {
					this.autoPlay()
				}, 3000)
			})
		},
		methods: {
			change(index) {
				this.currentIndex = index
			},
			go() {
				this.timer = setInterval(() => {
					this.autoPlay()
				}, 2500)
			},
			stop() {
				clearInterval(this.timer)
				this.timer = null
			},
			autoPlay() {
				this.currentIndex++
				if (this.currentIndex > 11) {
					this.currentIndex = 0
				}
			}
		}
	}
</script>
<style>
	.container {
		width: 80%;
		margin: 0 auto;
		display: grid;
		grid-template-columns: 1fr 2fr 1fr;
		grid-template-rows: 260px auto 100px;
		grid-gap: 5px 10px;
	}

	#search {
		grid-column-start: 2;
		grid-column-end: 4;
	}
</style>
