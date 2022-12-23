<template>
  <div v-if="displayCredits" class="container bg-slate-800 rounded-lg max-w-[800px] m-2 overflow-x-auto mb-24">
    <div class="flex flex-row">
      <div class="container flex justify-start text-white p-2 pl-4 max-w-[800px] italic"><h2>Credits</h2>
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
    </div>
  


    <div
      class="container bg-slate-900 min-h-[100px] rounded-bl-lg rounded-br-lg text-white p-1 max-w-[800px] font-mono"
    >
      <div class="text-[#57a64a] italic pl-3 flex flex-wrap">
        <colorText
          :printSpeed="20"
          :printStatus="sachaLine1"
          @printDone="sachaLine2 = true"
          printableText="//Credits"
        ></colorText>
        <colorText
          class="whitespace-nowrap pl-1"
          :printSpeed="20"
          @printDone="sachaLine3 = true"
          :printStatus="sachaLine2"
          printableText=""
        ></colorText>
      </div>

      <div class="text-[#57a64a] italic pl-3 flex flex-wrap">
        <colorText
          :printSpeed="20"
          :printStatus="sachaLine2"
          @printDone="sachaLine3 = true"
          printableText="//Website made by me, main character drawn by me, all other characters from pinterest"
        ></colorText>
      </div>

      <img src="../assets/f2bg.png" rel="preload" />
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
      displayCredits: true,
    };
  },
  components: {
    colorText,
  },
};
</script>
