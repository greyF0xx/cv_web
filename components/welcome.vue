<template>
  <header id="Index" class="mainArticle">
    <div class="homePicContainer">
      <svg v-html="picBg" id="picBg" class="picBg"></svg>
      <!-- <img src="~/assets/avatar2.png" id="homePic" class="homePic" /> -->
      <h2 id="homePic" class="heroTitle">Massine <br />Mountasser</h2>
    </div>
    <div class="welcome">
      <p class="homeTitle animate-text-1">IT engineer - Project Manager</p>
      <p class="homeSubTitle animate-text-2">
        Full stack developer, 25 years old
      </p>
    </div>
    <p class="homeText" id="homeText">
      Hi there! Take a dive into my journey..<br />Here you can explore some of
      my projects and get to know me better. <br />I do web dev, recently
      graduated in IT engineering. <br />Feel free to browse this page and
      you'll find my resume all the way down. <br />Don't hesitate to reach out
      if you have any ideas or collaborations in mind. <br />Thank you for
      visiting!
    </p>
    <arrows id="arrows" />
  </header>
</template>

<script>
export default {
  data: function () {
    return {
      picBg:
        '<svg xmlns="http://www.w3.org/2000/svg" data-name="Layer 2" viewBox="0 0 553 553"><defs><linearGradient id="a" x1="80.98" x2="472.02" y1="80.98" y2="472.02" gradientUnits="userSpaceOnUse"><stop offset="0" stop-color="#103a69"/><stop offset="1" stop-color="#042245"/></linearGradient></defs><circle cx="276.5" cy="276.5" r="276.5" fill="url(#a)" data-name="Layer 1"/></svg>',
    };
  },
  methods: {
    animateText(id, delay, delay_start) {
      let contents, letters;
      document.querySelectorAll(".animate-text-" + id).forEach(function (elem) {
        contents = elem.textContent.trim();
        elem.textContent = "";
        letters = contents.split("");
        elem.style.visibility = "visible";
        letters.forEach(function (letter, index_1) {
          setTimeout(function () {
            elem.textContent += letter;
          }, delay_start + delay * index_1);
        });
        delay_start += delay * letters.length;
      });
    },
  },
  mounted: function () {
    this.animateText(1, 100, 1000);
    this.animateText(2, 80, 1000);
    setTimeout(function () {
      document.getElementById("picBg").style.transform = "scale(1)";
      document.getElementById("picBg").style.opacity = 1;
    }, 2000);
    setTimeout(function () {
      document.getElementById("homePic").style.opacity = 1;
    }, 3000);
    setTimeout(function () {
      document.getElementById("homeText").style.opacity = 1;
    }, 2000);
    setTimeout(function () {
      document.getElementById("arrows").style.opacity = 1;
    }, 5000);
  },
};
</script>
<style>
.animate-text {
  visibility: hidden;
}
#arrows,
#homeText,
#homePic {
  opacity: 0;
  transition: all 1s ease-in-out;
}
#picBg {
  opacity: 0;
  transform: scale(0);
  transition: all 1s ease-in-out;
}
</style>
