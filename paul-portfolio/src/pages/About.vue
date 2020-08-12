<template>
  <Layout>
    <div class="about-me">
      <h1>About me</h1>
      <p></p>
      <div id="sliderOne" class="slider">
        <ul id="slide-wrap">
          <li v-for="(slide, index) in sliderOne" :key="index" class="slide" :style="transform">
            <div class="content">
              <img :src="slide.img" alt="">
              <p class="slide-text">{{slide.text}}</p>
            </div>
          </li>
        </ul>
        <a class="prev" @click="prevSlide(sliderOne)">&#10094;</a>
        <a class="next" @click="nextSlide(sliderOne)">&#10095;</a>
      </div>

      <div id="sliderTwo" class="slider">
        <ul id="slide-wrap">
          <li v-for="(slide, index) in sliderTwo" :key="index" class="slide" :style="transform">
            <div class="content">
              <img :src="slide.img" alt="">
              <p class="slide-text">{{slide.text}}</p>
            </div>
          </li>
        </ul>
        <a class="prev" @click="prevSlide(sliderTwo)">&#10094;</a>
        <a class="next" @click="nextSlide(sliderTwo)">&#10095;</a>
      </div>

      <div id="sliderThree" class="slider">
        <ul id="slide-wrap">
          <li v-for="(slide, index) in sliderThree" :key="index" class="slide" :style="transform">
            <div class="content">
              <img :src="slide.img" alt="">
              <p class="slide-text">{{slide.text}}</p>
            </div>
          </li>
        </ul>
        <a class="prev" @click="prevSlide(sliderThree)">&#10094;</a>
        <a class="next" @click="nextSlide(sliderThree)">&#10095;</a>
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
      count: 0,
      sliderWidth: 0,
      sliderOne: [
        {
          img: require('../../static/longboard1.jpg'),
          text: 'Longboarding'
        },
        {
          img: require('../../static/longboard2.jpg'),
          text: 'snowboarding'
        },
        {
          img: require('../../static/longboard1.jpg'),
        },
        {
          img: require('../../static/longboard1.jpg'),
        },
      ],
      sliderTwo: [
        {
          img: require('../../static/longboard1.jpg'),
          text: 'Longboarding'
        },
        {
          img: require('../../static/longboard2.jpg'),
          text: 'snowboarding'
        },
        {
          img: require('../../static/longboard1.jpg'),
        },
        {
          img: require('../../static/longboard1.jpg'),
        },
      ],
      sliderThree: [
        {
          img: require('../../static/longboard1.jpg'),
          text: 'Longboarding'
        },
        {
          img: require('../../static/longboard2.jpg'),
          text: 'snowboarding'
        },
        {
          img: require('../../static/longboard1.jpg'),
        },
        {
          img: require('../../static/longboard1.jpg'),
        },
      ],
    };
  },
  computed: {
    transform() {
    	const amount = - this.count * this.sliderWidth;
      const transformArg = `translateX(${amount}px)`;
			return {transform: transformArg};
    }
  },
  methods: {
    items(slides) {
      return slides.length;
    },
    nextSlide(slides) {
      if (this.count < (this.items(slides)-1)) {
        this.count = this.count + 1;
      } else {
        this.count = 0;
      }
    },
    prevSlide(slides) {
      if (this.count > 0) {
        this.count = this.count - 1;
      } else {
        this.count = slides.length - 1;
      }
    }
  },
}
</script>

<style scoped>

@media (min-width: 1024px) {
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

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  color: black!important
}

.slider {
  position: relative;
  width: 80vw;
  height: 450px;
  overflow: hidden;
  margin: auto;
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


