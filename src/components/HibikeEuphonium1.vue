<template>
  <v-dialog v-model="dialog4" width="580px">
    <v-card>
      <v-icon id="icon" @click="close()">fas fa-times</v-icon>
      <v-carousel
              :height="imageHeight"
              hide-delimiter-background
              hide-delimiters
      >
        <v-carousel-item
                v-for="({src},i) in items"
                :key="i"
                :src="src"
        >
        </v-carousel-item>
      </v-carousel>
      <v-card-title>
        京都駅中央口JRホーム側改札外
      </v-card-title>
      <v-card-text>
        <p>アニメ、響け! ユーフォニアム、やはり俺の青春ラブコメはまちがっている。続など多数</p>
        <p>場所は<u>京都府京都市下京区東塩小路釜殿町</u></p>
        <p>ここを聖地と読んでいいのかわからないが、多くのアニメやゲームのシーンで使われている場所である。</p>
        <p>響け! ユーフォニアムでは2期7話の駅ビルコンサートでの演奏で使われいる。部長の小笠原晴香のサクソフォーンソロがめちゃカッコイイ</p>
        <p>やはり俺の青春ラブコメはまちがっている。続では2期1・2話の修学旅行編で使われている。</p>
        <div class="map">
          <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3268.8327678723413!2d135.75657801518423!3d34.985853375400254!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x600108ae918b02ef%3A0xb61a446e74a21c08!2z5Lqs6YO96aeF!5e0!3m2!1sja!2sjp!4v1572878273286!5m2!1sja!2sjp" frameborder="0" style="border:0;" allowfullscreen=""></iframe>
        </div>
        <v-card-actions>
          <v-spacer></v-spacer>
        </v-card-actions>
        <v-btn class="close-button" v-if="this.$vuetify.breakpoint.xs" @click="close()">Close</v-btn>
      </v-card-text>
    </v-card>
  </v-dialog>
</template>

<script>
  export default {
    name: "HibikeEuphonium1",
    data() {
      return {
        dialog4: false,
        items: [
          {
            src: 'https://pilgrimage-note-images.s3-ap-northeast-1.amazonaws.com/IMG_2430.jpg',
          },
        ]
      };
    },
    computed: {
      imageHeight () {
        switch (this.$vuetify.breakpoint.name) {
          case 'xs': return '240px'
          case 'sm': return '400px'
          case 'md': return '400px'
          case 'lg': return '400px'
          case 'xl': return '400px'
        }
        return this.imageHeight();
      },
    },
    methods: {
      open() {
        this.dialog4 = true;
      },
      close() {
        this.dialog4 = false;
      }
    }
  }
</script>

<style scoped>
  #icon {
    position: absolute;
    margin: 15px 20px;
    font-size: 25px;
    z-index: 1;
  }

  .map {
    position: relative;
    overflow: hidden;
    padding-bottom: 56.25%;
  }
  .map iframe {
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    width: 100%;
  }

  .close-button {
    float: right;
    margin-top: -22px;
  }

  @media screen and (max-width: 375px) {
    .map {
      margin: 25px 0 30px
    }
  }
</style>
