<template>
	<div
		v-if="!hasPaid && isPaymentPeriod"
		class="max-w-3xl mx-auto px-4 sm:px-6 pt-4"
	>
		<UAlert
			color="neutral"
			title="Aporte pendiente"
			:description="`Tienes hasta el día 8 para realizar tu aporte de Q${currentAmount}.00`"
		/>
	</div>
</template>

<script setup lang="ts">
	const statusStore = usePaymentStatusStore()
	const { hasPaid, currentAmount, isPaymentPeriod, loading } =
		storeToRefs(statusStore)
</script>