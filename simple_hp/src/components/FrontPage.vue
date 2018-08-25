<template lang="pug">
  div#frontpage.main
    v-app(dark)
      v-toolbar(fixed)
        img(:src="require('@/assets/ylogo.png')" alt="ylogo" height="70")
        v-toolbar-title(v-text="company_name")
        v-spacer
        v-toolbar-items.hidden-sm-and-down
          v-btn(flat v-scroll-to="'#home'") ホーム
            br 
            | Home
          v-btn(flat v-scroll-to="'#about'") 事業内容
            br 
            | About
          v-btn(flat v-scroll-to="'#company_info'") 会社概要
            br
            | Company Info
          //- v-btn(flat slot='activator' dark) Contact
          v-layout
            v-dialog(v-model='contact_dialog' persistent max-width='500px')
              v-btn.contact(flat slot='activator' dark style="height: 65px") お問い合わせ
                br
                | Contact
              v-card
                v-card-title
                  span.headline お問い合わせ
                v-card-text
                  v-container(grid-list-md)
                    v-layout(wrap)
                      v-flex(xs12)
                        v-text-field(label='*名前' required hint='お名前を入力してください')
                      v-flex(xs12)
                        v-text-field(label='*Email' required hint='Emailを入力してください')
                      v-flex(xs12)
                        v-text-field(label='*電話' hint='ご連絡先電話番号を入力してください')
                      v-flex(xs12)
                        v-textarea(label='*お問い合わせ内容' required hint='お問い合わせ内容を入力してください')
                      //- v-flex(xs12)
                        //- v-textarea(label='Password' type='password' required)
                      //- small *indicates required field
                      small *は必須入力項目です。
                v-card-actions
                  v-spacer
                  v-btn(color='blue darken-1' flat @click.native='contact_dialog = false') Close
                  v-btn(color='blue darken-1' flat @click.native='contact_dialog = false') Send

      v-content
        section#home
          v-parallax(:src="require('@/assets/top.jpg')" height="600")
            v-layout.white--text(column align-center justify-center)
              img(:src="require('@/assets/ylogo.png')" alt="ylogo" height="200")
              h1.red--text.mb-2.display-3.text-xs-center(v-text="company_name")
              div.display-1.black--text.mb-3.text-xs-center(v-text='slogan')
        
        section
          v-jumbotron(:gradient="gradient" dark :src="require('@/assets/material2.jpg')")
            v-container(fill-height)
              v-layout(align-center)
                v-flex(text-xs-center)
                  h3.display-3 事業内容
                  div.white--text(margin-top="100px" v-text="com_export")
        //- section
        //-   v-layout.my-5(column wrap align-center)
        //-     v-card-text.elevation-0.transparent
        //-       div.text-xs-center
        //-          h2.headline.red--text 事業内容
        //-          div.white--text(margin-top="100px" v-text="com_export")
        section#about
          v-parallax(:src="require('@/assets/ship.jpg')" height="380")
            v-layout(column align-center justify-center)
              div.headline.pink--text.text-lg-center
        
        //-  中号車
        section
          v-layout.my-12(column wrap align-center)
            v-flex.my-3(xs12 sm4)
              div.text-xs-center
                h2.headline.blue--text(v-text='used_car_business')
            v-flex(xs12)
              v-container(grid-list-xl)
                v-layout(row wrap align-center)
                  v-flex(xs12 md5)
                    v-card.elevation-0.transparent
                      v-card-text 
                        img(:src="require('@/assets/car_lot.jpg')" height="150" width="150" alt="2.jpg")
                  v-flex(xs12 md5)
                    v-card.elevation-0.transparent
                      v-card-text(v-text="used_car")

        section
          v-parallax(:src="require('@/assets/meeting.jpg')" height="380")
            v-layout(column align-center justify-center)
              div.headline.pink--text.text-lg-center

        section
          v-layout.my-5(column wrap align-center)
            v-card-text.elevation-0.transparent
              div.text-xs-center
                h2.display-1.blue--text(v-text='our_system')
                img(:src="require('@/assets/business_content.png')" width="70%" alt="business_content")

        section
          v-parallax(:src="require('@/assets/car.jpg')" height="380")
            v-layout(column align-center justify-center)
              div.headline.pink--text.text-lg-center   
        
        sections
          v-container(grid-list-xl)
            v-layout.my-5(row wrap justify-center)
              v-flex(sm10 md5)
                v-card.elevation-0.transparent
                  v-card-title.layout.justify-center(primary-title)
                    div#company_info.display-1 会社概要
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
                        v-list-tile-title Director WAI MYO THANT
                        v-list-tile-title 代表取締役 ワイ ミョー タン
                    //- 設立
                    v-list-tile 
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 public
                      v-list-tile-content
                        v-list-tile-title 平成29年8月24日                  
                    //- 場所
                    v-list-tile  
                      v-list-tile-action
                        v-icon.blue--text.text--lighten-2 place
                      v-list-tile-content
                        a(href="https://goo.gl/maps/SUS2BBccrY32")
                          v-list-tile-title 埼玉県越谷市下間久里1148-1
                          v-list-tile-title 越谷スカイハイツ B 6F  
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
                        v-list-tile-title ゆうちょ銀行
                        v-list-tile-title みずほ銀行、りそな銀行

        section.map
          iframe(src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3231.144822960657!2d139.77767671540133!3d35.91895502450469!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x6018bdfb0131a13d%3A0x9b31d86a3cf50b89!2z44CSMzQzLTAwNDUgU2FpdGFtYS1rZW4sIEtvc2hpZ2F5YS1zaGksIFNoaW1vbWFrdXJpLCAxMTQ4LTEg6LaK6LC344K544Kr44Kk44OP44Kk44OE77yi!5e0!3m2!1sen!2sjp!4v1534565889300" width="100%" height="450" frameborder="0" style="border:0" allowfullscreen)
        

      v-footer(dark height="auto")
        v-card.lighten-1.white--text.text-xs-center.flex(flat tile)
          v-card-title
            strong.subheading 
              //- button.btn(type="button" @click="showModal") Privacy
              v-layout(row justify-center)
                v-dialog(v-model='privacy_dialog' width='600px')
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
                      v-btn(color='green darken-1' flat='flat' @click='privacy_dialog = false') Close
            v-spacer
            v-btn.mx-3.white--text(v-for="icon in icons" :key="icon" icon)
              v-icon(size="24px") {{ icon }}
  
          
          v-card-text.white--text.justify-center
            .copy &copy; 2018 {{ title }}. All Rights Reserved.
</template>

<script>
// import CompanyInfo from './CompanyInfo'
// import Privacy from './Privacy'
// import MyMap from './MyMap.vue'


export default {
  name: 'FrontPage',
  // component: {
  //   // CompanyInfo,
  //   // Privacy,
  // },
  data () {
    return {
      privacy_dialog: false,
      contact_dialog: false,
      msg: 'よこそ株式会社 Y',
      company_name: '株式会社 Y',
      slogan: '世界中に車を届ける',
      our_system: 'Our System',
      used_car_business: '中古車輸出事業',
      intro: 'まず、事業部長は部内での「長」であり、責任者である、ということです。部内での指揮をとるのも事業部長なので、この部ではどのようなことをしていくのか、何のためにこの作業をするのかなど、自分の所属する事業部の役割をしっかりと理解した上で、未来設計を立てていく必要があります。それはもちろん一人で考える場合もありますが、もしいい案が思い浮かばない場合には部内の部下に聞いたりして決めていくこともあるようです。部内会議などでは最終決定権を持っているのも事業部長ななので、しっかりとした決断力や判断力も求められます。',
      com_export: '当社は、世界でブランドとして人気の高い日本車を幅広く提供しております。世界の人口増加と経済発展に合わせて、自動車の需要が拡大していくと考えられます。弊社は常にサービスを提供しようと努めております。私たちは、自動車の購入から船積みまで、世界各国に車を渡すために必要なすべての工程を行っております。',
      used_car: '当社では、ミャンマー、モンゴルへ日本の中古車を輸出しております。 経済成長の著しいミャンマー、モンゴルなどの新興国において、特に人気のあるミニバンやSUVを中心に輸出しています。 世界経済において、アジアなどの新興国が重要な役割を果たすようになる日も遠くありません。こうした国々では、自動車販売マーケットもますます拡大していくことでしょう。この大きな流れに乗り、私たちもさらなる成長を遂げていきたいと考えております。 ',
      gradient: 'to top right, rgba(63,81,181, .7), rgba(25,32,72, .7)',
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
  .contact {
    height: 65px
  }
  .map {
    margin: 20px
  }
</style>
