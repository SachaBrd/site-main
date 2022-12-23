<template>
  <div v-if="displayAbout" class="container bg-slate-800 rounded-lg max-w-[800px] m-2 overflow-x-auto mb-24">
    <div class="flex flex-row">
      <div class="container flex justify-start text-white p-2 pl-4 max-w-[800px] italic"><h2>Projects</h2>
      <!-- <span class="pl-5"
          ><Toggle
            v-model="pepeToggle"
            :classes="{
              container:
                'inline-block rounded-full outline-none focus:ring focus:ring-green-500 focus:ring-opacity-30',
              toggle:
                'flex w-12 h-4 rounded-full relative cursor-pointer transition items-center box-content border-2 text-xs leading-none',
              toggleOn:
                'bg-[#57a64a] border-[#57a64a] justify-start text-white',
              toggleOff:
                'bg-gray-300 border-gray-300 justify-end text-gray-700',
              toggleOnDisabled:
                'bg-gray-300 border-gray-300 justify-start text-gray-400 cursor-not-allowed',
              toggleOffDisabled:
                'bg-gray-200 border-gray-200 justify-end text-gray-400 cursor-not-allowed',
              handle:
                'inline-block bg-white w-5 h-4 top-0 rounded-full absolute transition-all',
              handleOn: 'left-full transform -translate-x-full',
              handleOff: 'left-0',
              handleOnDisabled:
                'bg-gray-100 left-full transform -translate-x-full',
              handleOffDisabled: 'bg-gray-100 left-0',
              label: 'text-center w-8 border-box whitespace-nowrap select-none',
            }"
        /></span> -->
      </div>
          
      <Transition>
        
      <div class="absolute right-48 -top-[-135px]" style="z-index:-900;" v-show="pepeToggle">
          <img class="strong-tilt-move-shake" 
            src="../assets/f2bg.png"
            rel="preload"
          />
        </div>
      </Transition>

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
          >site-main</a
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
// import Toggle from "@vueform/toggle";
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
      // pepeToggle: false,
    };
  },
  components: {
    colorText,
    // Toggle,
  },
};
</script>
