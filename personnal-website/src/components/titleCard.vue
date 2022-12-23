<template>
    <!-- <div> -->
    <!-- <div v-if="displayTitle"> -->
    <div class="flex justify-center"
      v-if="displayTitle" :class="{ '': displayTitle, '': !displayTitle }"
    >  
      <!-- <a href=""> -->
        <h1>
          <!-- <img class="vertical-shake" margin-left="600" rel="preload" src="../assets/f2bg.png" alt="Title" /> -->
          <img class="vertical-shake" margin-left="600" rel="preload" src="../assets/st2.png" alt="Title" />
        </h1>
      <!-- </a> -->
    </div>
</template>

<script>
export default {
  name: "titleCard",
  data() {
    return {
      displayTitle: true,
    };
  },
  components: {},
  props:{
    displayProject: Boolean
  }
};
</script>

<style>
@keyframes vertical-shaking {
  0% { transform: translateY(0) }
  25% { transform: translateY(5px) }
  50% { transform: translateY(0px) }
  75% { transform: translateY(5px) }
  100% { transform: translateY(0) }
}

img.vertical-shake {
  animation: vertical-shaking 2s infinite;
}
</style>