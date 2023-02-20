<template>
    <form>
        <input v-model="inputText" />
        <button type="button" @click="speech">Speech</button>
    </form>
</template>
  
<script>
import { Predictions } from 'aws-amplify';
import { ref } from 'vue';

export default {
    setup() {
        const inputText = ref('');

        const speech = () => {
            // Text Speech の実装
            Predictions.convert({
                textToSpeech: {
                    source: {
                        text: inputText.value,
                    },
                },
            })
                .then((result) => {
console.log(result);
                    const AudioContext = window.AudioContext || window.webkitAudioContext;
                    const audioCtx = new AudioContext();
                    const source = audioCtx.createBufferSource();

console.log('AudioContext', AudioContext);
console.log('audioCtx', audioCtx);
console.log('Before',source);

                    audioCtx.decodeAudioData(result.audioStream, (buffer) => {
                        source.buffer = buffer;
                        source.connect(audioCtx.destination);
                        source.start(0);
console.log('After',source);
                    });
                })
                .catch((error) => console.warn(error));
            // ↑↑↑↑↑↑
        };

        return {
            inputText,
            speech,
        };
    },
};
</script>
  
  