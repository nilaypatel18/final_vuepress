<template>
	<div class="home">
		<div class="hero">
			<img
			v-if="data.heroImage"
			:src="$withBase(data.heroImage)"
			alt="hero"
			>
			<h1>{{ data.heroText || $title || 'Hello' }}</h1>
			<p class="description">
				{{ data.tagline || $description || 'Welcome to your VuePress site' }}
			</p>

			<p
			class="action"
			v-if="data.actionText && data.actionLink"
			>

		</p>
		<div
		class="features"
		v-if="data.features && data.features.length"
		>
		<div
		class="feature"
		v-for="(feature, index) in data.features"
		:key="index"
		>
		<h2>{{ feature.title }}</h2>
		<p>{{ feature.details }}</p>
	</div>
</div>
<Content custom/>

</div>
</div>
</div>
</template>
<script>
export default {
	name : "Home",
	computed:{
		data(){
			return this.$page.frontmatter
		},
		actionLink () {
			return {
				link: this.data.actionLink,
				text: this.data.actionText
			}
		}
	}
}
</script>