<template>
<div class="resume col-12">
  <div class="section profile-content">
      <div class="owner">
        <div class="avatar">
          <img :src="person.image" alt="Circle Image" class="img-circle img-no-padding img-responsive">
        </div>
        <div class="name">
          <p class="text-center">{{person.name.first}} {{person.name.middle}} {{person.name.last}}</p>
          <h6 class="description">{{person.position}}</h6>
          <p class="description">{{ person.about }}</p>
        </div>
      </div>
      <div class="row">
        <div class="col-6 section-dark">
          <h3 class="title"><i class="fas fa-id-card"></i> Contact</h3>
          <h5>
            <i class="fas fa-user-circle"></i>
            <li href="#" class="btn btn-link" target="_blank">Born {{person.birth.year}} in {{person.birth.location}}</li>
          </h5>
          <h5>
            <i class="fa fa-home" aria-hidden="true"></i>
            <a href="#" class="btn btn-link" target="_blank">{{person.contact.street}},{{person.contact.city}}</a>
          </h5>
          <h5>
            <i class="fa fa-envelope" aria-hidden="true"></i>
            <a :href="'mailto:'+person.contact.email" class="btn btn-link" target="_blank">{{person.contact.email}}</a>
          </h5>
          <h5>
            <i class="fa fa-phone" aria-hidden="true"></i>
            <a :href="'tel:'+person.contact.phone" class="btn btn-link" target="_blank">{{person.contact.phone}}</a>
          </h5>
          <h5>
            <i class="fa fa-globe" aria-hidden="true"></i>
            <a :href="'https://'+person.contact.website" class="btn btn-link" target="_blank">{{person.contact.website}}</a>
          </h5>
          <h5>
            <i class="fa fa-linkedin" aria-hidden="true"></i>
            <a :href="'https://linkedin.com/in/'+person.contact.linkedin" class="btn btn-link" target="_blank">{{person.contact.linkedin}}</a>
          </h5>
          <h5>
            <i class="fa fa-github" aria-hidden="true"></i>
            <a :href="'https://github.com/'+person.contact.github" class="btn btn-link" target="_blank">{{person.contact.github}}</a>
          </h5>
          <h5>
            <i class="fab fa-youtube"></i>
            <a :href="'https://youtube.com/'+person.contact.youtube" class="btn btn-link" target="_blank">{{person.contact.youtube}}</a>
          </h5>
          <hr>
          <h3 class="title"><i class="fas fa-flask"></i> Skills</h3>
          <div class="skill" v-for="skill in person.skills">
            <div class="right">
              <span class="title">{{skill.name}}&nbsp;</span>
              <div class="progress">
                 <div :class="'progress-bar progress-bar-'+skill.type" role="progressbar" :style="'width: '+skill.level+'%;'" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
                </div>
              </div>
            </div>
          </div>
                  <br>
        </div>
        <br>
        <br>
        <br>
        <div class="col-6">
          <h3 class="title"><i class="fas fa-briefcase"></i> Experience</h3>
            <div v-for="experience in person.experience">
              <a :href="experience.website" target="_blank">
                <div class="row">
                  <div class="col-3 ml-auto mr-auto">
                    <img :src="experience.img" alt="Circle Image" class="img-circle img-no-padding img-responsive">
                  </div>
                  <div class="col-9 ml-auto mr-auto">
                    <p class="mytext">{{experience.position}}-{{experience.company}}</p>
                    <h6 class="description">{{experience.timeperiod}}</h6>
                    <p class="description">{{experience.description}}</p>
                  </div>
                </div>
              </a>
              <hr>
            </div>
          <h3 class="title">  <i class="fas fa-graduation-cap"></i>  Education</h3>
          <div v-for="education in person.education">
          <a :href="education.website" target="_blank">
            <div class="row">
              <div class="col-3 ml-auto mr-auto">
                <img :src="education.img" alt="Circle Image" class="img-circle img-no-padding img-responsive">
              </div>
              <div class="col-9 ml-auto mr-auto">
                <p class="mytext">{{education.degree}}</p>
                <h6 class="description">{{education.timeperiod}}</h6>
                <p class="description">{{education.description}}</p>
              </div>
            </div>
            </a>
            <hr>
          </div>
            <h3 class="title"><i class="fas fa-code"></i> Projects</h3>
            <div v-for="project in person.projects">
              <a :href="project.website" target="_blank">
                <div class="row">
                  <div class="col-12 ml-auto mr-auto">
                    <p class="mytext">{{project.name}}</p>
                    <h6 class="description">{{project.platform}}</h6>
                    <p class="description">{{project.description}}</p>
                  </div>
                </div>
              </a>
              <hr>
            </div>
        </div>
      </div>
      <br/>
  </div>
</div>
</template>

<script>
import {
  PERSON
} from '../person';

import Vue from 'vue';
export default Vue.component('cool', {
  name: 'cool',
  data () {
    return {
      person: PERSON
    };
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

@import '../assets/css/bt.css';
@import '../assets/css/paper-kit.min.css';

.mytext {
  color: #66615B;
}
</style>
