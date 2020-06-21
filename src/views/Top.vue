<template>
  <div>
    <!-- Navigation bar -->
    <Header />

    <!-- Head area -->
    <section
      class="hero is-origin-color is-fullheight is-fullheight-with-navbar"
    >
      <div class="hero-body">
        <div class="container">
          <div class="columns">
            <div class="column is-one-fifth-tablet">
              <figure class="image is-128x128" style="margin: auto">
                <img
                  alt="プロフィール写真"
                  class="is-rounded"
                  src="@/assets/myIcon.jpg"
                />
              </figure>
            </div>
            <div class="column is-four-fifths-tablet has-text-centered-mobile">
              Hello! I am
              <h1 class="title is-1">
                Lima.json
              </h1>
              <h2 class="subtitle is-3">
                Backend Engineer <br />(API Developer)
              </h2>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- About -->
    <section class="section" id="about">
      <!-- Title -->
      <div class="section-heading">
        <h3 class="title is-2">About Me</h3>
        <h4 class="subtitle is-5">私について、概要</h4>
        <div class="container">
          <p>
            API開発を主としたバックエンドエンジニアをしています。<br />
            MAU300万を超えるスマホアプリや、スマホでの注文を行うSPAのバックエンド開発をしてきました。
            業務経験のある言語はPHP(Laravel)、vue.jsはコードレビュー程度。AWS上での開発をしました。<br />
            個人的にflutter, go, vue.jsの勉強をしています。
            このサイトもvue.jsとCSSとしてbulmaで作っています。<br />
            バックエンドエンジニアから、次のステージとしてアーキテクトを目指してバックエンドに限らず様々な知識を集めています。
          </p>
        </div>
      </div>

      <div class="columns has-same-height is-gapless">
        <div class="column">
          <!-- Profile -->
          <div class="card">
            <div class="card-content">
              <h3 class="title is-4">Profile</h3>

              <div class="content">
                <table class="table-profile">
                  <tr>
                    <th colspan="1"></th>
                    <th colspan="2"></th>
                  </tr>
                  <tr>
                    <td>Address:</td>
                    <td>Tokyo, Kanagawa</td>
                  </tr>
                  <tr>
                    <td>Phone:</td>
                    <td>secret!!</td>
                  </tr>
                  <tr>
                    <td>Email:</td>
                    <td>lmimsra07@gmail.com</td>
                  </tr>
                </table>
              </div>
              <br />
              <div class="buttons has-addons is-centered">
                <a href="https://github.com/lmimsra" class="button is-link">
                  Github
                </a>
                <a
                  href="https://twitter.com/lmimsra_dev"
                  class="button is-link"
                >
                  Twitter
                </a>
              </div>
            </div>
          </div>
        </div>
        <div class="column">
          <!-- Skills -->
          <div class="card">
            <div class="card-content skills-content">
              <h3 class="title is-4">Skills</h3>
              ※個人の100% 独断で評価しています
              <div class="content">
                <SkillBar
                  v-for="(skill, index) in skills"
                  v-bind:key="index"
                  v-bind:skill-name="skill.name"
                  v-bind:skill-level="skill.value"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills tags -->
    <div class="tags custom-tags">
      <span
        class="tag is-light"
        v-for="(tagName, index) in skillTags"
        v-bind:key="index"
      >
        {{ tagName }}
      </span>
    </div>

    <!-- Resume -->
    <section class="section" id="resume">
      <div class="section-heading section-text">
        <h3 class="title is-2">Resume</h3>
        <h4 class="subtitle is-5">実績・経験</h4>
      </div>
      <!--   TODO: そのうち経歴書ダウンロードできるようにしたい   -->
      <!--      <a href="#" class="button is-link is-medium">-->
      <!--        <span class="icon">-->
      <!--          <i class="fas fa-file-alt"></i>-->
      <!--        </span>-->
      <!--        <span>Download My Resume</span>-->
      <!--      </a>-->
      <div class="container">
        <div class="columns is-multiline">
          <Resume
            v-for="(resume, index) in resumes"
            v-bind:key="index"
            v-bind:title="resume.title"
            v-bind:about="resume.about"
            v-bind:technology="resume.technology"
            v-bind:role="resume.role"
            v-bind:performance="resume.performance"
            v-bind:members="resume.members"
          />
        </div>
      </div>
    </section>
    <!-- あとのために少しだけコメントを残す -->
    <!-- Services -->
    <!-- <section class="section" id="services">
      <div class="section-heading section-text">
        <h3 class="title is-2">Services</h3>
        <h4 class="subtitle is-5">提供する価値</h4>
      </div>
      <div class="container">
        <div class="columns">
          <div class="column">
            <div class="box">
              <div class="content">
                <h4 class="title is-5">バックエンド API開発</h4>
                Laravelフレームワークを使ったAPI開発の設計、実装、テストコード、各種テストまで対応します。
              </div>
            </div>
          </div>
        </div>
      </div>
    </section> -->

    <!-- Resume -->
    <!-- <section class="section" id="resume">
      <div class="section-heading section-text">
        <h3 class="title is-2">Resume</h3>
        <h4 class="subtitle is-5">More about my past</h4>
        <a href="#" class="button is-link is-medium">
          <span class="icon">
            <i class="fas fa-file-alt"></i>
          </span>
          <span>Download My Resume</span>
        </a>
      </div>
    </section> -->

    <!-- Portfolio -->
    <section class="section" id="portfolio">
      <div class="container">
        <div class="section-heading section-text">
          <h3 class="title is-2">Portfolio</h3>
          <h4 class="subtitle is-5">作ったものなど</h4>
        </div>
        <br />

        <div class="container portfolio-container">
          <div class="columns is-multiline">
            <div
              class="column is-half-tablet"
              v-for="(item, index) in portfolios"
              v-bind:key="index"
            >
              <PortfolioCard
                :title="item.title"
                :tags="item.tags"
                :image-file="item.imageFile"
                :description="item.description"
                :preview-link="item.previewLink"
                :code-link="item.codeLink"
              />
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Achievement Level -->
    <section class="section">
      <nav class="level">
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Tweets</p>
            <p class="title">150,000</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Following</p>
            <p class="title">641</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Followers</p>
            <p class="title">427</p>
          </div>
        </div>
        <div class="level-item has-text-centered">
          <div>
            <p class="heading">Likes</p>
            <p class="title">11,000</p>
          </div>
        </div>
      </nav>

      <div class="twitter-widget">
        <Timeline
          :id="tweetId"
          :source-type="'profile'"
          :options="{ height: tweetHeight }"
        />
      </div>
    </section>

    <!-- Contact -->
    <section class="section" id="contact">
      <div class="container">
        <div class="section-heading section-text">
          <h3 class="title is-2">Contact</h3>
          <h4 class="subtitle is-5">Twitterかメールでよろしくです！</h4>
          <h4 class="subtitle is-5">（フォーム準備できずすいません）</h4>
        </div>
        <br />

        <!-- <div class="columns">
          <div class="column is-6 is-offset-3">
            <div class="box">
              <div class="field">
                <label class="label">Name</label>
                <div class="control">
                  <input class="input" type="text" placeholder="Text input" />
                </div>
              </div>

              <div class="field">
                <label class="label">Email</label>
                <div class="control has-icons-left">
                  <input
                    class="input"
                    type="email"
                    placeholder="Email input"
                    value=""
                  />
                  <span class="icon is-small is-left">
                    <i class="fas fa-envelope"></i>
                  </span>
                </div>
              </div>

              <div class="field">
                <label class="label">Message</label>
                <div class="control">
                  <textarea class="textarea" placeholder="Textarea"></textarea>
                </div>
              </div>

              <div class="field is-grouped has-text-centered">
                <div class="control">
                  <button class="button is-link is-large">
                                        <span class="icon">
                                          <i class="fas fa-envelope"></i>
                                        </span>
                    <span>Submit</span>
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div> -->
      </div>
    </section>

    <!-- Footer -->
    <Footer />
  </div>
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'
import SkillBar from '@/components/SkillBar'
import PortfolioCard from '@/components/PortfolioCard'
import { Timeline } from 'vue-tweet-embed'
import Resume from '@/components/Resume'
export default {
  name: 'Top',
  data() {
    return {
      skills: [
        // max100にすると計算しやすい
        { name: 'PHP(Laravel)', value: 75 },
        { name: 'JavaScript(vue.js)', value: 30 },
        { name: 'HTML5/CSS3', value: 30 },
        { name: 'Dart(Flutter)', value: 10 },
        { name: 'Go', value: 10 },
        { name: 'Database(MySQL)', value: 45 }
      ],
      skillTags: [
        'Node.js',
        'VueJS',
        'JavaScript',
        'HTML5',
        'CSS3',
        'Bulma',
        'Bootstrap',
        'PHP',
        'Laravel',
        'MySQL',
        'AWS',
        'Go',
        'Flutter',
        'PHPUnit',
        'Git',
        'RESTful API',
        'JetBrains',
        'Nginx',
        'firebase',
        'serverless'
      ],
      portfolios: [
        {
          title: 'portfolio site',
          tags: ['vue.js', 'PWA', 'bulma'],
          // imageFile: 'noImage.png',
          imageFile: null,
          description:
            '自分の経歴などを紹介するサイト。vueとbulmaで実装。テンプレからなのでアプリケーション的に使えるように改善していきたい。' +
            'AWSのパイプラインで自動デプロイできるようにするまではがんばりました。そう、このサイトですw',
          previewLink: 'https://www.lmimsra.dev/',
          codeLink: 'https://github.com/lmimsra/Profile'
        },
        {
          title: 'Nuxt.js on Lambda',
          tags: ['nuxt', 'lambda', 'ssr'],
          // imageFile: 'noImage.png',
          imageFile: null,
          description:
            'Nuxtをサーバーレスにしたくて作成。ブログのネタにもしたかった。 ServerlessというCLIでデプロイしてます。 ソースコードの中身はほぼないです',
          previewLink: 'https://test.apisample.dev/',
          codeLink: 'https://github.com/lmimsra/NuxtOnLambda'
        },
        {
          title: 'Git Commit Checker',
          tags: ['go', 'lambda'],
          imageFile: null,
          description:
            '実行日のGitのアクティビティ数を確認してTwitterとSlackに送信するバッチとして利用。Goを試しに使ってみたくて作成',
          previewLink:
            'https://twitter.com/lmimsra_dev/status/1226156340722196480?s=20',
          codeLink: 'https://github.com/lmimsra/GitCommitChecker'
        },
        {
          title: 'Vue PWA APP',
          tags: ['vue.js', 'PWA', 'firebase'],
          // imageFile: 'noImage.png',
          imageFile: null,
          description:
            '社内向けにBBQイベント主催するために周知、ビンゴ用に突貫で作成。初めてvueをまともに書いたのもこのアプリ',
          previewLink: null,
          codeLink: 'https://github.com/lmimsra/VuePwaSample'
        },
        {
          title: 'privante',
          tags: ['flutter', 'firebase', 'serverless'],
          // imageFile: 'noImage.png',
          imageFile: null,
          description:
            'VueのPWAアプリを外部に出したいと思ってflutterの勉強がてら作成中のアプリ。初めてのことが多すぎて苦戦中です。',
          previewLink: null,
          codeLink: 'https://github.com/lmimsra/privante'
        }
      ],
      tweetId: 'lmimsra_dev',
      tweetHeight: '800',
      resumes: [
        {
          title: 'スマホ予約アプリAPI開発',
          about: '大手飲食店の席予約アプリ運用開発',
          technology: 'Lumen(php7.0), Redis, MySQL, EC2(AWS)',
          role:
            '運用保守案件の要件定義, 設計, 実装, テスト, アプリ開発のベンダコントロール',
          performance:
            'バックエンド開発リード, 既存バグの改修, 案件レベルの要件定義, アプリ用の管理画面新規開発',
          members: '6人(PM1, バックエンド2, ネイティブ3)'
        },
        {
          title: '商品注文SPA API開発',
          about: '大手飲食店の注文アプリ新規開発・運用',
          technology:
            'vue.js, Laravel(php7.3), RedisCluster, MySQL, Docker, ECS(AWS)',
          role:
            '新規開発の要件定義, 設計, 実装, テスト, 運用保守全般, ' +
            'アプリ開発のベンダコントロール, ネイティブ, web, API横断的な開発サポート',
          performance:
            'PM, PL, バックエンド開発リード, 新規API設計90本(PJ合計), API実装, 運用保守対応全般, cloudWatchを使ったログ調査',
          members: '10人(PM1, バックエンド3, ネイティブ3, フロント2, 企画1)'
        },
        {
          title: '飲食店向けオウンドアプリ開発',
          about: '大手飲食チェーン向けのオウンドアプリ新規開発',
          technology:
            'bootstrap, Laravel(php7.4), RedisCluster, MySQL, Docker, ECS(AWS)',
          role: '新規開発の要件定義, アーキテクチャ設計, API概要設計',
          performance:
            'アプリケーション全体の要件定義, サーバーサイド技術選定, サーバーサイド全体のアーキテクチャ設計, RESTFullなAPI設計',
          members: '8人(PM1, バックエンド3, ネイティブ3, フロント1)'
        },
        {
          title: '飲食店向けスマホ注文アプリ web拡張',
          about:
            '飲食チェーンを対象としたスマートフォン注文アプリのネイティブ版からweb対応する機能拡張',
          technology:
            'vue.js, Laravel(php7.3), RedisCluster, MySQL, Docker, ECS(AWS)',
          role: '要件定義, 設計, 実装, テスト, アーキテクチャ設計',
          performance:
            'バックエンド開発全体のリード, タスク管理, 機能拡張に伴う認証周辺の詳細設計・実装',
          members: '7人(PM1, バックエンド2, ネイティブ2, フロント1, 企画1)'
        },
        {
          title: '問診票システム開発',
          about: '病院向け問診票電子化プロジェクト(大学在学中)',
          technology: 'JavaEE(Java8), JSF, Jax-rs, MySQL, Tomcat',
          role:
            '要求整理, 要件定義, 設計, デザイン(CSS), 実装, ' +
            'テスト, システム全体のUI, UX対応',
          performance:
            'プロトタイプ型開発提案, 開発環境構築全般, 画面デザイン・調整, 進捗管理',
          members: '3人(PM1, エンジニア2)'
        }
      ]
    }
  },
  components: {
    Header,
    Footer,
    SkillBar,
    PortfolioCard,
    Timeline,
    Resume
  }
}
</script>

<style scoped lang="scss">
.section-text {
  text-align: center;
}
</style>
