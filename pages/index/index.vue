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
						name: 'cart',
						text: 'Grid 1',
					},
					{
						name: 'cart',
						text: 'Grid 2',
					},
					{
						name: 'cart',
						text: 'Grid 3',
					},
					{
						name: 'cart',
						text: 'Grid 4',
					},
					{
						name: 'cart',
						text: 'Grid 5',
					},
					{
						name: 'cart',
						text: 'Grid 6'
					},
					{
						name: 'cart',
						text: 'Grid 7'
					},
					{
						name: 'cart',
						text: 'Grid 8'
					},
					{
						name: 'cart',
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
				this.list[index].badge && this.list[index].badge++

				uni.showToast({
					title: `点击第${index+1}个宫格`,
					icon: 'none'
				})
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
		padding: 15px 0;;
	}
</style>
