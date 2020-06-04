<template>
  <v-daialog v-model="dialog" width="500" disabled="true">
    <v-card>
      <v-card-title class="headline">
        <v-icon size="24">mdi-information</v-icon>サーバ移行のお知らせ
      </v-card-title>
      <v-card-text>
        サーバを新しくNetlifyからロリポップ！へ移行するにあたり，URLが変更になります．
        ブックマークをしている方はブックマークの再登録をお願いいたします．
        <br />
        {{
        redirectTime
        }}秒後にリダイレクトします．
      </v-card-text>
      <v-btn color="primary" text @click="redirectStart(0)">新しいURLへ</v-btn>
    </v-card>
  </v-daialog>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "RedirectNews",
  data() {
    return {
      redirectTime: 10
    };
  },
  created() {
    setInterval(() => {
      this.redirectTime--;
      this.redirectStart(this.redirectTime);
    }, 1000);
  },
  mounted() {},
  methods: {
    redirectStart(redirectTime: number) {
      if (redirectTime <= 0) {
        if (process.browser) {
          location.href = "https://covid19-miyazaki.digick.jp/";
        }
      }
    }
  }
});
</script>
