<template>
  <div
    style="background-color: rgb(27, 29, 39)"
    class="
      p-2
      h-80
      flex
      mx-auto
      items-center
      justify-center
      transition-all
      transform-gpu
      transform-all
      hover:-translate-y-2
      ease-in-out
      duration-200
      shadow-white
      hover:shadow-2xl
    "
  >
    <div class="text-xl text-center">
      <img
        v-bind:src="image"
        alt=""
        srcset=""
      />
      <div class="text-lg drop-shadow dr">{{title}}</div>
      <div
        class="
          text-base
          px-3
          my-1
          py-3
          transition-all
          duration-300
          hover:bg-pink-600
          w-max
          mx-auto
          rounded-sm
          cursor-pointer
        "
      >
       <a v-bind:href="url">Watch</a> 
      </div>
    </div>
  </div>
</template>
<style>

</style>
<script>
export default {
      props: ['id', 'title', 'duration', 'image'],
}
</script>