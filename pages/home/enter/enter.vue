<template>
	<view class="home">
		<BgHeader></BgHeader>
		<view class="swiper-item">
			<image mode="top" style="width: 100%;" :src="bgImg" />
		</view>
		<uni-grid :column="3" :showBorder='false' class="dataListGrid"  @change="linkto()">
			<uni-grid-item v-for="item in dataList" :key='item.index' :index='item.index' class="dataListItem">
				<view class="homeList">
					<image style="width:40px;height: 40px;" :src="item.icon" />
					<text class="text">{{item.text}}</text>
				</view>
			</uni-grid-item>
		</uni-grid>
	</view>

</template>

<script>
	import BgHeader from '../header/header.vue';
	export default {
		components: {
			BgHeader,
		},
	    data() {
	        return {
	            indicatorDots: false,  //显示面板指示点
	            autoplay: true,  //自动切换
	            interval: 5000,  //自动切换时间间隔
	            duration: 500,  //滑动动画时长
				circular:true, //采用衔接滑动，即播放到末尾后重新回到开头
				bgImg: require('../../../static/home/bg.jpg'),
				dataList:[
					{
						index:0,
						text:'学习',
						path:'study',
						icon: require('../../../static/home/study.png')
					},
					{
						index:1,
						text:'总结',
						path:'summary',
						icon: require('../../../static/home/summary.png')
					},
					{
						index:2,
						text:'阅读',
						path:'read',
						icon: require('../../../static/home/read.png')
					},
					{
						index:3,
						text:'收藏',
						path:'collect',
						icon: require('../../../static/home/collect.png')
					},
					{
						index:4,
						text:'运动',
						path:'motion',
						icon: require('../../../static/home/motion.png')
					},
				]
	        }
	    },
	    methods: {
			linkto(e){
				let item=e.detail.index;
				uni.navigateTo({
					url: `../../${this.dataList[item].path}/${this.dataList[item].path}`
				});
			}
	    }
	}
</script>

<style lang="less">
	.home{
		overflow: hidden;
		position: relative;
		.uni-padding-wrap,.page-section,.page-section-spacing,.swiper{
			min-height: 40vh;
			line-height: 40vh;
			padding: 0;
		}
		.dataListGrid{
			position: relative;
			margin-top: 20px;
			.dataListItem{
				.homeList{
					display: flex;
					flex-direction: column;
					align-items: center;
					justify-content: center;
					height: -webkit-fill-available;
					.text{
						margin-top: 10px;
					}
				}
			}

		}
	}
</style>
