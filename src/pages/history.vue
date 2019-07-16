<template>
  <v-layout justify-center>
    <v-timeline>
      <v-timeline-item v-for="(item, i) in items" :key="i" :color="item.color" small>
        <template v-slot:opposite>
          <span :class="`headline font-weight-bold ${item.color}--text`" v-text="item.year"></span>
        </template>
        <div class="py-3">
          <h2 :class="`headline font-weight-light mb-3 ${item.color}--text`">{{ item.title }}</h2>
          <div>
            {{ item.description }}
          </div>
        </div>
        <v-chip v-for="(tag, index) in item.tags" :key="index" label :color="`${item.color}`" text-color="white">
          <v-icon left>label</v-icon>{{ tag }}
        </v-chip>
      </v-timeline-item>
    </v-timeline>
  </v-layout>
</template>

<script>
export default {
  data: () => ({
    items: [
      {
        title: '少年期',
        description:
          '魔法のiらんどから始まり、ジオシティーズ、FC2等のレンタルサーバでゲームのファンサイトを作成・運用を行う。',
        tags: ['HTML', 'CSS'],
        color: 'indigo',
        year: '2002'
      },
      {
        title: '学生として',
        description:
          'Pascalから入りC言語、Javaを学ぶ。また、C言語を利用したマイコンへの組み込みプログラミング等を行う。',
        tags: ['Pascal', 'C', 'Java', 'Linux'],
        color: 'teal',
        year: '2007'
      },
      {
        title: '独学',
        description:
          'オブジェクト指向プログラミングの理解を深めるために再度Javaを学習し、その後Railsチュートリアルを利用してRuby on RailsでのWebアプリケーション制作を学習する。',
        tags: ['Java', 'Ruby', 'Ruby on Rails', 'Git'],
        color: 'pink',
        year: '2015'
      },
      {
        title: 'Web系システム開発会社にて',
        description:
          'ECサイトの受託開発を行う会社に入社し、主にバックエンドエンジニアとして大小様々な案件に携わる。2018年からはチームリーダーとして、新人教育の強化やマネジメントも行う。',
        tags: ['C#', 'ASP.NET', 'CSS(Sass)', 'JavaScript', 'PostgreSQL', 'SVN', 'Git', 'IIS', 'Jenkins'],
        color: 'purple',
        year: '2016'
      },
      {
        title: 'Portfolio作成',
        description: '最新のフロントエンド技術を試すべくNuxt.jsを利用してPortfolioサイトを作成する。',
        tags: ['Vue.js', 'Nuxt.js', 'Git'],
        color: 'deep-orange',
        year: '2019'
      }
    ]
  })
}
</script>
