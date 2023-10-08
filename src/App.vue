<template>
  <GenerateQoute />
</template>

<script>
import GenerateQoute from './components/GenerateQoute.vue';

export default {
  name: 'App',
  components: {
    GenerateQoute,
  }
}
</script>

<style>
html, body {
  position: absolute;
  height: 100%;
  width: 100%;
  left: 0;
  top: 0;
}

html {
  background-image: url(https://unsplash.imgix.net/photo-1423683249427-8ca22bd873e0?fit=crop&fm=jpg&h=700&q=75&w=1050);
  background-position: center center;
  background-size: cover;
}

body {
  background-color: rgba(0, 0, 0, 0.1);
  font-family: 'Nova Square', cursive;
}

.neato-header {
  color: white;
  padding: 30px;
  text-align: center;
  border: 3px solid white;
  margin-top: 30px;
}
.neato-header h1, .neato-header h2 {
  letter-spacing: 0.05em;
}
.neato-header h1 {
  font-size: 25px;
  text-transform: uppercase;
}
.neato-header h2 {
  transform: translate(0, -50%);
  font-family: "Vollkorn";
  font-weight: italic;
  font-size: 21px;
  overflow: hidden;
  margin: -30px -33px 0 -33px;
  position: absolute;
  width: calc( 100% + 6px );
}
.neato-header h2:before, .neato-header h2:after {
  content: "";
  position: absolute;
  width: 100%;
  margin-top: -2px;
  border-top: 3px solid white;
  top: 50%;
}
.neato-header h2:before {
  transform: translate(-100%, 0);
  margin-left: -30px;
}
.neato-header h2:after {
  margin-left: 30px;
}
.card {
  box-shadow: rgba(255, 255, 255) 0px 8px 0px;
  position: relative;
}

.card {
  position: relative;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  flex-direction: column;
  min-width: 0px;
  overflow-wrap: break-word;
  background-color: rgb(248, 248, 248);
  background-clip: border-box;
  border: 0px solid rgba(0, 0, 0, 0.125);
  border-radius: 0.57rem;
}

.bg-primary {
  background-color: rgb(240, 194, 75) !important;
}

.mb-9 {
  margin-bottom: 4.96rem !important;
}

.card-icon-border-large {
  width: 100px;
  height: 100px;
  margin: -3.06rem auto 0px;
  text-align: center;
  background-color: rgb(255, 255, 255);
  border: 6px solid;
  border-radius: 50%;
  font-size: 1.88rem;
  line-height: 90px;
  color: rgb(102, 102, 102);
}

.mtn-80 {
  margin-top: -5rem !important;
}

.border-primary {
  border-color: rgb(240, 194, 75) !important;
}

.text-primary {
  color: rgb(240, 194, 75) !important;
}

.bg-success {
  background-color: rgb(181, 213, 106) !important;
}

.border-success {
  border-color: rgb(181, 213, 106) !important;
}

.text-success {
  color: rgb(181, 213, 106) !important;
}

.bg-danger {
  background-color: rgb(234, 112, 102) !important;
}

.border-danger {
  border-color: rgb(234, 112, 102) !important;
}

.text-danger {
  color: rgb(234, 112, 102) !important;
}

.bg-info {
  background-color: rgb(132, 190, 214) !important;
}

.border-info {
  border-color: rgb(132, 190, 214) !important;
}

.text-info {
  color: rgb(132, 190, 214) !important;
}

.bg-purple {
  background-color: rgb(165, 151, 231) !important;
}

.border-purple {
  border-color: rgb(165, 151, 231) !important;
}

.text-purple {
  color: rgb(165, 151, 231) !important;
}


.bg-pink {
  background-color: rgb(234, 119, 173) !important;
}

.border-pink {
  border-color: rgb(234, 119, 173) !important;
}

.text-pink {
  color: rgb(234, 119, 173) !important;
}

a{
  text-decoration: none;
  color: white;
}
a:hover{
  color: white;
  opacity: 0.4;
}

</style>
