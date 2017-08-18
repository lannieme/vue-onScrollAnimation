<template>
  <div class="hello container">
    <div class="content" v-bind:class="{active: isSignUpActive}">
      <div class="statement">
        <h1 class="title">More than 10 million creatives</h1>

        <a class="signupLink" v-bind:class="{active: isSignUpActive}" href="/signup">Sign Up.</a>
      </div>
    </div>

    <div class="trigger">
        <v-waypoint @waypoint="signUpHandler"></v-waypoint>
    </div>

    <div class="trigger">
        <v-waypoint @waypoint="inHandler"></v-waypoint>
    </div>

    <div class="jobs staticHide " v-bind:class="{active: isActive}">
      <div class="jobBody">
        Interested in joining our team? See our <a class="link" href="/careers">open jobs.</a>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      isActive: false,
      isSignUpActive: false
    }
  },
  methods: {
    inHandler () {
      this.isActive = true
    },
    signUpHandler () {
      this.isSignUpActive = true
    }
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.container {
  height: calc(100vh - 60px + 120px);
  position: relative;
}

.content {
  background-color: black;
  display: flex;
  flex-direction: column;
  height: 100%;
  justify-content: center;
}

.content.active {
  background-image: url("../assets/signUpBackground.png");
}

.statement {
  text-align: center;
}

.title {
  color: white;
  font-size: 80px;
  font-weight: bold;
  line-height: 1;
}

.signupLink {
  color: white;
  display: none;
  font-size: 80px;
  font-weight: bold;
  line-height: 1;
  text-decoration: underline;
}

.signupLink.active {
  display:  block;
}

.jobs {
  align-items: center;
  background-color: white;
  display: flex;
  font-size: 25px;
  font-weight: bold;
  height: 120px;
  justify-content: center;
  text-align: center;
  width: 100%;
}

.trigger {
  bottom:  0;
  width:  100%;
}

.staticHide {
  display:  none;
}
.staticHide.active {
  display: flex;
}

.link {
  color: black;
  font-weight: bold;
  text-decoration: underline;
}
</style>
