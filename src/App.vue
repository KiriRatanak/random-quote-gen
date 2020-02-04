<template>
  <div id="app" class="container mx-auto my-24 max-w-lg">
	<gen-button class="mx-auto my-12" v-on:click.native="fetchQuote"/>
    <quote-box :quote="quote" :author="author"/>
  </div>
</template>

<script>
import QuoteBox from './components/QuoteBox'
import GenButton from './components/GenButton'

export default {
	name: 'app',
	components: {
		'quote-box' : QuoteBox,
		'gen-button' : GenButton
	},
	data: () => {
		return {
			quote: 'A life is worth more than a book',
			author: 'Rachel Caine'
		}
	},
	methods: {
		fetchQuote: async function() {
			const baseUrl = 'http://api.forismatic.com/api/1.0/?method=getQuote&lang=en&format=json'
			const result = await this.$http.get(baseUrl)
			this.quote = result.data.quoteText
			this.author = result.data.quoteAuthor
		},
	},
	created() {
	},
}
</script>

<style>

</style>
