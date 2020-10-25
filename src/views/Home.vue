<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
  <button @click="changeText">Log</button>
</template>

<script>
import {
  ref, computed, watch, onMounted,
} from 'vue';

// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import ENV from '@/constants';

export default {
  name: 'Home',
  components: {
    HelloWorld,
  },
  emits: ['emit-value'],
  props: {
    inputText: String,
  },
  setup(props, context) {
    onMounted(() => {
      console.log(context);
      console.log(ENV);
    });

    const templateText = ref('');
    const templateBoolean = ref(false);
    const templateObject = ref({});

    watch(templateText, (value) => {
      if (value) {
        console.log('Analytics: Invalid text');
      }
    });

    const checkInput = computed(() => (templateObject.value ? true : null));

    function changeText() {
      templateBoolean.value = true;
      console.log(templateBoolean.value);
      if (templateText.value === '') {
        return;
      }
      console.log(templateBoolean.value);
      context.emit('emit-value', templateText.value);
    }

    return {
      changeText,
      checkInput,
    };
  },
};
</script>
