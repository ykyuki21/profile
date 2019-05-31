<template>
  <v-flex>
    <h2 class="headline">About</h2>
    <p>兵庫県在住、神戸の街が好きな{{ getAge }}歳</p>
    <p>お仕事ではECサイトのバックエンドを担当</p>
    <p>一番幸福を感じる瞬間は美味しい物を食べている時</p>
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
  },
  computed: {
    getAge: function() {
      const today = new Date()
      const birth = new Date('1991-05-21')

      // TODO: 今年の年齢を変数名でわかりやすく表現したい
      const age = today.getFullYear() - birth.getFullYear()

      if (
        today.getMonth() > birth.getMonth() ||
        (today.getMonth() === birth.getMonth() && today.getDate() >= birth.getDate())
      ) {
        return age
      } else {
        return age - 1
      }
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
