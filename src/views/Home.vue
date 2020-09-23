<template>
  <div class="home">
    <navbar/>
    <v-content>
      <v-container fluid>
        <v-alert
          outlined
          color="yellow darken-4"
        >
          <div class="title">DPTいちはらとは</div>
          <div>DPTいちはらは、Disaster Prevention Toolの略称で、その名前の通り防災のためのツールです。2019年秋の台風を経験した市内の大学生が、自らの経験や市民の方の声を受けて個人的に作成しました。</div>
        </v-alert>
        <v-card
          outlined
          class="mb-4"
          v-for="content in cardcontents"
          :key="content"
        >
          <v-card-title class="font-weight-black">{{content.title}}</v-card-title>
          <v-img
          :src="content.src"
          class="align-end"
          height="200px"
          >
          </v-img>
          <v-card-text class="text--primary">
            {{content.discript}}
          </v-card-text>
          <v-card-actions>
            <v-row justify="center" align-content="center">
              <v-btn color="primary">{{content.btncapt}}</v-btn>
            </v-row>
          </v-card-actions>
        </v-card>
      </v-container>
    </v-content>
  </div>
</template>

<script>
//import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    navbar
  },
  data: () => ({
    cardcontents:
      [{title:"避難所マップ",src:require("@/assets/hou.png"),discript:"災害種別ごとの避難所を確認することが出来ます。また、避難所の混雑度等を投稿したり、投稿内容を確認したりすることが出来ます。",url:"",btncapt:"避難所マップを開く"},
      {title:"災害発生状況マップ",src:require("@/assets/pap.png"),discript:"災害や停電の発生状況（被災状況）を地図上に投稿したり、投稿内容を確認したりすることが出来ます。",url:"",btncapt:"災害発生状況マップを開く"},
      {title:"ハザードマップ",src:require("@/assets/trip.png"),discript:"災害種別ごとのハザードマップを確認することが出来ます。",url:"",btncapt:"ハザードマップを開く"},
      {title:"災害伝言掲示板",src:require("@/assets/bor.png"),discript:"災害時に家族や友人等への伝言を残すことが出来ます。SNS等による連絡手段を失った場合や、ご自身の端末を使用できない場合などに利用できます。",url:"",btncapt:"災害伝言掲示板を開く"},
      {title:"災害に備えましょう",src:require("@/assets/chi.png"),discript:"災害に備えて用意しておきたい商品などを紹介しています。",url:"",btncapt:"災害に備える"}]
  })
}
</script>
