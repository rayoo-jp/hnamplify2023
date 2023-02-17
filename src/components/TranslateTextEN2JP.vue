<template>
  <div class="left">
    <textarea class="ioarea" v-model="inputText" placeholder="翻訳する文字列"></textarea>
  </div>
  <div class="right">
    <textarea class="ioarea" v-model="translatedText" disabled> </textarea>
  </div>
</template>

<script>
import { Predictions } from 'aws-amplify';
import { ref, watch } from 'vue';

export default {
  setup() {
    const inputText = ref('');
    const translatedText = ref('Translated strings');

    const translate = (text) => {
      if (!text.length) {
        translatedText.value = '';
        return;
      }

      // Text Translate の実装 ↓
      Predictions.convert({
        translateText: {
          source: {
            text: text,
          },
        },
      })
        .then((result) => {
          translatedText.value = result.text;
        })
        .catch((error) => {
          console.warn({ error });
        });
      // ↑↑↑↑↑↑

    };

    watch(inputText, (inputText) => {
      translate(inputText);
    });

    return {
      inputText,
      translatedText,
      translate,
    };
  },
};
</script>
