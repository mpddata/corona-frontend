<template>
  <div class="flex flex-row justify-center">
    <div class="w-1/3 flex flex-col rounded overflow-hidden shadow text-center text-red-600">
      <div class="h-16 pt-2 flex flex-auto items-center justify-center bg-red-100 text-xl lg:text-3xl font-bold font-sans">
        <span class="mx-2">
          <!--<template v-if="typeof confirmed === 'number'">
            <animated-number :value="confirmed" :round="1" :duration="300" :formatValue="formatNumber" />
          </template>
          <template v-else>
            {{ confirmed }}
          </template>-->
          {{ confirmed | formatNumber }}
        </span>
      </div>
      <div class="py-1 w-full bg-red-200 text-sm lg:text-base font-semibold font-sans">
        <span class="mx-2">{{ $t('Confirmed') }}</span>
      </div>
    </div>
    <div class="w-1/3 mx-2 flex flex-col rounded overflow-hidden shadow text-center text-green-600">
      <div class="h-16 pt-2 flex flex-auto items-center justify-center bg-green-100 text-xl lg:text-3xl font-bold font-sans">
        <span class="mx-2">
          <!--<template v-if="typeof recovered === 'number'">
            <animated-number :value="recovered" :round="1" :duration="300" :formatValue="formatNumber" />
          </template>
          <template v-else>
            {{ recovered }}
          </template>-->
          {{ recovered | formatNumber }}
        </span>
      </div>
      <div class="py-1 w-full bg-green-200 text-sm lg:text-base font-semibold font-sans">
        <span class="mx-2">{{ $t('Recovered') }}</span>
      </div>
    </div>
    <div class="w-1/3 flex flex-col rounded overflow-hidden shadow text-center text-gray-600">
      <div class="h-16 pt-2 flex flex-auto items-center justify-center bg-gray-200 text-xl lg:text-3xl font-bold font-sans">
        <span class="mx-2">
          <!--<template v-if="typeof deaths === 'number'">
            <animated-number :value="deaths" :round="1" :duration="300" :formatValue="formatNumber" />
          </template>
          <template v-else>
            {{ deaths }}
          </template>-->
          {{ deaths | formatNumber }}
        </span>
      </div>
      <div class="py-1 w-full bg-gray-300 text-sm lg:text-base font-semibold font-sans">
        <span class="mx-2">{{ $t('Deaths') }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import AnimatedNumber from "animated-number-vue";

export default {
  props: {
    confirmed: [Number, String],
    recovered: [Number, String],
    deaths: [Number, String],
  },
  components: {
    AnimatedNumber
  },
  methods: {
    formatNumber(value) {
      return this.$options.filters.formatNumber(value);
    }
  }
}
</script>