<template>
  <div class="flex justify-center">
    <div>
      <a href=".">
        <h1>
          <!-- <img class="vertical-shake" margin-left="600" rel="preload" src="../assets/f2bg.png" alt="Title" /> -->
          <img class="vertical-shake" margin-left="600" rel="preload" src="../assets/sacha.png" alt="Title" />
        </h1>
        </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "titleCard",
  components: {},
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