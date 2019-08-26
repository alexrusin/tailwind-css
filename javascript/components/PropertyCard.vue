<template>
    <div class="bg-white rounded-lg overflow-hidden shadow-lg">
        <div class="relative pb-2/3">
            <img class="absolute h-full w-full object-cover" :src="property.imageUrl" :alt="property.imageAlt">
        </div>
        <div class="p-6">
            <div class="flex items-baseline">
                <span class="inline-block bg-teal-200 text-teal-800 text-xs px-2 rounded-full uppercase font-semibold tracking-wide">New</span>
                <div class="ml-2 text-gray-600 text-xs uppercase font-semibold tracking-wide">
                    {{ property.beds }} beds &bull; {{ property.baths }} baths
                </div>
            </div>
            <h4 class="mt-1 font-semibold text-lg leading-tight truncate">{{ property.title }}</h4>
            <div class="mt-1">
                {{ property.formattedPrice }} 
                <span class="text-gray-600 text-sm"> / wk </span>
            </div>
            <div class="mt-2 flex items-center">
                <svg v-for="i in 5" :key="i" :class="i <= property.rating ? 'text-teal-500' : 'text-gray-400'" class="h-4 w-4 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
                    <path d="M10 1.3l2.388 6.722H18.8l-5.232 3.948 1.871 6.928L10 14.744l-5.438 4.154 1.87-6.928-5.233-3.948h6.412L10 1.3z"/>
                </svg>
                <span class="ml-2 text-gray-600 text-sm">{{property.reviewCount }} reviews</span>
            </div>
            </div>
    </div>
</template>

<script>
export default {
    props: ['property']
}
</script>