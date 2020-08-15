<template>
  <Layout>
    <div class="about-me">
      <p><span class="text">My hobbies</span> </p>
      <div id="sliderOne" class="slider">
        <ul id="slide-wrap">
          <li v-for="(slide, index) in sliderOne" :key="index" class="slide" :style="transform1">
            <div class="content">
              <img :src="slide.img" alt="">
              <p class="slide-text">{{slide.text}}</p>
            </div>
          </li>
        </ul>
        <a class="prev" @click="prevSlide1(sliderOne)">&#10094;</a>
        <a class="next" @click="nextSlide1(sliderOne)">&#10095;</a>
      </div>
      <p><span class="text">Where I worked</span> </p>
      <div id="sliderTwo" class="slider">
        <ul id="slide-wrap">
          <li v-for="(slide, index) in sliderTwo" :key="index" class="slide" :style="transform2">
            <div class="content">
              <img :src="slide.img" alt="">
              <p class="slide-text">{{slide.text}}</p>
            </div>
          </li>
        </ul>
        <a class="prev" @click="prevSlide2(sliderTwo)">&#10094;</a>
        <a class="next" @click="nextSlide2(sliderTwo)">&#10095;</a>
      </div>
      <p><span class="text">My projects</span> </p>
      <div id="sliderThree" class="slider">
        <ul id="slide-wrap">
          <li v-for="(slide, index) in sliderThree" :key="index" class="slide" :style="transform3">
            <div class="content">
              <img :src="slide.img" alt="">
              <p class="slide-text"><a :href="slide.href">{{slide.text}}</a> </p>
            </div>
          </li>
        </ul>
        <a class="prev" @click="prevSlide3(sliderThree)">&#10094;</a>
        <a class="next" @click="nextSlide3(sliderThree)">&#10095;</a>
      </div>
    </div>
  </Layout>
</template>

<script>
  export default {
    metaInfo: {
      title: 'About me'
    },
    mounted() {
      const thiss = this;
      this.sliderWidth = document.getElementById('sliderOne').offsetWidth;
      // this.sliderWidth = document.getElementById('slider').offsetWidth;
      // this.sliderWidth = document.getElementById('slider').offsetWidth;
      this.sliderList = document.getElementById('slide-wrap');
      this.slider = document.getElementById('slider');
      this.slide = document.querySelectorAll('.slide');
      window.addEventListener('resize', () => {
        this.sliderWidth = document.getElementById('slider').offsetWidth;
      });
    },
    data() {
      return {
        slider: '',
        sliderList: '',
        slide: null,
        count1: 0,
        count2: 0,
        count3: 0,
        sliderWidth: 0,
        sliderOne: [
          {
            img: require('../../static/longboard1.jpg'),
            text: 'Longboarding'
          },
          {
            img: require('../../static/snowboarding.jpg'),
            text: 'Snowboarding'
          },
          {
            img: require('../../static/swimming.png'),
            text: 'Swimming'
          },
          {
            img: require('../../static/travelling.jpg'),
            text: 'Travelling'
          },
        ],
        sliderTwo: [
          {
            img: require('../../static/electric.jpg'),
            text: 'Electric Castle'
          },
          {
            img: require('../../static/snowfest.jpg'),
            text: 'Snow Fest'
          },
          {
            img: require('../../static/untold.jpg'),
            text: 'Untold'
          },
          {
            img: require('../../static/rock.jpg'),
            text: 'Rockstadt Extreme Fest'
          },
        ],
        sliderThree: [
          {
            img: require('../../static/tic-tac-toe-project.jpg'),
            text: 'Tic Tac Toe',
            href: '../../../tic tac toe/index.html'
          },
          {
            img: require('../../static/rock-paper-scissors-project.jpg'),
            text: 'Rock Paper Scissors',
            href: '/rock-paper-scissors'
          },
          {
            img: require('../../static/clock-project.jpg'),
            text: 'Clock',
            href: '/clock'
          }
        ],
      };
    },
    computed: {
      transform1() {
        const amount = - this.count1 * this.sliderWidth;
        const transformArg = `translateX(${amount}px)`;
        return {transform: transformArg};
      },
      transform2() {
        const amount = - this.count2 * this.sliderWidth;
        const transformArg = `translateX(${amount}px)`;
        return {transform: transformArg};
      },
      transform3() {
        const amount = - this.count3 * this.sliderWidth;
        const transformArg = `translateX(${amount}px)`;
        return {transform: transformArg};
      }
    },
    methods: {
      items(slides) {
        return slides.length;
      },
      nextSlide1(slides) {
        if (this.count1 < (this.items(slides)-1)) {
          this.count1 = this.count1 + 1;
        } else {
          this.count1 = 0;
        }
      },
      prevSlide1(slides) {
        if (this.count1 > 0) {
          this.count1 = this.count1 - 1;
        } else {
          this.count1 = slides.length - 1;
        }
      },
      nextSlide2(slides) {
        if (this.count2 < (this.items(slides)-1)) {
          this.count2 = this.count2 + 1;
        } else {
          this.count2 = 0;
        }
      },
      prevSlide2(slides) {
        if (this.count2 > 0) {
          this.count2 = this.count2 - 1;
        } else {
          this.count2 = slides.length - 1;
        }
      },
      nextSlide3(slides) {
        if (this.count3 < (this.items(slides)-1)) {
          this.count3 = this.count3 + 1;
        } else {
          this.count3 = 0;
        }
      },
      prevSlide3(slides) {
        if (this.count3 > 0) {
          this.count3 = this.count3 - 1;
        } else {
          this.count3 = slides.length - 1;
        }
      }
    },
  }
</script>

<style scoped>
.text {
    background: gray;
    color: white;
    font-size: 34px;
    font-family: sans-serif;
    font-style: italic;
    padding: 10px 20px;
}

  @media (min-width: 1024px) {
    .about-me{
      max-width: 1018px;
      margin: auto;
    }
    .about-me {
      margin: 0 96px;
    }

    .text {
      font-size: 44px;
    }
  }

  @media (min-width: 1280px) {
    .about-me {
      max-width: 1228px;
    }
  }

  .prev, .next {
      cursor: pointer;
      position: absolute;
      top: 50%;
      width: auto;
      padding: 16px;
      margin-top: -45px;
      color: gray!important;
      font-weight: bold;
      font-size: 45px;
      transition: 0.6s ease;
      border-radius: 0 3px 3px 0;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
  }

  .next {
    right: 0;
    border-radius: 3px 0 0 3px;
  }

  .prev:hover, .next:hover {
    color: black!important
  }

  .slider {
    position: relative;
    width: 80vw;
    height: 450px;
    overflow: hidden;
    margin: 50px auto;
  }

  .slider img {
    height: 100%
  }

  .slide-text {
      position: absolute;
      background: rgba(0,0,0,0.5);
      padding: 0 10px;
      color: white;
      font-size: 30px;
      bottom: 0;
  }

  .slide-text a {
    color: white
  }
  

  .content {
    width: 80vw;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: black;
    font-size: 5em;
    font-family: sans-serif;
  }

  ul {
    position: relative;
    list-style: none;
    height: 100%;
    display: flex;
    flex-flow: row nowrap;
    margin: 0;
    padding: 0;
  }

  li {
    position: relative;
    height: 100%;
    width: 80vw;
  }
</style>


