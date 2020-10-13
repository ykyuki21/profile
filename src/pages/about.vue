<template>
  <v-flex>
    <h2 class="heading">About</h2>
    <p>兵庫県出身、東京都在住の{{ getAge }}歳</p>
    <p>業務ではバックエンドを担当することが多いがフロントエンドも好き</p>
    <p>ユーザー体験の観点から、使っていて気持ちが良いと思ってもらえるサイトを作りたい</p>
    <h2 class="heading">Like</h2>
    <p>美味しいご飯</p>
    <p>サッカー観戦</p>
    <p>ゲーム</p>
    <p>漫画</p>
    <p>アニメ</p>
    <h2 class="heading">Skills</h2>
    <p>
      <span v-for="(skill, index) in skills" :key="index">
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
      skills: [
        'Ruby',
        'Ruby on Rails',
        'C#',
        'ASP.NET',
        'JavaScript',
        'TypeScript',
        'React',
        'Next.js',
        'CSS',
        'MySQL',
        'PostgreSQL',
        'Git',
        'GCP'
      ]
    }
  },
  computed: {
    getAge: function() {
      const today = new Date()
      const birth = new Date('1991-05-21')

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

.heading {
  margin-top: 10px;
}
</style>
