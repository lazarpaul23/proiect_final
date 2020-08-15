<template>
    <Layout>
        <div class="wall">
            <img src="../../static/wall1.jpg">
        </div>
        <div class="clock">
            <div id="hours"></div>
            <div id="minutes"></div>
            <div id="seconds"></div>
            <div class="three"></div>
            <div class="six"></div>
            <div class="nine"></div>
            <div class="twelve"></div>
            <div class="center"></div>
        </div>
    </Layout>
</template>

<script>
export default {
    metaInfo: {
        title: 'Clock'
    },
    methods: {
        moveHands() {
            let date = new Date();
            let h = 30 * (date.getHours() % 12 + date.getMinutes() / 60);
            let m = 6 * date.getMinutes();
            let s = 6 * date.getSeconds();
            
            document.getElementById('seconds').style.cssText = "-webkit-transform:rotate(" + s + "deg);";
            document.getElementById('minutes').style.cssText = "-webkit-transform:rotate(" + m + "deg);";
            document.getElementById('hours').style.cssText = "-webkit-transform:rotate(" + h + "deg);";
        }
    },
    mounted() {
        setInterval(() => {
		    this.moveHands()
	}, 1000)
    }
}
</script>
<style scoped>
* { 
  margin: 0;
  padding: 0;
  border: 0;
}

.clock {
  height: 400px;
  width: 400px;
  background-color: #DDDDDD;
  border-radius: 100%;
  border: 5px solid black;
  margin: auto;
  position: absolute;
  top: 250px;  right: 50px;
}

.twelve {
  position: absolute;
  width: 3px;
  height: 15px;
  background: #111111;
  left: 0;
  top: 0;
  right: 0;
  margin: 0 auto;
}

.three {
  position: absolute;
  width: 15px;
  height: 3px;
  background: #111111;
  top: 0;
  bottom: 0;
  right: 0;
  margin: auto 0;
}

.six {
  position: absolute;
  width: 3px;
  height: 15px;
  background: #111111;
  left: 0;
  bottom: 0;
  right: 0;
  margin: 0 auto;
}

.nine {
  position: absolute;
  width: 15px;
  height: 3px;
  background: #111111;
  top: 0;
  bottom: 0;
  left: 0;
  margin: auto 0;
 }

.center {
  width: 10px;
  height: 10px;
  position: absolute;
  left: 0; right: 0; bottom: 0; top: 0;
  margin: auto;
  background: #000;
  border-radius: 100%;
 }

#seconds {
  position: absolute;
  height: 160px;
  width: 2px;
  left: 0; right: 0; bottom: 160px; top: 0px;
  margin: auto;
  background: #000;
  -webkit-transform-origin: bottom;
  background: #FF4136;
}

#minutes {
  position: absolute;
  height: 200px;
  width: 2px;
  left: 0; right: 0; bottom: 200px; top: 0px;
  margin: auto;
  background: #000;
  -webkit-transform-origin: bottom;
}

#hours {
  position: absolute;
  height: 80px;
  width: 6px;
  left: 0; right: 0; bottom: 80px; top: 0px;
  margin: auto;
  background: #000;
  -webkit-transform-origin: bottom;
}

.wall {
  margin: 0 auto;
  width: 100%;
  height: 100%;
}
</style>