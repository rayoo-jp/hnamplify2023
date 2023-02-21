<template>
  <div class="left">
    <textarea class="ioarea" v-model="inputText" placeholder="翻訳する文字列"></textarea>
  </div>
  <div class="right">
    <textarea class="ioarea" v-model="translatedText" disabled> </textarea>
  </div>
  <div class="right">
    <button type="button" @click="speech">Speech</button>
  </div>
</template>

<script>
import { Predictions } from 'aws-amplify';
import { ref, watch } from 'vue';

export default {
  setup() {
    const inputText = ref('');
    const translatedText = ref('翻訳後の文字列');
    const textToSpeech = ref('スピーチ');


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
          // result.language = "en";
          translatedText.value = result.text;
          console.log('inputText = ', inputText);
          console.log('translateText result = ', result);
          console.log('translateText translatedText= ', translatedText);
        })
        .catch((error) => {
          console.warn({ error });
        });
      // ↑↑↑↑↑↑
    };

    watch(inputText, (inputText) => {
      translate(inputText);
    });


    const speech = () => {
      // Text Speech の実装
      Predictions.convert({
        // inputText = translatedText;
        textToSpeech: {
          source: {
            text: translatedText.value,
          },
        },
      })
        .then((result) => {
          console.log('speech', result);
          const AudioContext = window.AudioContext || window.webkitAudioContext;
          const audioCtx = new AudioContext();
          const source = audioCtx.createBufferSource();

          audioCtx.decodeAudioData(result.audioStream, (buffer) => {
            source.buffer = buffer;
            source.connect(audioCtx.destination);
            source.start(0);
          });
        })
        .catch((error) => console.warn(error));
      // ↑↑↑↑↑↑
    };



    return {
      inputText,
      translatedText,
      translate,
      textToSpeech,
      speech,
    };
  },
};
</script>
