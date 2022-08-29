<template>
	<div class="index-page">
		<!-- 搜索 -->
		<div class="index-search">
			<input type="search" placeholder="搜索" />
			<icon name="search" class="search" v-on:click="search()"></icon>
		</div>

		<!-- 模块 -->
		<div class="index-modules">
			<div v-for="item in modules" class="modules-item" v-bind:key="item.id" v-on:click="onClick(item)">
				<div class="item-img">
					<img :src="item.imageUrl" />
					<div class="item-name">{{item.name}}</div>
				</div>
				<div>
					<icon name="caret-right"></icon>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'IndexMain',
		data() {
			return {
				modules: [],
			}
		},
		created() {
			this.getModules();
		},
		methods: {
			onClick(item) {
				window.open(item.link);
			},
			getModules() {
				this.modules = [{
					"id": "1",
					"name": "博客",
					"link": "http://192.168.1.146:9076/",
					"imageUrl": "http://192.168.1.146:18009/images/twitter/FbAzksvaIAAiPEs.jfif",
				}, {
					"id": "0",
					"name": "极空间",
					"link": "http://192.168.1.146:5055/",
					"imageUrl": "http://192.168.1.146:18009/images/twitter/FbAzksvaIAAiPEs.jfif",
				}, {
					"id": "2",
					"name": "本地资源",
					"link": "http://192.168.1.146:18009/images/",
					"imageUrl": "http://192.168.1.146:18009/images/twitter/FbPy0YwVsAELvTf.jfif",
				}, {
					"id": "3",
					"name": "网盘挂载",
					"link": "http://192.168.1.146:49156/",
					"imageUrl": "http://192.168.1.146:18009/images/twitter/FbAzksvaIAAiPEs.jfif",
				}, ];
			}
		},
	}
</script>

<style lang="less">
	.index-page {

		.index-search {
			margin: 10px auto 20px auto;
			width: 40%;
			height: 3rem;
			border: 1px solid #797979;
			border-radius: 30px;
			display: flex;
			align-items: center;
			padding: 0 20px;

			input {
				flex: 8;
				margin: 1px 0 1px 1px;
				padding: 0 10px 0 19px;
				border: 0;
				max-height: none;
				outline: none;
				box-sizing: border-box;
				height: 3rem;
				font-size: 1rem;
				vertical-align: top;
				border-radius: 6px;
				background-color: transparent;
			}
		}

		.index-modules {
			margin: 0 1.25rem;
			display: flex;
			justify-content: center;
			align-items: center;
			flex-wrap: wrap;


			.modules-item:hover {
				box-shadow: 3px 3px 3px #888888;
				transition: box-shadow 0.3s;
			}

			.modules-item {
				background-color: aliceblue;
				width: 12rem;
				display: flex;
				justify-content: space-between;
				align-items: center;
				border-radius: 10px;
				margin: 10px;
				padding: 20px;
				cursor: pointer; //鼠标切换成手

				.item-img {
					display: flex;
					justify-content: space-between;
					align-items: center;

					img {
						width: 2rem;
						height: 2rem;
						margin-right: 0.5rem;
						object-fit: cover;
					}
				}
			}
		}
	}
</style>
