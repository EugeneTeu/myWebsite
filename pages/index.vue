<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm12 md12>
      <v-row justify="center">
        <p class="display-3 font-italic font-weight-bold">Welcome</p>
      </v-row>
      <v-row justify="center">
        <p class=" ma-4  subtitle-1 font-italic font-weight-light">
          My name is Eugene Teu and I am currently a year 2 Computer Science Undergraduate @ National University of Singapore. My focus area of study includes Software Engineering and Programming languges.
          I aspire to use my knowledge and skills to build things that will have leave an impact on society in the future.
        </p>
      </v-row>
      <v-divider class="mt-4 mb-4"></v-divider>
      <p
        class="subtitle-2 font-weight-light"
      >This website was build using VueJs, VuetifyJs and Nuxtjs frameworks. Not only will this serves as my portfolio website, it is a playground for me to explore web development</p>
      <v-row justify="center">
        <p class="display-3 font-italic font-weight-bold">My Skills</p>
      </v-row>
      <v-row justify="center">
        <v-avatar size="200">
          <v-img :src="require('../assets/profilepic1.png')" aspect-ratio="5/4"></v-img>
        </v-avatar>
      </v-row>
      <v-row justify="center">
        <p
          class="ml-4 mr-4 subtitle-1 font-italic font-weight-light"
        >The following are my current skills. I have a strong focus in both App and Web development</p>
      </v-row>
      <v-row justify="center">
        <v-card class="mt-2 mr-2 ml-2 mb-2" min-width="300" hover>
          <v-card-title>Languages</v-card-title>
          <v-list>
            <v-list-item v-for="(index) in  languages" :key="index">
              <v-list-item-content>
                <v-list-item-title v-text="index.lang"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-card>
        <v-card class="mt-2 ml-2 mr-2 mb-2" min-width="300" hover>
          <v-card-title>Frameworks</v-card-title>
          <v-list>
            <v-list-item v-for="(index) in  Frameworks" :key="index">
              <v-list-item-content>
                <v-list-item-title v-text="index.framework"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
          <v-card-title>Customer Mangement</v-card-title>
          <v-list>
            <v-list-item v-for="index,i in  Customer" :key="i">
              <v-list-item-content>
                <v-list-item-title v-text="index.cms"></v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </v-list>
        </v-card>
      </v-row>
         <v-row justify="center">
        <v-card class="mt-2 mr-2 ml-2 mb-2" min-width="300" hover>
          <v-card-title>Articles I have written</v-card-title>
          <v-list>
            <v-list-item v-for="index,i in  ArticlesWritten" :key="i">
              <v-list-item-content>
                <v-list-item-title class="text-wrap" v-text="index.article"></v-list-item-title>
              </v-list-item-content>
               <v-list-item-action>

              <v-btn
              hover
              color="green"
              :href="index.link"
              target="_blank"
              >View </v-btn>

            </v-list-item-action>
            </v-list-item>
          </v-list>

        </v-card>
        </v-row>
      <v-divider class="mt-2 mb-4"></v-divider>

      <v-row justify="center">
        <p class="ma-2 display-3 font-italic font-weight-bold">My Experience</p>
        <v-card hover>
          <v-list-item v-for="index,i in WorkExperience" :key="i">
            <v-list-item-content>
              <v-list-item-title>{{index.job}}</v-list-item-title>
              <v-list-item-subtitle v-if="index.companyName">Company: {{ index.companyName}}</v-list-item-subtitle>
              <v-list-item-subtitle v-if="index.writeup">{{ index.writeup}}</v-list-item-subtitle>
              <v-list-item-subtitle v-if="index.timePeriod">{{ index.timePeriod}}</v-list-item-subtitle>
              <v-divider class="mt-2"></v-divider>
            </v-list-item-content>

          </v-list-item>
        </v-card>
      </v-row>

      <v-divider class="mt-4 mb-4"></v-divider>
      <v-row justify="center">
        <p class=" ma-2 display-3 font-italic font-weight-bold">Contact Me</p>
      </v-row>
      <v-row justify="center">
        <v-btn
         hover
        class = "ma-4 text-black"
        v-for="index,i in contact"
        :key=i
        color="green"
    
        :href="index.link"
        target="_blank"
        >
        {{index.social}}
        </v-btn>
      </v-row>
        </v-row>

  

    </v-flex>
  </v-layout>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      languages: [
        { lang: "HTML/CSS (intermediate)" },
        { lang: "JavaScript (intermediate)" },
        { lang: "Java (proficient)" },
        { lang: "Python (intermediate)" },
        { lang: "Dart (proficient)" },
        { lang: "Haskell (beginner)" }
      ],
      Frameworks: [
        { framework: "Flutter" },
        { framework: "Yii2" },
        { framework: "VueJs" }
      ],
      Customer: [
        { cms: "WordPress (proficient)" },
        { cms: "Drupal (prior experience)" }
      ],
      ArticlesWritten: [
          { article:"Life at Webpuppies",
            link:"https://webpuppies.com.sg/blogposts/what-is-it-like-being-independent-as-an-intern/"
          },
          {
            article:"Custom Flutter Widget tutorial",
            link:"https://medium.com/@eugeneteu/flutter-building-a-custom-step-input-interface-afc5fcd36d8"
          }
      ],

      WorkExperience: [
        {
          job: "Full Stack Web Developer Intern",
          companyName: "Webpuppies Pte Ltd",
          writeup:
            "Worked on Design, Front-end development and Back-end development Achieved project completion for companies like Addidas & Reebok, Teapasar and Truly Enamoured",
          timePeriod: "May 2019 -> Aug 2019"
        },
        {
          job: "Software Engineer Intern (incoming)",
          companyName: "",
          timePeriod: "Dec 2019 -> April 2020"
        }
      ],

      contact: [
        {
          social : "Linkedin",
          link : "https://www.linkedin.com/in/eugeneteu/"
        },
         {
          social : "Github",
          link : "https://github.com/EugeneTeu"
        },
        {
          social: "Instagram",
          link: "https://www.instagram.com/cwteu/?hl=en"
        },
         {
          social: "Email",
          link: "mailto:eugeneteu@gmail.com"
        }

      ]
    };
  }
};
</script>
