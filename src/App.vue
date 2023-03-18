<template>
  <!-- <div class="container mr-100"> -->
  <v-app id="body">
    <Header :loggedIn="loggedIn" :logout="logout" />
  <!-- </div> -->
    
    <v-main>
      <router-view class="container mt-15"></router-view>
    </v-main>


    <Footer fixed></Footer>
  </v-app>
<!-- </div> -->
  <!-- <Footer></Footer> -->
</template>

<script>
import Footer from './components/Footer.vue'
import Header from './components/Header.vue'
import moment from 'moment'
export default {
  name: 'App',
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
    this.appBarHeight = this.$refs.appBar.$el.offsetHeight;
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll);
    //  this.appBarHeight = this.$refs.appBar.$el.offsetHeight;
  },
  methods:{
    handleScroll() {
      this.scrollPosition = window.scrollY;
      if (this.scrollPosition > this.appBarHeight+10) {
        this.appBarBackgroundColor = '#FFA500'; // Change to blue color
        this.elevation = 4;
      } else {
        this.appBarBackgroundColor = 'transparent'; // Change to transparent
        this.elevation = 0;
      }
    },
    onClock(val){
      this.time = moment(val).format("DD/MM/YYYY hh:mm:ss");
    }
  },
  components: {
    Footer,
    Header
  },
  data() {
    return {
      items: [
        { id: 1,title: 'Service 1' },
        { id: 2,title: 'Service 2' },
        { id: 3,title: 'Service 3' },
        { id: 4,title: 'Service 4' },
        ],
        scrollPosition: 0,
        elevation: 0,
        appBarBackgroundColor: 'transparent',
        appBarHeight: 0,
      // time:"",
      loggedIn: false,
    }
    //
  },
};
</script>

<style>
@import url(https://fonts.googleapis.com/css?family=Nunito+Sans);
#grad1 {
    height: 200px;
    background: red; /* For browsers that do not support gradients */    
    background: -webkit-linear-gradient(left, red , yellow); /* For Safari 5.1 to 6.0 */
    background: -o-linear-gradient(right, red, yellow); /* For Opera 11.1 to 12.0 */
    background: -moz-linear-gradient(right, red, yellow); /* For Firefox 3.6 to 15 */
    background: linear-gradient(to right, red , yellow); /* Standard syntax (must be last) */
}
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#body {
  height: 100vh;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-image: linear-gradient(45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 300% 300%;
  animation: color-anim 12s infinite linear alternate;
  -webkit-animation: color-anim 12s infinite linear alternate;
}
@keyframes color-anim {
  0% {
    background-position: 0 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0 50%;
  }
}
/* div {
  border: 1px solid black;
  background-color: lightblue;
  padding-top: 50px;
  padding-right: 30px;
  padding-bottom: 50px;
  padding-left: 80px;
} */
/* div {
  width: 500px;
  height: 200px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
  background: rgba(255, 255, 255, 0.1);
} */
/* div h1 {
  color: #fff;
  font-size: 1.5rem;
  text-transform: capitalize;
} */

</style>