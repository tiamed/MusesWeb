<template>

</template>
<script>
import { Grid, GridItem } from 'vux'

export default {
  components: {
    Grid,
    GridItem
  }
}
</script>
<style scoped>
@import url(//maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css);

@import url(https://fonts.googleapis.com/css?family=Source+Code+Pro:400, 500);
@keyframes roll {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 0;
    transform: translate(-150%, -50%) rotate(-90deg) scale(0.3);
    box-shadow: none;
  }
  100% {
    opacity: 1;
    transform: translate(-50%, -50%) rotate(0deg) scale(1);
    box-shadow: 0 3px 5px rgba(0, 0, 0, 0.3);
  }
}
* {
  box-sizing: border-box;
}
.wrapper {
  animation: roll 1.5s;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  padding: 25px;
  background: #eee;
  border-radius: 50%;
  box-shadow: 0 3px 5px rgba(0, 0, 0, 0.3);
}
.wrapper:active #img-result {
  margin-top: 2px;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.3);
}
.wrapper #img-result {
  cursor: pointer;
  margin: 0;
  position: relative;
  background: #f7f7fa;
  background-size: cover;
  background-position: center;
  display: block;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  box-shadow: 0 3px 5px rgba(0, 0, 0, 0.3);
  color: rgba(0, 0, 0, 0);
  transition: box-shadow 0.3s, margin 0.3s, background-image 1.5s;
}
.wrapper #img-result.no-image:before {
  font-family: "FontAwesome";
  content: "\f030";
  position: absolute;
  left: 50%;
  top: 50%;
  color: #fff;
  font-size: 48px;
  opacity: 0.8;
  transform: translate(-50%, -50%);
  text-shadow: 0 0px 5px rgba(0, 0, 0, 0.4);
}
.wrapper button {
  margin-top: 20px;
  display: block;
  font-family: "Open Sans Condensed", sans-serif;
  background: #eee;
  width: 100%;
  border: none;
  color: #fff;
  padding: 10px;
  letter-spacing: 1.3px;
  font-size: 1.05em;
  border-radius: 5px;
  box-shadow: 0 4px 5px rgba(0, 0, 0, 0.3);
  outline: 0;
  transition: box-shadow 0.3s, margin-top 0.3s, padding 0.3s;
}
.wrapper button:active {
  box-shadow: none;
  margin-top: 24px;
  padding: 8px;
}
.show-button {
  background: #264974;
  border: none;
  color: #fff;
  padding: 10px 20px;
  float: right;
  display: none;
}
.upload-result {
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: #fff;
  overflow-y: auto;
}
.upload-result__content {
  word-break: break-all;
  font-family: "Source Code Pro";
  overflow-wrap: break-word;
}
div#bg-img {
  height: -webkit-fill-available;
}
</style>
<script>
import { Flexbox } from "vux";
import upload from "../js/upload.js";
export default {
  data() {},
  beforeCreate() {},
  mounted() {
    this.$nextTick(function() {
      upload.upload();
      $();
    });
  },
  updated() {
    upload.upload();
  },
  methods: {}
};
</script>
