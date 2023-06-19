<template>
	<view class="content">
		<view class="wrapper">
			<view class="title">基础使用</view>
			<DateTabs :value.sync="value1" @change='onDateTabsChange'></DateTabs>
			<view class="value">当前日期：{{ value1 }}</view>
		</view>
		<view class="wrapper">
			<view class="title">设置当前日期、开始日期和结束日期</view>
			<DateTabs :value.sync="value2" startDate="2023-06-01" endDate="2023-06-30"></DateTabs>
			<view class="value">当前日期：{{ value2 }}</view>
		</view>
		<view class="wrapper">
			<view class="title">设置朴素样式</view>
			<DateTabs :value.sync="value3" plain></DateTabs>
			<view class="value">当前日期：{{ value3 }}</view>
		</view>
		<view class="wrapper">
			<view class="title">设置主题色</view>
			<DateTabs :value.sync="value4" color="red" bgColor="rgba(255, 0, 0, 0.1)"></DateTabs>
			<view class="value">当前日期：{{ value4 }}</view>
		</view>
	</view>
</template>

<script>
	import DateTabs from '@/uni_modules/hope-11-date-tabs/components/hope-11-date-tabs/date-tabs.vue'

	export default {
		components: {
			DateTabs,
		},
		data() {
			return {
				value1: '',
				value2: '2023-06-06',
				value3: '',
				value4: '',
			}
		},
		onLoad() {

		},
		methods: {
			onDateTabsChange(e) {
				console.log(e)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;

		.wrapper {
			margin: 20px 0;

			.title {
				margin-bottom: 10px;
				font-weight: bold;
				display: flex;
				justify-content: center;
				align-items: center;
			}

			.value {
				margin-top: 10px;
				display: flex;
				justify-content: center;
				align-items: center;
			}
		}
	}
</style>