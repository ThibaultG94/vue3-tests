<template>
	<div>
		<!-- Menu view -->
		<!-- <h2>Menu {{ $route.params.id }}</h2> -->
		<h2>
			{{ menu.name }}
		</h2>
		<div>
			<img :src="`/images/${menu.image}`" :alt="menu.name" />
			<p>
				{{ menu.description }}
			</p>
		</div>
	</div>
</template>

<script>
import menuData from '@/data.json';

export default {
	computed: {
		menuId() {
			return parseInt(this.$route.params.id);
		},
		menu() {
			return menuData.menus.find((menu) => menu.id === this.menuId);
		},
	},
};
</script>
