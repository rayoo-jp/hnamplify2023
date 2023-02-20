<template>
  <input id="check1" class="check" type="radio" name="ai" />
  <label class="label" for="check1"> テキスト翻訳 -  Japanese to Chinees with Speech - Amazon Translate/Polly </label>
  <div class="content">
    <TranslateText />
  </div>

  <input id="check2" class="check" type="radio" name="ai" />
  <label class="label" for="check2"> 画像物体認識 - Amazon Rekognition </label>
  <div class="content">
    <IdentifyLabels />
  </div>

  <input id="check3" class="check" type="radio" name="ai" />
  <label class="label" for="check3"> 画像テキスト抽出 - Amazon Rekognition(日本語検出不可) </label>
  <div class="content">
    <IdentifyText />
  </div>

  <input id="check4" class="check" type="radio" name="ai" />
  <label class="label" for="check4"> テキスト解析 - Amazon Comprehend </label>
  <div class="content">
    <InterpretText />
  </div>

  <input id="check5" class="check" type="radio" name="ai" />
  <label class="label" for="check5"> テキストスピーチ（日本語） - Amazon Polly </label>
  <div class="content">
    <TextSpeech />
  </div>
</template>

<script>
// 追加 2
import TranslateText from '@/components/TranslateText.vue';
import IdentifyLabels from '@/components/IdentifyLabels.vue';
import IdentifyText from '@/components/IdentifyText.vue';
import InterpretText from '@/components/InterpretText.vue';
import TextSpeech from '@/components/TextSpeech.vue';
export default {
  components: {
    // 追加 3
    TranslateText,
    IdentifyLabels,
    IdentifyText,
    InterpretText,
    TextSpeech,
  },
};
</script>
