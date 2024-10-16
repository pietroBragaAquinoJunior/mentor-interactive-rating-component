<template>
  <div class="h-[100vh] bg-[hsl(216,12%,8%)] flex justify-center items-center">
    <div class="flex flex-col justify-around w-[88vw] h-[53vh] bg-gradient-to-b from-[hsla(213,19%,18%,0.8)] to-[hsla(213,19%,18%,0.5)] rounded-2xl p-5 md:w-[50vh] md:rounded-3xl md:p-8">
      <div class="bg-[hsl(213,19%,18%)] w-[45px] h-[45px] flex justify-center items-center rounded-full ">
        <img src="/images/icon-star.svg" alt="Icon Star">
      </div>
      <h1 class="text-[1.5rem] font-[700] md:text-[1.8rem]">
        How did we do?
      </h1>
      <p class="text-[0.85rem] text-[hsl(217,12%,63%)] md:text-[1rem]">
        Please let us know how we did with your support request. All feedback is appreciated
        to help us improve our offering!
      </p>
      <div class="flex justify-between items-center ">
        <div v-for="number in numbers" :key="number">
          <div
            v-if="number==rate"
            class="rounded-full bg-[hsl(0,0%,100%)] w-[40px] h-[40px] md:h-[45px] md:w-[45px] flex justify-center items-center text-[hsl(213,19%,18%)] font-[700] cursor-pointer hover:bg-[hsl(25,97%,53%)]"
          >
            {{ number }}
          </div>
          <div
            v-else
            class="rounded-full bg-[hsl(213,19%,18%)] w-[40px] h-[40px] md:h-[45px] md:w-[45px] flex justify-center items-center text-[hsl(217,12%,63%)] font-[700] cursor-pointer hover:bg-[hsl(25,97%,53%)] hover:text-[hsl(213,19%,18%)]"
            @click="changeRate(number)"
          >
            {{ number }}
          </div>
        </div>
      </div>
      <button class="uppercase bg-[hsl(25,97%,53%)] text-[hsl(213,19%,18%)] p-3 font-[700] rounded-full text-[16px] hover:bg-[hsl(0,0%,100%)]">
        submit
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
const numbers = ref([1, 2, 3, 4, 5])
const rate = ref(0)
const changeRate = (value: number) => {
  rate.value = value
}
</script>
