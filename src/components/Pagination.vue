<template>
	<div>
		<nav aria-label="Page navigation example">
			<ul class="pagination">
				<li class="page-item" :class="{'disabled': !pagination.has_pre}">
					<a class="page-link" href="#" aria-label="Previous" @click.prevent="pageComponent(pagination.current_page - 1)">
						<span aria-hidden="true">&laquo;</span>
					</a>
				</li>
				<li class="page-item" v-for="page in pagination.total_pages" :key="page" :class="{'active':pagination.current_page === page}">
					<a class="page-link" href="#" @click.prevent="pageComponent(page)">{{page}}</a>
				</li>
				<li class="page-item" :class="{'disabled': !pagination.has_next}">
					<a class="page-link" href="#" aria-label="Next" @click.prevent="pageComponent(pagination.current_page + 1)">
						<span aria-hidden="true">&raquo;</span>
					</a>
				</li>
			</ul>
		</nav>
	</div>
</template>

<script>
	export default {
		name:'Pagination',
		props:{
			pagination :{
				type:Object
			},
		},
		data() {
			return {
			}
		},
		methods: {
			pageComponent(page){
				this.$emit('chageCurrentPage',page)
			}
		},
	}
</script>

<style lang="scss" scoped>

</style>