<template>
  <div id="11">
    <div class="intro">
      <h1 id="1" class="intro__text">Introducing the all-new iOS 14, iPadOS 14, and watchOS 7 and the entirely reimagined macOS
        Big Sur. Each massive update transforms the experience of using your favorite devices, giving you the power to
        do more of the things you love like never before.</h1>
      <h1 class="intro__text-ios">iOS</h1>
    </div>

    <div class="outer">
      <div class="device">
        <div class="phone"></div>
      </div>
      <div class="text">
        <h1>Redesigned widgets show more information on your home screen.</h1>

        <h1>The App Library automatically organizes apps.</h1>

        <h1>Messages makes important conversations easy to access.</h1>

        <h1 class="text__last">App Clips help you handle tasks faster.</h1>
      </div>
    </div>

    <!--   Social Connections -->
    <div class="social-icons">
      <a class="social-icon social-icon--codepen" href="https://codepen.io/braydoncoyer" target="_blank">
        <i class="fa fa-codepen"></i>
        <div class="tooltip">Codepen</div>
      </a>
      <a class="social-icon social-icon--twitter" href="https://twitter.com/BraydonCoyer" target="_blank">
        <i class="fa fa-twitter"></i>
        <div class="tooltip">Twitter</div>
      </a>
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
    startAnimation() {
      this.$gsap.registerPlugin(ScrollTrigger);
      const textTitles = [...document.querySelectorAll("h1")];

      console.log(textTitles);

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
    }

  }
}
</script>
<style scoped>
@import '~/assets/scss/main.css';
</style>
