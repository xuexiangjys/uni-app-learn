<template>
	<view class="warp">
		<uni-grid :column="3" @change="change">
			<uni-grid-item v-for="(item, index) in list" :index="index" :key="index">
				<view class="grid-item-box">
					<uni-icons :type="item.name" :color="'#299ee3'" size="30" />
					<text class="text">{{ item.text }}</text>
				</view>
			</uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
	import uniGrid from "@/components/uni-grid/uni-grid.vue"
	import uniGridItem from "@/components/uni-grid-item/uni-grid-item.vue"
	import uniIcons from "@/components/uni-icons/uni-icons.vue"
	export default {
		components: {
			uniGrid,
			uniGridItem,
			uniIcons
		},
		data() {
			return {
				list: [{
						name: 'checkbox',
						url: './widget/button',
						text: '按钮',
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 2',
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 3',
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 4',
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 5',
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 6'
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 7'
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 8'
					},
					{
						name: 'cart',
						url: './widget/button',
						text: 'Grid 9'
					}
				]
			}
		},
		onLoad() {

		},
		methods: {
			change(e) {
				let {
					index
				} = e.detail
				uni.navigateTo({
					url: this.list[index].url
				});
			},
		}
	}
</script>

<style>
	.grid-item-box {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 15px 0;
	}

	.text {
		font-size: 15px;
		margin-top: 10px;
		color: #808080;
	}
</style>
