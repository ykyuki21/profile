<template>
  <v-flex>
    <h2 class="headline">About</h2>
    <p>兵庫県在住、神戸の街が好きな1991年5月生まれの28歳</p>
    <p>趣味はスポーツ観戦、ゲーム</p>
    <p>主に観るスポーツはサッカー(Jリーグ)、League of Legends</p>
    <p>ゲームはメルクストーリアを中心にプレイ中</p>
    <h2 class="headline">Skill</h2>
    <h3 class="subheading">実務経験有り</h3>
    <p>
      <span v-for="(skill, index) in skills" :key="index">
        <template v-if="index !== 0"
          >/
        </template>
        {{ skill }}
      </span>
    </p>
    <h3 class="subheading">実務経験無し</h3>
    <p>
      <span v-for="(skill, index) in hobby_skills" :key="index">
        <template v-if="index !== 0"
          >/
        </template>
        {{ skill }}
      </span>
    </p>
  </v-flex>
</template>

<script>
export default {
  data() {
    return {
      skills: ['C#', 'ASP.NET', 'CSS', 'JavaScript', 'PostgreSQL', 'IIS', 'SVN', 'Git', 'Jenkins'],
      hobby_skills: ['TypeScript', 'Vue.js', 'Firebase']
    }
  }
}
</script>

<style scoped>
p {
  margin-bottom: 0px;
}

.headline {
  margin-top: 10px;
}
</style>
