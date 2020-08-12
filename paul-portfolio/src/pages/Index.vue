<template>
  <Layout>
    <div class="header">
      <div class="header-section">
        <div class="col-md-1"></div>
        <div class="col-md-5 col-xl-4">
          <h1>Hi,<br> I'm Paul Lazar!</h1>
          <p class="header-description">
            I'm 25 years old and I'm form Baia Mare, Romania. In my last 3 years I work in the field of events, more exactly at a stage company, as Visual Jockey. I had the chance to be part of the biggest festivals and concerts in Cluj-Napoca and Romania. But this job was too physically exhausting so I decide to try something new and lear programming. </p>
        </div>
        <div class="col-md-5 col-xl-6">
          <img class="header-banner" src="../../static/header-banner.png" alt="Front End Developer">
        </div>
      </div>
      <div class="about-section">
        <div class="col-md-1"></div>
        <div class="col-xl-10">
          <h2>
            What can I do for you?
          </h2>
          <div class="about">
            <div class="col-xl-4 services">
              <img class="about-image" src="../../static/about-image.jpg" alt="Front End Developer">
            </div>
            <div class="col-xl-4 services">
              <img src="../../static/webdesign.png" alt="Web Design" width="170">
              <p class="service-title">Web Design</p>
              <p class="service-description">A website should be designed for the people who will use it, so that's exactly what I do. User focused design should be the primary goal of any website.</p>
            </div>
            <div class="col-xl-4 services">
              <img src="../../static/webdevelopment.png" alt="Web Design" width="170">
              <p class="service-title">Web Development</p>
              <p class="service-description">Every website should be built with two primary goals: Firstly, it needs to work across all devices. Secondly, it needs to be fast as possible.</p>
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
    title: 'Paul Lazar - Front End Developer'
  }
}
</script>

<style scoped>
.about {
  padding: 50px 0 ;
}

.header h1 {
  margin: 0;
  font-size: 48px;
  line-height: 53px;
  padding-top: 50px;
}

.header-description {
  padding-top: 50px;
}

.header-section {
  max-width: 1200px;
  margin: auto;
}

.service-title {
  margin-top: 20px;
  font-size: 24px;
  font-weight: 600;
}

.services {
  padding-bottom: 50px;
}

@media (min-width: 768px) {
  .about, .header-section, .about-section {
    display: flex;
  }

  .about-image {
    padding-right: 60px;
  }

  .header-banner {
    padding-left: 60px;
  }
}

@media (max-width: 767px) {
  .about-image {
    margin: auto;
  }

  .header-banner {
    margin: 20px 0 50px 0;
  }
  .services {
    margin: auto;
    text-align: center;
  }
}
</style>
