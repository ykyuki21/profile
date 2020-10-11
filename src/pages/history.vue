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
        title: 'Kobe City College of Technology',
        description:
          '電子工学科でPascal, C, Javaを学ぶ。また、C言語を利用したマイコンへの組み込みプログラミング等を行う。',
        tags: ['Pascal', 'C', 'Java', 'Linux'],
        color: 'indigo',
        year: '2007 ~'
      },
      {
        title: 'IVP Co., Ltd.',
        description:
          'バックエンドエンジニアとして大小様々なECサイトの開発に携わる。2018年からはチームリーダーとして、新人教育の強化やマネジメントも行う。',
        tags: [
          'C#',
          'ASP.NET',
          'HTML',
          'CSS',
          'JavaScript',
          'PostgreSQL',
          'SVN',
          'Git',
          'Windows Server',
          'IIS',
          'Jenkins'
        ],
        color: 'purple',
        year: '2016 ~'
      },
      {
        title: 'ZINEYOU, Inc',
        description:
          '自社サービスの開発に携わる。ビジネスチームからの要望を明確化して実装したり、自ら分析を行い機能の追加・改善を行う。また、モノリシックな環境を改善すべく、フロントエンドをNext.js、バックエンドをRailsに分割するプロジェクトを進める。',
        tags: ['Rails', 'MySQL', 'GCP', 'TypeScript', 'React', 'Next.js', 'jQuery'],
        color: 'deep-orange',
        year: '2019 ~'
      }
    ]
  })
}
</script>
