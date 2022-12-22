<template>
  <div v-if="displayAbout" class="container bg-slate-800 rounded-lg max-w-[800px] m-2 overflow-x-auto mb-24">
    <div class="flex flex-row">
      <div class="container flex justify-start text-white p-2 pl-4 max-w-[800px] italic"><h2>Projects</h2></div>
      <div class="container flex justify-end text-white p-2 gap-2 max-w-[800px]">
      <button
        class="rounded-full w-5 h-5 bg-[#00CA4E] hover:bg-[#33D571]"
      ></button>
      <button @click="this.$emit('closed')"
        class="rounded-full w-5 h-5 bg-[#FFBD44] hover:bg-[#FFCA69]"
      ></button>
      <button
        @click="this.$emit('closed')"
        class="rounded-full w-5 h-5 bg-[#FF605C] hover:bg-[#FF807D]"
      ></button>
    </div>
    </div>
    <div
      class="container bg-slate-900 min-h-[100px] rounded-bl-lg rounded-br-lg text-white p-1 max-w-[800px] font-mono"
    >
      <div class="text-[#57a64a] italic pl-3 flex flex-wrap">
        <colorText
          :printSpeed="20"
          :printStatus="sachaLine1"
          @printDone="sachaLine2 = true"
          printableText="//My Projects so far"
        ></colorText>
      </div>

      <div class="pl-3">
        <colorText
          :printSpeed="50"
          @printDone="sachaLine3 = true"
          :printStatus="sachaLine2"
          printableText="links = {"
        ></colorText>
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine4 = true"
          :printStatus="sachaLine3"
          printableText="This website: "
        ></colorText
        ><a v-if="sachaLine4"
          class="text-cyan-400 underline"
          href="https://github.com/SachaBrd/site-main"
          target="_blank"
          >https://github.com/SachaBrd/site-main</a
        >
      </div>

      <!-- <div class="text-purple-400 pl-6 flex flex-row">
        <colorText class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine5 = true"
          :printStatus="sachaLine4"
          printableText="Restaurant: "
        ></colorText
        ><a v-if="sachaLine5"
          class="text-cyan-400 underline"
          href="https://github.com/SachaBrd/site-restaurant"
          target="_blank"
          >https://github.com/SachaBrd/site-restaurant</a
        >
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine6 = true"
          :printStatus="sachaLine5"
          printableText="Pokmeon battle : "
        ></colorText
        ><a v-if="sachaLine6"
          class="text-cyan-400 underline"
          href="https://github.com/SachaBrd/pokemon-battle-system"
          target="_blank"
          >https://github.com/SachaBrd/pokemon-battle-system</a
        >
      </div> -->

      <div class="pl-3">
        <colorText
          :printSpeed="50"
          :printStatus="sachaLine3"
          printableText="}"
        ></colorText>
      </div>

    </div>
  </div>
</template>

<script>
import colorText from "./colorText";
export default {
  name: "OSWindow",
  data() {
    return {
      sachaLine1: true,
      sachaLine2: false,
      sachaLine3: false,
      sachaLine4: false,
      sachaLine5 : false,
      sachaLine6 : false,
      displayAbout: true,
    };
  },
  components: {
    colorText,
  },
};
</script>
