<template>
    <Box>
      <div>
        <Link
          :href="route('listing.show', {listing: listing.id})"
        >
        <ListingAddress
            :listing="listing"
            class="text-lg font-semibold"
          />
          <div class="flex items-center gap-2">
            <Price
              :price="listing.price"
              class="text-2xl font-bold"
            />
            <div class="text-xs text-gray-500">
              <Price :price="monthlyPayment" /> / month
            </div>
          </div>
          <ListingDetail :listing="listing" class="text-lg" />
         
        </Link>
      </div>
      <div class="mt-3">
        <Link class="btn-primary bg-orange-400 mr-4"
          :href="route('listing.edit', {listing: listing.id})"
        >
          Edit
        </Link>
       
      </div>
    </Box>
  </template>
  
  <script setup>
  import { Link } from '@inertiajs/inertia-vue3'
  import ListingAddress from '@/Components/ListingAddress.vue'
  import Box from '@/Components/UI/Box.vue'
  import ListingDetail from '@/Components/ListingDetail.vue'
  import Price from '@/Components/Price.vue'
  import { useMonthlyPayment } from '@/Composables/useMonthlyPayment'
  const props = defineProps({listing: Object})
  const { monthlyPayment } = useMonthlyPayment(
    props.listing.price, 2.5, 25,
  )
  </script>