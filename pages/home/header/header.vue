<template>
	<view class="information">
		<view class="informationList">
			<view class='informationListLeft'>
				<image class="icon" :src="headerIcon" />
				<view class='edition'>
					<view style="font-size: 16px;">诉诉飞飞</view>
					<view style="font-size: 12px;">1216827215@qq.com</view>
				</view>
			</view>
			<view class='informationListRight'>
				<text>{{edition}}</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				edition: 'v1.0.0',
				headerIcon: require('../../../static/home/header.jpg')
			}
		}
	}
</script>

<style lang="less">
	.information {
		position: absolute;
		z-index: 999;
		top: 5vh;
		width: -webkit-fill-available;

		.informationList {
			padding: 0 20px;
			width: inherit;
			display: flex;
			justify-content: space-between;

			.informationListLeft {
				display: flex;
				justify-content: flex-start;
				align-items: center;
				color: #FFFFFF;

				.icon {
					width: 50px;
					height: 50px;
					border-radius: 50%;
				}

				.edition {
					padding-left: 12px;
				}
			}
			.informationListRight {
				color: #EEEEEE;
			}

		}
	}
</style>
