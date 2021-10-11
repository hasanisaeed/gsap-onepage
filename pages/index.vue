<template>
  <div >
    <div class="intro">
      <h4  class="intro__text">
        در شهریور 96، جمعی از نخبگان کارآفرینی، فناوری و لجستیک گرد هم آمدند و برای حل چالش های حمل و نقل جاده ای کالای کشور، ایده دانش بنیان سامانه هوشمند حمل بار را در قامت باروان پدید آوردند تا صاحبان کالا دغدغه حمل نداشته، رانندگان کامیون همواره به بار دسترسی داشته و بهره وری و خدمات شرکت های حمل و نقلی توسعه پیدا کند.

        خاطر آسوده صاحب کالا، لبخند رضایت راننده و اعتماد شرکت حمل و نقلی ارزش های ماست. می کوشیم با تحقیق و توسعه در کنار تجربیات سازنده کیفیت خدمات باروان را بالا برده و چشم اندازی روشن و با ارزش برای صنعت حمل و نقل کالای کشور بسازیم و آن را در تراز جهانی ارائه کنیم.

      </h4>
      <h4 class="intro__text-ios">کاروان</h4>
    </div>

    <div class="outer">
      <div class="device">
        <div class="phone"></div>
      </div>
      <div class="text">
        <h1>
          رانندگان عزیز با پیوستن به سامانه هوشمند باروان، به بزرگترین سالن اعلام بار مجازی کشور دسترسی پیدا کنید، هزینه ها را کاهش و درآمد خود را بالا ببرید:
        </h1>

        <h1>
          استعلام خلافی کامیون، عوارض جاده ای، حواله دولتی لاستیک کامیون و …
        </h1>

        <h1>
          باروان چیست؟
          سامانه هوشمند حمل بار
          باروان یک سامانه اعلام بار و حمل بار است. در این سامانه صاحب کالا به راحتی اعلام بار کرده و بار خود را در معرض دید و انتخاب هزاران راننده کامیون از سراسر کشور قرار می دهد
        </h1>

        <h1 class="text__last">اپلیکیشن رانندگان باروان را از اینجا دانلـود و به سادگی ثبت نام کنید!</h1>
      </div>
    </div>

<div class="team">

  <div class="on" style="background: green">
    TEST
    <h1 style="color: black;">    TEST   TEST   TEST   TEST   TEST   TEST   TEST   TEST  TEST</h1>
  </div>
  <div class="on" style="background: red">
    TEST
    <h1 style="color: black;">    TEST   TEST   TEST   TEST   TEST   TEST   TEST   TEST  TEST</h1>
  </div>
  <div class="on" style="background: yellowgreen">
    TEST
    <h1 style="color: black;">    TEST   TEST   TEST   TEST   TEST   TEST   TEST   TEST  TEST</h1>
  </div>
  <div class="on" style="background: darkmagenta">
    TEST
    <h1 style="color: black;">    TEST   TEST   TEST   TEST   TEST   TEST   TEST   TEST  TEST</h1>
  </div>

</div>
  </div>
</template>

<script>
import {ScrollTrigger} from 'gsap/ScrollTrigger'

export default {
  mounted() {
    this.startAnimation()
  },
  methods: {
    animate(boxEls) {

      console.log('>>>>>>>>>>')
      let tl = this.$gsap.timeline({
        scrollTrigger: {
          id: "box",
          trigger: ".team",
          toggleActions: "play pause resume pause",
          start: "10%",
          end: "50%",
          markers: true,
          scrub: 0.25
        }
      });
      tl.from(boxEls, {
        opacity: 0,
        marginLeft: 0,
        transform: "scale(1.5)",
        stagger: 0.5
      });
    },
    initEls() {
      return document.querySelectorAll(".on");
    },
    init() {
      this.animate(this.initEls());
    },
    startAnimation() {
      this.$gsap.registerPlugin(ScrollTrigger);
      const textTitles = [...document.querySelectorAll("h1")];
      console.log(textTitles)
      this.$gsap.timeline({
        scrollTrigger: {
          trigger: ".phone",
          start: "center center",
          end: "center 60%",
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
            start: "top 55%",
            end: "top 10%",
            scrub: true,
            toggleClass: {
              targets: ".phone",
              className: `phone${i - 1}`
            }
          }
        });
      });

      let tl2 = this.$gsap.timeline({
        scrollTrigger: {
          trigger: ".team",
          toggleActions: "play pause resume pause",
          scrub: 0.25
        }
      });

      const boxEls =  document.querySelectorAll("on") ;
      tl2.from(boxEls, {
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
@import '~/assets/style/main.css';
@import '~/assets/style/team.css';
</style>
