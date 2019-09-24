<template>
  <v-container grid-list-md text-xs-center>
    <v-layout column>
      <v-flex xs12 sm8 md12 class="text-center">
        <p class="display-3 font-italic font-weight-bold">My Portfolio</p>
        <p
          class="subtitle-1 font-italic font-weight-light"
        >I enjoy creating things in my spare time and participating in hackathons!</p>
        <p
          class="subtitle-1 font-italic font-weight-light"
        >The following are some stuff that I have completed!</p>
        <v-row justify="center">
          <div class="text-center mr-4 ml-4">
            <v-avatar size="55">
              <img src="../assets/flutter.png" alt="avatar" />
            </v-avatar>
          </div>
          <div class="text-center mr-4 ml-4">
            <v-avatar size="62">
              <img src="../assets/firebase.png" alt="firebase" />
            </v-avatar>
          </div>
        </v-row>
        <v-divider class="mt-8 mb-4"></v-divider>
        <p class="display-2 font-italic font-weight-medium">Side Projects</p>
        <v-divider class="mt-2 mb-4"></v-divider>
        <v-container>
          <v-layout row>
            <v-flex
            sm12
            md6>
              <v-card
              min-height="480"

              fluid
              hover
              >
                <v-list-item>
                    <v-list-item-content>
                      <v-list-item-title class="headline font-weight-bold" >{{projects[0].title}}</v-list-item-title>
                      <v-list-item-subtitle  >{{projects[0].subtitle}}</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>

                <v-divider class="mt-4 mb-4"></v-divider>
                <v-row justify="center"
                  >
                  <v-img  :src="require('../assets/homepage.png')" aspect-ratio="1" contain max-height="200"></v-img>
                  <v-img  :src="require('../assets/loginscreen.png')" aspect-ratio="1" contain max-height="200"></v-img>
                </v-row>



              <v-card-text>{{ projects[0].writeup}}</v-card-text>
              <v-card-actions>
              <v-btn
              hover
              color="green"
              :href="projects[0].githublink"
              target="_blank"
              >Github Repo</v-btn>
              </v-card-actions>
              </v-card>
              </v-flex>
                <v-flex
                sm12
                md6>
                <v-card
              min-height="480"

              fluid
              hover
              >
                <v-list-item>
                    <v-list-item-content>
                      <v-list-item-title class="headline font-weight-bold" >{{projects[1].title}}</v-list-item-title>
                      <v-list-item-subtitle  >{{projects[1].subtitle}}</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>

                <v-divider class="mt-4 mb-4"></v-divider>
                <v-row justify="center"
                  >
                  <v-img  :src="require('../assets/flutterHack.png')" aspect-ratio="1" contain max-height="200"></v-img>
                </v-row>
              <v-card-text>{{ projects[1].writeup}}</v-card-text>
              <v-card-actions>
              <v-btn
              hover
              color="green"
              :href="projects[1].githublink"
              target="_blank"
              >Github Repo</v-btn>
              </v-card-actions>
              </v-card>

            </v-flex>
          </v-layout>
        </v-container>
        <v-divider class="mt-4 mb-4"></v-divider>
        <p class="display-2 font-italic font-weight-medium">Hackathon Experiences</p>
        <v-divider class="mt-2 mb-4"></v-divider>
        <v-expansion-panels :multiple="true" :inset="true">
          <v-expansion-panel v-for="(info) in hackathons" :key="info.index">
            <v-expansion-panel-header :ripple="true" class="font-weight-bold">{{ info.title }}</v-expansion-panel-header>
            <v-expansion-panel-content :eager="true">
              <v-col v-if="info.index == 0">
              <v-img  :src="require('../assets/yitu.png')" contain height="250"></v-img>
              <v-divider class="mt-4 mb-4"></v-divider>
              </v-col>
              {{info.writeup}}
              <v-btn v-if="info.index == 1" hover
              color="green"
              :href="info.githublink"
              target="_blank">Github repo</v-btn>
              </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-flex>
    </v-layout>
  </v-container>
</template>


<script>
export default {
  components: {},
  data() {
    return {
      projects: [
        {
          title: "BrewCompass",
          subtitle: "Mobile App using Flutter framework with Firebase as back-end ",

          src: "../assets/loginscreen.png",
          writeup:
            "A specialty coffee companion app that has journaling functionality and provides a platform for Coffee Lovers to share recipes. Created for NUS Project Orbital. Acheived highest possible level of achievement among the three grades: Apollo 11",
          githublink:
            "https://github.com/EugeneTeu/BrewCompass/tree/master/coffee_app"
        },
        {
          title: "FlutterFly",
          subtitle: "Third Place at Singapore Flutter Hackathon 2019",
          writeup:
            "Trex clone centered around flutter community. Submission for International Flutter Hackathon (Singapore leg) ",
          githublink: "https://github.com/EugeneTeu/FlutterFly"
        }
      ],
      hackathons: [
        {
          index: 0,
          title: "YITU HACK-AI-THON",
          cardtitle: "Technology used: Python with TensorFlow",
          writeup:
            "Finished top 20 out of 41 teams that participated in the hackathon. Tasked with improving a machine learning model in detecting cars and pedestrian with in 72 hours",
          githublink: ""
        },
        {
          index: 1,
          title: "NUS Hack N Roll 2019",
          src: "",
          cardtitle: "Technology used: Java, Java Swing",
          writeup:
            "Our submission for this hackathon was a fast-paced arcade game written in Java. Paired with a Bluetooth-based motion controller built out of an Arduino kit. Players would be able to navigate through a menu and use this controller to control their character to avoid the enemy and rise through the levels",
          githublink: "https://github.com/EugeneTeu/DI-SuHackathon"
        }
      ]
    };
  }
};
</script>
