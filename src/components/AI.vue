<template>
  <input id="check1" class="check" type="radio" name="ai" />
  <label class="label" for="check1"> Translate - English to Japanese </label>
  <div class="content">
    <!-- 追加 1 -->
    <TranslateText />
  </div>

  <input id="check2" class="check" type="radio" name="ai" />
  <label class="label" for="check2"> Indentify Labels - Amazon Rekognition </label>
  <div class="content">
    <!-- 追加 1 -->
    <IdentifyLabels />
  </div>

  <input id="check3" class="check" type="radio" name="ai" />
  <label class="label" for="check3"> Indentify Text - Amazon Rekognition </label>
  <div class="content">
  </div>

  <input id="check4" class="check" type="radio" name="ai" />
  <label class="label" for="check4"> Interpret Text - Amazon Comprehend </label>
  <div class="content">
  </div>

  <input id="check5" class="check" type="radio" name="ai" />
  <label class="label" for="check5"> Text to Speech - Amazon Polly </label>
  <div class="content">
  </div>
</template>

<script>
// 追加 2
import TranslateText from '@/components/TranslateTextEN2JP.vue';
import IdentifyLabels from '@/components/IdentifyLabels.vue';

export default {
  components: {
    // 追加 3
    TranslateText,
    IdentifyLabels,
  },
};
</script>
