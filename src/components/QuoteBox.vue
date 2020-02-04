<template>
	<div class="border rounded max-w-2xl shadow-lg rounded-lg overflow-hidden">
		<div class="px-6 py-4 bg-blue-100">
			<div class="text-center sm:text-left">
				<div class="inline-block container">
					<img class="w-6 h-6 absolute" src="../assets/quote.png" alt="quotation-mark">
					<p class="mx-8 p-4 text-blue-900 text-3xl">{{quote}}</p>
					<p class="mx-8 p-4 text-gray-500 text-xl">{{author}}</p>
				</div>
			</div>
		</div>
	</div>	
</template>

<script>
export default {
	props: ['quote', 'author'],
	data: function() {
		return {};
	},
}
</script>