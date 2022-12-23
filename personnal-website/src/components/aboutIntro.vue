<template>
  <div
    v-if="displayAbout"
   :class="{ 'container bg-slate-800 rounded-lg max-w-[800px] m-2 relative': displayProject, 'container bg-slate-800 rounded-lg max-w-[800px] m-2 relative mb-24': !displayProject }"
  >
    <div class="flex flex-row">
      <div
        class="container flex justify-start text-white p-2 pl-4 max-w-[800px] italic"
      >
        <h2>About</h2>
        <span class="pl-5"
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
        /></span>
      </div>
       <Transition>
      <div class="absolute right-24 -top-[135px]" v-show="pepeToggle">
        <!-- <a href=""> -->
        <img class="strong-tilt-move-shake"
          src="../assets/red.png"
          rel="preload"
        />
        <!-- </a> -->
      </div>
      </Transition>

      <div
        class="container flex justify-end text-white p-2 gap-2 max-w-[800px]"
      >
        <button
          class="rounded-full w-5 h-5 bg-[#00CA4E] hover:bg-[#33D571]"
        ></button>
        <button
          @click="this.$emit('closed')"
          class="rounded-full w-5 h-5 bg-[#FFBD44] hover:bg-[#FFCA69]"
        ></button>
        <button
          @click="this.$emit('closed')"
          class="rounded-full w-5 h-5 bg-[#FF605C] hover:bg-[#FF807D]"
        ></button>
      </div>
    </div>
    <div
      class="container bg-slate-900 min-h-[260px] rounded-bl-lg rounded-br-lg text-white p-1 max-w-[800px] font-mono"
    >
      <div class="text-[#57a64a] italic pl-3 flex flex-wrap">
        <colorText
          :printSpeed="20"
          :printStatus="sachaLine1"
          @printDone="sachaLine2 = true"
          printableText="//Hi my name is Sacha"
        ></colorText>
        <colorText
          class="whitespace-nowrap pl-1"
          :printSpeed="20"
          @printDone="sachaLine3 = true"
          :printStatus="sachaLine2"
          printableText=""
        ></colorText>
      </div>
      <div class="text-[#57a64a] italic pl-3 pb-3">
        <colorText
          :printSpeed="20"
          @printDone="sachaLine4 = true"
          :printStatus="sachaLine3"
          printableText="//I am a 24 years old data & cloud engineer living in Paris, France. I do code, play music, paint, digital art and more."
        ></colorText>
      </div>
      

      <div class="pl-3">
        <colorText
          :printSpeed="50"
          @printDone="sachaLine5 = true"
          :printStatus="sachaLine4"
          printableText="links = {"
        ></colorText>
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText
          class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine6 = true"
          :printStatus="sachaLine5"
          printableText="Mail:"
        ></colorText
        ><a
          v-if="sachaLine6"
          class="text-cyan-400 underline"
          href=""
          target="_blank"
          >bourdeau.sacha@gmail.com</a
        >
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText
          class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine7 = true"
          :printStatus="sachaLine6"
          printableText="Github:"
        ></colorText
        ><a
          v-if="sachaLine7"
          class="text-cyan-400 underline"
          href="https://github.com/sachabrd"
          target="_blank"
          >github.com/sachabrd</a
        >
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText
          class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine8 = true"
          :printStatus="sachaLine7"
          printableText="Instagram:"
        ></colorText
        ><a
          v-if="sachaLine8"
          class="text-cyan-400 underline"
          href="https://www.instagram.com/sachabrd_art/"
          target="_blank"
          >instagram.com/sachabrd_art</a
        >
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText
          class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine9 = true"
          :printStatus="sachaLine8"
          printableText="Spotify:"
        ></colorText
        ><a
          v-if="sachaLine9"
          class="text-cyan-400 underline"
          href="https://open.spotify.com/user/ozyra?si=db6ec2a855f74364"
          target="_blank"
          >spotify</a
        >
      </div>

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText
          class="pr-1"
          :printSpeed="50"
          @printDone="sachaLine10 = true"
          :printStatus="sachaLine9"
          printableText="Soundcloud:"
        ></colorText
        ><a
          v-if="sachaLine10"
          class="text-cyan-400 underline"
          href="https://soundcloud.com/sacha-bourdeau-781774250"
          target="_blank"
          >soundcloud</a
        >
      </div>

      
      

      <div class="text-purple-400 pl-6 flex flex-row">
        <colorText
          class="pr-1"
          @printDone="sachaLine11 = true"
          :printSpeed="50"
          :printStatus="sachaLine10"
          printableText=""
        ></colorText
        ><a
          v-if="sachaLine11"
          class="text-cyan-400 underline"
          href=""
          target="_blank"
          ></a
        >
      </div>

      <div class="pl-3">
        <colorText
          :printSpeed="50"
          :printStatus="sachaLine10"
          printableText="}"
        ></colorText>
      </div>

    </div>
  </div>
</template>

<script>
import colorText from "./colorText";
import Toggle from "@vueform/toggle";
export default {
  name: "aboutIntro",
  data() {
    return {
      sachaLine1: true,
      sachaLine2: false,
      sachaLine3: false,
      sachaLine4: false,
      sachaLine5: false,
      sachaLine6: false,
      sachaLine7: false,
      sachaLine8: false,
      sachaLine9: false,
      sachaLine10: false,
      sachaLine11: false,
      sachaLine12: false,
      displayAbout: true,
      pepeToggle: false,
    };
  },
  components: {
    colorText,
    Toggle,
  },
  props:{
    displayProject: Boolean
  }
};
</script>

<style>

.v-enter-active,
.v-leave-active {
  transition: opacity 0.3s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

img.strong-tilt-move-shake:hover {
  animation: tilt-n-move-shaking 0.20s infinite;
}

img.constant-tilt-shake {
  animation: tilt-shaking 0.3s infinite;
}

@keyframes tilt-n-move-shaking {
  0% { transform: translate(0, 0) rotate(0deg); }
  25% { transform: translate(2px, 2px) rotate(5deg); }
  50% { transform: translate(0, 0) rotate(0eg); }
  75% { transform: translate(-2px, 2px) rotate(-5deg); }
  100% { transform: translate(0, 0) rotate(0deg); }
}

@keyframes vertical-shaking {
  0% { transform: translateY(0) }
  25% { transform: translateY(2px) }
  50% { transform: translateY(-2px) }
  75% { transform: translateY(2px) }
  100% { transform: translateY(0) }
}

img.vertical-shake {
  animation: vertical-shaking 2s infinite;
}

</style>
