<script>
export default {
  props: {
    rating: {
      type: Number,
    },
  },
};
</script>

<template>
  <div class="p-[27px_20px_31px_24px] sm:p-[37px_42px_31px_36px]">
    <div class="inline-block p-[11px] bg-lightGray/10 rounded-full sm:p-[20px]">
      <svg
        viewBox="0 0 17 16"
        class="w-[14px] aspect-square sm:w-[18px]"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="m9.067.43 1.99 4.031c.112.228.33.386.58.422l4.45.647a.772.772 0 0 1 .427 1.316l-3.22 3.138a.773.773 0 0 0-.222.683l.76 4.431a.772.772 0 0 1-1.12.813l-3.98-2.092a.773.773 0 0 0-.718 0l-3.98 2.092a.772.772 0 0 1-1.119-.813l.76-4.431a.77.77 0 0 0-.222-.683L.233 6.846A.772.772 0 0 1 .661 5.53l4.449-.647a.772.772 0 0 0 .58-.422L7.68.43a.774.774 0 0 1 1.387 0Z"
          fill="#FC7614"
        />
      </svg>
    </div>
    <h2
      class="font-bold text-[24px] text-white mt-[15px] sm:mt-[27px] sm:text-[31px]"
    >
      How did we do?
    </h2>
    <p
      class="text-lightGray mt-[9px] text-[14px] sm:leading-[26px] sm:[word-spacing:0px] sm:font-semibold sm:text-[16px]"
    >
      Please let us know how we did with your support request. All feedback is
      appreciated to help us improve our offering!
    </p>
    <ul
      class="grid grid-cols-5 mt-[26px] justify-items-center gap-[18px] sm:gap-[29px]"
    >
      <li
        v-for="i in [1, 2, 3, 4, 5]"
        class="font-bold rounded-full w-full aspect-square flex justify-center items-center cursor-pointer hover:bg-orange hover:text-darkBlue"
        @click="$emit('setRating', i)"
        :class="{
          'bg-white text-darkBlue': rating === i,
          'bg-lightGray/10 text-lightGray': rating !== i,
        }"
        :key="i"
      >
        <span class="pt-[3px] leading-[14px] text-[14px] sm:text-[16px]">{{
          i
        }}</span>
      </li>
    </ul>
    <button
      class="w-full bg-orange text-[14px] text-veryDarkBlue rounded-full mt-[25px] py-[14px] tracking-[2px] font-bold flex justify-center items-center hover:bg-white sm:mt-[40px] sm:py-[16px] sm:text-[17px]"
      aria-label="Submit rating"
      @click="$emit('submitRating')"
    >
      <span class="inline-block h-[16px] sm:h-[18px]">SUBMIT</span>
    </button>
  </div>
</template>
