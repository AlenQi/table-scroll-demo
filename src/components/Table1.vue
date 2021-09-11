<template>
	<a-table
		:columns="columns"
		:data-source="data"
		class="components-table-demo-nested"
	>
		<a slot="operation">Publish</a>
		<a-table
			style="width: 1800px"
			slot="expandedRowRender"
			:columns="innerColumns"
			:data-source="innerData"
			:pagination="false"
			:scroll="{ x: 3000 }"
		>
			<span slot="status"> <a-badge status="success" />Finished </span>
			<span slot="operation" class="table-operation">
				<a>Pause</a>
				<a>Stop</a>
				<a-dropdown>
					<a-menu slot="overlay">
						<a-menu-item>
							Action 1
						</a-menu-item>
						<a-menu-item>
							Action 2
						</a-menu-item>
					</a-menu>
					<a> More <a-icon type="down" /> </a>
				</a-dropdown>
			</span>
		</a-table>
	</a-table>
</template>
<script>
const columns = [
	{ title: 'Name', dataIndex: 'name', key: 'name', width: 200 },
	{ title: 'Platform', dataIndex: 'platform', key: 'platform', width: 200 },
	{ title: 'Version', dataIndex: 'version', key: 'version', width: 200 },
	{ title: 'Upgraded', dataIndex: 'upgradeNum', key: 'upgradeNum', width: 200 },
	{ title: 'Creator', dataIndex: 'creator', key: 'creator', width: 200 },
	{ title: 'Date', dataIndex: 'createdAt', key: 'createdAt1', width: 200 },
	{ title: 'Date', dataIndex: 'createdAt', key: 'createdAt2', width: 200 },
	{ title: 'Date', dataIndex: 'createdAt', key: 'createdAt3', width: 200 },
	{
		title: 'Action',
		key: 'operation',
		scopedSlots: { customRender: 'operation' },
		width: 200
	},
];

const data = [];
for (let i = 0; i < 3; ++i) {
	data.push({
		key: i,
		name: 'Screem',
		platform: 'iOS',
		version: '10.3.4.5654',
		upgradeNum: 500,
		creator: 'Jack',
		createdAt: '2014-12-24 23:12:00',
	});
}

const innerColumns = [
	{ title: 'Date', dataIndex: 'date', key: 'date1', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date2', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date3', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date4', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date5', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date7', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date8', width: 300 },
	{ title: 'Date', dataIndex: 'date', key: 'date9', width: 300 },
	{ title: 'Name', dataIndex: 'name', key: 'name', width: 300 },
	{
		title: 'Status',
		key: 'state',
		scopedSlots: { customRender: 'status' },
		width: 300,
	},
	{
		title: 'Upgrade Status',
		dataIndex: 'upgradeNum',
		key: 'upgradeNum',
		width: 300,
	},
	{
		title: 'Action',
		dataIndex: 'operation',
		key: 'operation',
		fixed: 'right',
		scopedSlots: { customRender: 'operation' },
		width: 300,
	},
];

const innerData = [];
for (let i = 0; i < 3; ++i) {
	innerData.push({
		key: i,
		date: '2014-12-24 23:12:00',
		name: 'This is production name',
		upgradeNum: 'Upgraded: 56',
	});
}

export default {
	name: 'Table',
	data() {
		return {
			data,
			columns,
			innerColumns,
			innerData,
		};
	},
};
</script>
