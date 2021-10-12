<template>
  <div>
    <div class="intro">
      <h4 class="intro__text">
        در شهریور 96، جمعی از نخبگان کارآفرینی، فناوری و لجستیک گرد هم آمدند و برای حل چالش های حمل و نقل جاده ای کالای
        کشور، ایده دانش بنیان سامانه هوشمند حمل بار را در قامت باروان پدید آوردند تا صاحبان کالا دغدغه حمل نداشته،
        رانندگان کامیون همواره به بار دسترسی داشته و بهره وری و خدمات شرکت های حمل و نقلی توسعه پیدا کند.

        خاطر آسوده صاحب کالا، لبخند رضایت راننده و اعتماد شرکت حمل و نقلی ارزش های ماست. می کوشیم با تحقیق و توسعه در
        کنار تجربیات سازنده کیفیت خدمات باروان را بالا برده و چشم اندازی روشن و با ارزش برای صنعت حمل و نقل کالای کشور
        بسازیم و آن را در تراز جهانی ارائه کنیم.

      </h4>
      <h4 class="intro__text-ios">کاروان</h4>
    </div>

    <div class="outer">
      <div class="device">
        <div class="phone"></div>
      </div>
      <div class="text">
        <h1>
          رانندگان عزیز با پیوستن به سامانه هوشمند باروان، به بزرگترین سالن اعلام بار مجازی کشور دسترسی پیدا کنید، هزینه
          ها را کاهش و درآمد خود را بالا ببرید:
        </h1>

        <!--        <h1>-->
        <!--          استعلام خلافی کامیون، عوارض جاده ای، حواله دولتی لاستیک کامیون و …-->
        <!--        </h1>-->

        <!--        <h1>-->
        <!--          باروان چیست؟-->
        <!--          سامانه هوشمند حمل بار-->
        <!--          باروان یک سامانه اعلام بار و حمل بار است. در این سامانه صاحب کالا به راحتی اعلام بار کرده و بار خود را در معرض-->
        <!--          دید و انتخاب هزاران راننده کامیون از سراسر کشور قرار می دهد-->
        <!--        </h1>-->

        <h1 class="text__last">اپلیکیشن رانندگان باروان را از اینجا دانلـود و به سادگی ثبت نام کنید!</h1>
      </div>
    </div>

    <section class="mobile">
      <div class="hardware"></div>
      <div class="screen">
        <div class="image-top"></div>
        <ul class="downloads">
          <li class="download">
            <div class="download-show"></div>
          </li>
          <li class="download on on-1"></li>
          <li class="download on on-2"></li>
          <li class="download on on-3"></li>
        </ul>
      </div>
    </section>
    <!--    <div id="main">-->
    <!--      <section class="container">-->
    <!--        <section class="elements">-->
    <!--          <div class="box a">A</div>-->
    <!--          <div class="box b">B</div>-->
    <!--          <div class="box c">C</div>-->
    <!--        </section>-->
    <!--        <section class="text hidden">-->
    <!--          <div class="t">Paragraph 1</div>-->
    <!--          <div class="t">Paragraph 2</div>-->
    <!--          <div class="t">Paragraph 3</div>-->
    <!--          <div class="t">Paragraph 4</div>-->
    <!--        </section>-->
    <!--      </section>-->
    <!--    </div>-->


    <!--    <div class="team">-->
    <!--      <div class="on" style="background: green;height:150px;">-->
    <!--        TEST-->
    <!--        <h1 style="color: black;"> TEST TEST TEST TEST TEST TEST TEST TEST TEST</h1>-->
    <!--      </div>-->
    <!--      <div class="on" style="background: red;height:150px;">-->
    <!--        TEST-->
    <!--        <h1 style="color: black;"> TEST TEST TEST TEST TEST TEST TEST TEST TEST</h1>-->
    <!--      </div>-->
    <!--      <div class="on" style="background: yellowgreen;height:150px;">-->
    <!--        TEST-->
    <!--        <h1 style="color: black;"> TEST TEST TEST TEST TEST TEST TEST TEST TEST</h1>-->
    <!--      </div>-->
    <!--      <div class="on" style="background: darkmagenta;height:150px;">-->
    <!--        TEST-->
    <!--        <h1 style="color: black;"> TEST TEST TEST TEST TEST TEST TEST TEST TEST</h1>-->
    <!--      </div>-->
    <!--    </div>-->
  </div>
</template>

<script>
import {ScrollTrigger} from 'gsap/ScrollTrigger'

export default {
  mounted() {
    this.startAnimation()
    // this.scrollStart()
  },
  methods: {
    scrollStart() {
      this.$gsap.registerPlugin(ScrollTrigger);

      let tl = this.$gsap.timeline({
        scrollTrigger: {
          id: 'box',
          trigger: '.elements',
          toggleActions: 'play pause resume pause',
          start: 'top top',
          end: 'bottom top',
          scrub: 0.25,
          pin: true
        }
      });

      let tl2 = this.$gsap.timeline({
        scrollTrigger: {
          id: 'text',
          trigger: '.text',
          start: 'top 80%',
          end: 'bottom 80%',
          markers: true,
          scrub: 0.25
        }
      });

      var boxEls, textEls;

      boxEls = document.querySelectorAll('.box');
      textEls = document.querySelectorAll('.t');

      tl.from(boxEls, {
        opacity: 0,
        stagger: 0.5
      });

      tl2.from(textEls, {
        opacity: 0,
        stagger: 0.5
      });
    },

    /*********************************/

    startAnimation() {
      this.$gsap.registerPlugin(ScrollTrigger);

      const textTitles = [...document.querySelectorAll("h1")];

      this.$gsap.timeline({
        scrollTrigger: {
          trigger: ".phone",
          start: "center center",
          // end: "center 60%",
          endTrigger: ".text__last",
          pinSpacing: true,
          pin: true
        }
      });
      textTitles.forEach((title, i) => {
        this.$gsap.to(title, {
          opacity: 1,
          scrollTrigger: {
            trigger: title,
            // start: "top 55%",
            // end: "top 10%",
            scrub: true,
            toggleClass: {
              targets: ".phone",
              className: `phone${i - 1}`
            }
          }
        });
      });





      var boxEls = document.querySelectorAll(".on");


      let tl = this.$gsap.timeline({
        scrollTrigger: {
          id: "box",
          trigger: ".mobile",
          toggleActions: "play puase resume pause",
          start: "20%",
          end: "60%",
          // markers: true,
          scrub: 0.25
        }
      });

      tl.from(boxEls, {
        opacity: 0,
        marginLeft: 0,
        transform: "scale(1.5)",
        stagger: 0.5
      });

    }

  }
}
</script>
<style scoped>
@import 'assets/style/main.css';
/*@import '~/assets/style/team.css';*/

#main {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100%;
}

.void {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh;
  font-size: 20px;
  background: #333;
}

.container {
  position: relative;
  width: 100%;
  /*   height: calc(100vh + 500px); */
  background: #222;
}

.elements, .text {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-around;
  width: 100%;
}

.elements {
  height: 100vh;
  background: #f96723;
}

.text {
  bottom: 0;
  height: 500px;
  background: #dc4a06;
  border-top: 1px dotted red;
}

.box {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100px;
  height: 100px;
  background: #112f1d;
}

.our-team {
  width: 100%;
  background: yellowgreen;
  margin-top: 50px;
  text-align: center;
}

.mobile {
  width: 770px;
  height: 1336px;
  margin: auto;
  margin-top: 400px;
  margin-bottom: -367px;
  position: relative;
}

.mobile .hardware {
  width: 770px;
  height: 1336px;
  background-size: 770px 1336px;
  background-repeat: no-repeat;
  background-image: url(https://www.apple.com/v/iphone-12-pro/f/images/overview/5g/5g_on_phone__qxgc670fz2aa_large.jpg);
}

.mobile .screen {
  width: 770px;
  height: 1336px;
  display: block;
  box-sizing: border-box;
  padding: 80px 20px 20px 20px;
  position: absolute;
  top: 0;
}

.mobile .screen .image-top {
  width: 650px;
  height: 200px;
  background-size: 650px 200px;
  background-repeat: no-repeat;
  background-image: url(https://www.apple.com/v/iphone-12-pro/f/images/overview/5g/5g_top_ui__fh2pbo18aviq_large.jpg);
  position: relative;
  z-index: 3;
  margin: auto;
}

.mobile .screen .downloads {
  list-style: none;
  margin: auto;
  z-index: 33;
  margin-top: 20px;
  padding-left: 0;
}

.mobile .screen .downloads .download {
  width: 100%;
  height: 200px;
  margin-bottom: 20px;
}

.mobile .screen .downloads .download-show {
  width: 730px;
  height: 200px;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url(https://www.apple.com/v/iphone-12-pro/f/images/overview/5g/5g_show_04__dbzl203ndh2e_large.jpg);
}

.mobile .screen .downloads .on {
  opacity: 1;
  width: 100%;
  transform: scale(1);
}

.mobile .screen .downloads .on-1 {
  width: 730px;
  height: 200px;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url(https://www.apple.com/v/iphone-12-pro/f/images/overview/5g/5g_show_01__bf4l35s1jn1e_large.jpg);
}

.mobile .screen .downloads .on-2 {
  width: 730px;
  height: 200px;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url(https://www.apple.com/v/iphone-12-pro/f/images/overview/5g/5g_show_02__f7pxk2oyioeq_large.jpg);
}

.mobile .screen .downloads .on-3 {
  width: 730px;
  height: 200px;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url(https://www.apple.com/v/iphone-12-pro/f/images/overview/5g/5g_show_03__c8qgtrgvtno2_large.jpg);
}
</style>
