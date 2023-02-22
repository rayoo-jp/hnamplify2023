<template>
  <div class="home">
    <h1>
      Welcome to Amplify Vue Workshop, {{ username }} ! Click
      <a href="https://catalog.workshops.aws/amplify-vue3/ja-JP"> here </a> for hands-on.
    </h1>


    <h3>事前準備</h3>
    <p>
      このワークショップに挑戦するには、個人用、もしくは開発用の AWS アカウントが必要です。 作成されていない方は<a
        href="https://pages.awscloud.com/event_JAPAN_Ondemand_Hands-on-for-Beginners-1st-Step_LP.html">AWS Hands-on for
        Beginners ハンズオンはじめの一歩: AWS アカウントの作り方 & IAM 基本のキ</a> を参考にアカウントを作成してください。 また、ワークショップ内の作業で AdministratorAccess
      のポリシーをアタッチした IAM ユーザーを作成する必要があるため、管理者権限を持つ IAM
      ユーザーでワークショップを進めてください。
    </p>
    <h3>注意事項</h3>
    <p>
      このワークショップは1つの AWS アカウントで1人が実行することを前提としています。このワークショップを1つの AWS
      アカウントで複数人が実行すると、リソース名が競合します。リソース名にサフィックスを付ける、もしくはリージョンを分けることによって、競合を回避してください。
    </p>
    <p>
      このワークショップではマネジメントコンソールのスクリーンショットを手順に載せています。マネジメントコンソールは適宜アップデートされているため完全に画像と一致していない可能性があります。AWS
      の操作に慣れていない方はワークショップ中は自分では進めずに、必ず講師の指示に従って進めてください。 </p>
    <h3>参考リンク</h3>
    <ul>
      <li>
        <a href="https://docs.amplify.aws/"> AWS Amplify 公式ドキュメント </a>
      </li>
      <li>
        <a href="https://amplify-sns.workshop.aws/ja/"> Amplify SNS Workshop </a>
      </li>
      <li>
        <a href="https://aws.amazon.com/jp/builders-flash/202203/amplify-studio-flash-development/?awsf.filter-name=*all">
          アプリを爆速で開発 ! AWS Amplify Studio で出来ること。</a>
      </li>
      <li>
        <a href="https://github.com/aws-amplify-jp/awesome-aws-amplify-ja">AWS Amplify のツール、チュートリアル、記事などのリンク集</a>
      </li>
      <li>
        <a href="https://ja.vuejs.org/">Vue.js The Progressive JavaScript Framework</a>
      </li>
    </ul>
    <img src="..\data\AmplifyArchitecture.png" />
  </div>
</template>
  
<script>
export default {
  props: {
    username: String,
  },
};
</script>
  