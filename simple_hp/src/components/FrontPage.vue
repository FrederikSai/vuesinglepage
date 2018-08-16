<template lang="pug">
  div.main
    v-app(dark)
      v-toolbar
        v-toolbar-title(v-text="company_name")
        v-spacer
        v-toolbar-items.hidden-sm-and-down
          v-btn(flat) Home
          v-btn(flat v-scroll-to="'#about'") About
          v-btn(flat v-scroll-to="'#contact'") Contact
      v-content
        section
          v-parallax(:src="require('@/assets/4.jpg')" height="600")
            v-layout.white--text(column align-center justify-center)
              img(:src="require('@/assets/ylogo.png')" alt="ylogo.js" height="200")
              h1.red--text.mb-2.display-1.text-xs-center(v-text="company_name")
              div.subheading.black--text.mb-3.text-xs-center 輸入・輸出を届ける
        
        section
          v-layout.my-5(column wrap align-center)
            v-card-text.elevation-0.transparent
              div.text-xs-center
                 h2.headline.red--text 社長の挨拶
                 div.white--text(margin-top="100px" v-text="intro")

        section
          v-parallax(:src="require('@/assets/meeting1.jpg')" height="380")
            v-layout(column align-center justify-center)
              div.headline.pink--text.text-lg-center
        
        //-  輸出
        section#about
          v-layout.my-12(column wrap align-center)
            v-flex.my-3(xs12 sm4)
              div.text-xs-center
                h2.headline.blue--text 輸出
            v-flex(xs12)
              v-container(grid-list-xl)
                v-layout(row wrap align-center)
                  v-flex(xs12 md5)
                    v-card.elevation-0.transparent
                      v-card-text 
                        img(:src="require('@/assets/8.jpg')" height="150" width="150" alt="2.jpg")
                  v-flex(xs12 md5)
                    v-card.elevation-0.transparent
                      v-card-text
                        | 当社は、世界でブランドとして人気の高い日本車を幅広く提供しております。世界の人口増加と経済発展に合わせて、自動車の需要が拡大していくと考えられます。
                        | 弊社は常にサービスを提供しようと努めております。私たちは、自動車の購入から船積みまで、世界各国に車を渡すために必要なすべての工程を行っております

        section
          v-parallax(:src="require('@/assets/ship.jpg')" height="380")
            v-layout(column align-center justify-center)
              div.headline.pink--text.text-lg-center
        
        //-   輸入
        section
          v-layout.my-12(column wrap align-center)
            v-flex.my-3(xs12 sm4)
              div.text-xs-center
                h2.headline.blue--text 輸入
            v-flex(xs12)
              v-container(grid-list-xl)
                v-layout(row wrap align-center)
                  v-flex(xs12 md5)
                      v-card.elevation-0.transparent
                        v-card-text 当社は鐵鋼原料、化学工業製品、包装資材の輸出入貿易事業ならびに国内取引を展開する専門商社です。グローバル化する社会に柔軟に対応し、お客様のニーズにお応えする為に現地でのきめ細かな情報収集や調査を行い、より良い原料や製品の調達を行っております。これからも安定供給、デリバリーの迅速化に努めて参ります。
                  v-flex(xs12 md5)
                    v-card.elevation-0.transparent
                      v-card-text 
                        img(:src="require('@/assets/8.jpg')" height="150" width="150" alt="2.jpg")
                  
        section
          v-parallax(:src="require('@/assets/car1.jpg')" height="380")
            v-layout(column align-center justify-center)
              div.headline.pink--text.text-lg-center   
        
        section
          v-container(grid-list-xl)
            v-layout.my-5(row wrap justify-center)
              v-flex(xs12 md5)
                v-card.elevation-0.transparent
                  v-card-title.layout.justify-center(primary-title)
                    div.headline#contact Company info
                  v-list.transparent

                    //- 商号
                    v-list-tile
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 business
                      v-list-tile-content
                        v-list-tile-title {{ company_name }}
                    //- 代表者
                    v-list-tile
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 face
                      v-list-tile-content
                        v-list-tile-title 代表取締役　WAI MYO THANT
                    //- 場所
                    v-list-tile  
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 place
                      v-list-tile-content
                        v-list-tile-title 埼玉県越谷市下間久里1148-1
                        v-list-tile-title 越谷スカイハイツ B 6F  
                    //- 設立
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 public
                      v-list-tile-content
                        v-list-tile-title 平成28年8月24日                  
                    //- 資本金
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 attach_money
                      v-list-tile-content
                        v-list-tile-title 500万円 
                    //- 電話
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 phone
                      v-list-tile-content
                        v-list-tile-title Tel. 0489-16-6936
                        v-list-tile-title Fax. 0489-16-6936
                    //- 事業内容
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 business_center
                      v-list-tile-content
                        v-list-tile-title 中古車輸出販売
                    //- 輸出地域
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 flight
                      v-list-tile-content
                        v-list-tile-title 中南米、ロシア及びCIS諸国
                        v-list-tile-title アフリカ、モンゴル、ミャンマー
                    //- 従業員数
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 people
                      v-list-tile-content
                        v-list-tile-title 2名
                    //- 取引銀行
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 account_balance
                      v-list-tile-content
                        v-list-tile-title みずほ銀行、ゆうちょ銀行、りそな銀行    

      v-footer(dark height="auto")
        v-card.lighten-1.white--text.text-xs-center.flex(flat tile)
          v-card-title
            strong.subheading 
              //- button.btn(type="button" @click="showModal") Privacy
              v-layout(row justify-center)
                v-dialog(v-model='dialog' width='600px')
                  v-btn(slot='activator' color='primary' dark) Privacy
                  v-card.text-lg-left
                    v-card-title
                      span.headline ライバシーポリシー
                    v-card-text
                        | 株式会社Y（以下、「当社」といいます。）は、以下のとおりプライバシーポリシー（以下「本ポリシー」といいます。）を定めます。
                    v-card-text
                        span.subheading
                          | ①プライバシー管理 
                        v-card-text
                          | 当社では、お客様の個人情報を正確かつ最新の状態に保ち、個人情報への不正アクセス・紛失・破損・改ざん・漏洩などを防止するため、セキュリティシステムの維持・管理体制の整備・社員教育の徹底等の必要な措置を講じ、安全対策を実施し個人情報の厳重な管理を行ないます。
                        span.subheading 
                          | ②プライバシー情報の利用目的
                        v-card-text
                          | 当社では、お客様からお預かりした個人情報を、次の業務を実施する目的で利用します。
                          | （１）サービスのご案内
                          | （２）業務の利用目的達成
                          | （３）お客様からの問い合わせ・依頼等へのご対応
                        span.subheading 
                          | ③プライバシー情報の第三者への提供について
                        v-card-text
                          | 当社では、次の場合を除いて、お客様の同意を得ることなく個人情報を第三者に開示いたしません。 
                          | （１）法令に基づく場合
                          | （２）お客様の同意がある場合
                          | （３）お客様が希望されるサービスを行なうために当社が業務を委託先に開示する場合 
                          | （４）人の生命、身体又は財産（法人の財産を含む。）の保護のために必要な場合であって、ご本人の同意を得ることが困難な場合
                        span.subheading 
                          | ④ プライバシー情報の安全対策
                        v-card-text
                          | 当社は、個人情報の正確性及び安全性確保のため、セキュリティに万全の対策を講じています。
                        span.subheading 
                          | ⑤ご本人の照会
                        v-card-text
                          | お客様は、当社の保有するご本人の個人情報の訂正または削除を請求することができます。
                        span.subheading 
                          | ⑥プライバシーポリシーの見直し
                        v-card-text
                          | 当社では、日本の法令等に基づき、お客様の個人情報をより良くするため、本ポリシーの見直し、改定をすることがあります。
                        span.subheading 
                         | ⑦問い合わせ窓口
                        v-card-text
                          | 本ポリシーに関するお問い合わせ・ご相談は、お問い合わせフォームからお願いします。
                    v-card-actions
                      v-spacer
                      v-btn(color='green darken-1' flat='flat' @click='dialog = false') Close
            v-spacer
            v-btn.mx-3.white--text(v-for="icon in icons" :key="icon" icon)
              v-icon(size="24px") {{ icon }}
          
          v-card-text.white--text.justify-center
            .copy &copy; 2018 {{ title }}. All Rights Reserved.
</template>

<script>

export default {
  name: 'FrontPage',
  data () {
    return {
      dialog: false,
      msg: 'よこそY株式会社',
      company_name: '株式会社Y',
      intro: 'まず、事業部長は部内での「長」であり、責任者である、ということです。部内での指揮をとるのも事業部長なので、この部ではどのようなことをしていくのか、何のためにこの作業をするのかなど、自分の所属する事業部の役割をしっかりと理解した上で、未来設計を立てていく必要があります。それはもちろん一人で考える場合もありますが、もしいい案が思い浮かばない場合には部内の部下に聞いたりして決めていくこともあるようです。部内会議などでは最終決定権を持っているのも事業部長ななので、しっかりとした決断力や判断力も求められます。',
      icons: [
        'fab fa-facebook',
        'fab fa-twitter',
        'fab fa-google-plus',
        'fab fa-linkedin',
        'fab fa-instagram'
      ]
    }
  }
}
</script>


<style scoped>
</style>
