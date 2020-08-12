<template>
  <Layout>
    <div class="header-section">
      <div class="col-xl-1"></div>
      <div class="col-xl-5">
        <h1>Curiculum Vitae</h1>
        <p class="header-description">
          Experienced Visual Jockey with over 3 years of experience in events industry. Excellent reputation for resolving problems, improving customer satisfaction, and driving overall operational improvements. Consistently saved costs while increasing profits.          
        </p>
      </div>
      <div class="col-xl-5">
        <img class="header-banner" src="../../static/Library.png" alt="Front End Developer">
      </div>
    </div>
    <div class="education-section">
      <div class="education">
        <div class="col-xl-1"></div>
        <h2>Education</h2>
      </div>
      <div class="education"> 
        <div class="col-xl-1"></div>
        <div class="col-xl-5" style="text-align:center">
          <img class="cv-image" src="../../static/Education.png" alt="Education">
        </div>   
        <div class="col-xl-5 cv-text">
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2009-2014</p>
            </div>
            <div>
              <p class="cv-title">High School Diploma</p>
              <p class="cv-description">Liceul Economic Nicolae Titulescu, Baia Mare</p>
            </div>
          </div>
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2014-2017</p>
            </div>
            <div>
              <p class="cv-title">Facultatea de Constructii</p>
              <p class="cv-description">Universitatea Tehnica din Cluj-Napoca, Cluj-Napoca</p>
            </div>
          </div>        
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2019-2020</p>
            </div>
            <div>
              <p class="cv-title">Intro in IT</p>
              <p class="cv-description">Scoala Informala de IT, Cluj-Napoca</p>
            </div>
          </div>
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2020</p>
            </div>
            <div>
              <p class="cv-title">Web Development (Javascript)</p>
              <p class="cv-description">Scoala Informala de IT, Cluj-Napoca</p>
            </div>
          </div>
        </div>
      </div> 
    </div>
    <div class="education-section">
      <div class="education">
        <div class="col-xl-1"></div>
        <h2>Work History</h2>
      </div>
      <div class="education flex flex-wrap flex-row-reverse"> 
        <div class="col-xl-1"></div>
        <div class="col-xl-5" style="text-align:center">
          <img class="cv-image cv-work-image" src="../../static/Work.png" alt="Education">
        </div>   
        <div class="col-xl-5">
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2014-2018</p>
            </div>
            <div>
              <p class="cv-title">Volunteer</p>
              <p class="cv-description">Organizatia Studentilor din Universitatea Tehnica, Cluj-Napoca</p>
            </div>
          </div>
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2017-2018</p>
            </div>
            <div>
              <p class="cv-title">Sound and Lights Technician's Assitant</p>
              <p class="cv-description">YTA Events, Cluj-Napoca</p>
            </div>
          </div>        
          <div class="curriculum-vitae">
            <div>
              <p class="cv-years">2018-NOW</p>
            </div>
            <div>
              <p class="cv-title">Visual Jockey</p>
              <p class="cv-description">Live Rental Grup, Cluj-Napoca</p>
              <ul>
                <li>Manipulation of imagery in real time through technological mediation and for an audience, in synchronization to music.</li>
                <li>Set up and operated audio and visual (AV) equipment for many company events, meetings and presentations per month.</li>
                <li>Maintained continuous knowledge of current and newly developed industry technology, making proactive suggestions to improve AV offerings and strategies.</li>
                <li>Ability to work under pressure.</li>
              </ul>
            </div>
          </div>
        </div>
      </div> 
    </div>
    <div class="education-section skills-section">
      <div class="education">
        <div class="col-xl-1"></div>
        <h2>Skills</h2>
      </div>
      <div class="education"> 
        <div class="col-xl-1"></div>
        <div class="col-xl-5" style="text-align:center">
          <img class="cv-image" src="../../static/Skills.png" alt="Education">
        </div>   
        <div class="col-xl-5">
          <div class="curriculum-vitae">
            <div>
              <p class="cv-title">SOFTWARE</p>
              <p class="cv-description"></p>
              <div style="display: flex">
                <img class="technology-icon" src="../../static/HTML5.png" alt="HTML">
                <img class="technology-icon" src="../../static/css.jpg" alt="CSS">
                <img class="technology-icon" src="../../static/Javascript.png" alt="Javascript">
              </div>
            </div>
          </div>
          <div class="curriculum-vitae">
            <div>
              <p class="cv-title">Languages</p>
              <p class="cv-description"></p>
              <div style="display: flex">
                <img class="language-icon" src="../../static/UK.png" alt="UK">
                <img class="language-icon" src="../../static/France.png" alt="France">
              </div>
            </div>
          </div>        
        </div>
      </div> 
    </div>
  </Layout>
</template>

<script>
export default {
  metaInfo: {
    title: 'Curiculum Vitae'
  }
}
</script>
<style scoped>
h2 {
  padding-bottom: 30px;
}

p {
  margin-bottom: 0;
}

ul {
  padding-left: 19px
}

li {
  padding: 5px 0;
}

.curriculum-vitae {
  display: flex;
  padding: 20px 0;
}

.cv-image {
  max-width: 450px;
}

.cv-years {
  font-size: 18px;
  line-height: 31px;
  font-weight: 700;
  padding-right: 20px;
  min-width: 115px;
}

.cv-title {
  font-size: 22px;
  line-height: 28px;
  font-weight: 600;
}

.education-section {
  padding-top: 80px;
}

.language-icon {
  width: 80px;
  margin-top: 30px;
  margin-right: 30px;
}

.technology-icon {
  margin-right: 30px;
  margin-top: 30px;
  width: auto;
  height: 70px;
}

@media (min-width: 1280px) {
  h1 {
    padding-top: 100px;
    padding-bottom: 40px;
  }

  .cv-text {
    padding-top: 80px;
  }

  .cv-work-image {
    margin-top: 100px;
  }

  .header-section, .education{
    display: flex;
  }

  .skills-section {
    padding-bottom: 50px;
  }
}

@media (max-width: 767px) {
  img {
    max-width: 250px!important;
  }

  .curriculum-vitae {
    display: block
  }

  h2 {
    padding-left: 15px;
  }
}
</style>
