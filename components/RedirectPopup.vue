<template>
  <v-snackbar
    color="blue"
    :timeout="0"
    v-model="daialogFlag"
    :multi-line="multiLine"
    auto-height
    top
  >
    サーバをNetlifyからロリポップへ移行するため、URLが変更となります。
    <v-btn text @click="daialogFlag = false">閉じる</v-btn>
  </v-snackbar>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "RedirectPopup",
  data() {
    return {
      daialogTime: 2,
      daialogFlag: true,
      multiLine: true
    };
  },
  created() {
    // setInterval(() => {
    //   this.daialogTime--;
    //   if (this.daialogTime == 0) {
    //     this.daialogFlag = true;
    //   }
    // }, 1000);
  },
  mounted() {},
  methods: {}
});
</script>


