<template>
  <v-row align="center" justify="center">
    <v-col>
      <v-row class="pl-5 pb-5" align="center" justify="center">
        <v-avatar color="#fafafa" size="200">
          <v-img :src="require('~/assets/images/logo.svg')" alt="logo"></v-img>
        </v-avatar>
      </v-row>
      <v-row align="center" justify="center">
        <h1 class="pl-5 display-2 font-weight-thin text-center black--text">The Congress you need</h1>
      </v-row>
    </v-col>
    <v-img
      src="https://i.ibb.co/b1vDRqB/bg.png"
      aspect-ratio="2.1"
      class="grey lighten-2 mx-5 my-5"
      max-height
      position="absolute"
    >
      <v-col>
        <v-row v-for="(depart, i) in departs" :key="i" align="center" justify="start" class="py-0">
          <v-col v-for="(member, j) in depart.members" :key="j" class="text-center">
            <v-card class="mx-5 my-0" shaped elevation="3" color="rgb(255, 255, 255, 0.15)">
              <v-row>
                <v-col cols="8">
                  <v-icon color="white" class="py-3">mdi-{{depart.icon}}</v-icon>
                  <v-card-title primary-title class="justify-center pt-1">
                    <div>
                      <h3
                        class="headline white--text font-weight-bold text-uppercase"
                      >{{member.name}}</h3>
                      <p class="white--text overline">( aka {{member.aka}} )</p>
                      <div
                        class="body-2 font-italic white--text font-weight-light text-uppercase"
                      >{{member.position}}</div>
                    </div>
                  </v-card-title>
                </v-col>
                <v-col class="py-0">
                  <v-avatar class="py-0 px-0" size="150" tile>
                    <v-hover v-slot:default="{ hover }">
                      <v-img
                        v-if="member.srs"
                        height="130%"
                        width="150%"
                        :src="require(`~/assets/images/avatars/`+ (hover ? `fun/${member.srs}_fun.png` : `srs/${member.srs}.png`))"
                      ></v-img>
                    </v-hover>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-card>
          </v-col>
        </v-row>
      </v-col>
    </v-img>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      departs: [
        {
          title: "Main",
          icon: "bank",
          members: [
            {
              name: "Oussama Zaazaa",
              position: "vice-president",
              aka: "Ozaazaa",
              srs: "ozaazaa"
            },
            {
              name: "Ayman Biri",
              aka: "biri",
              position: "president",
              srs: "biri"
            },
            {
              name: "Mariam Fanna",
              aka: "Mariam",
              position: "vice-president",
              srs: "mariam"
            }
          ]
        },
        {
          title: "Internal Affairs",
          icon: "cctv",
          members: [
            {
              name: "Mohamed Ouyizme",
              aka: "toxiic",
              position: "internal",
              srs: "toxic"
            },
            {
              name: "Alaa Zorkane",
              aka: "droven",
              position: "vice-internal",
              srs: "alaa"
            }
          ]
        },
        {
          title: "External Affairs",
          icon: "balloon",
          members: [
            {
              name: "Hafsa Essabrari",
              aka: "7fsa",
              position: "external",
              srs: "hafsa"
            },
            {
              name: "Aicha Laafia",
              aka: "l3afia",
              position: "vice-external",
              srs: "aicha"
            }
          ]
        },
        {
          title: "Secretary",
          icon: "typewriter",
          members: [
            {
              name: "Souad Lyazid",
              aka: "so3ada",
              position: "secretary",
              srs: "souad"
            },
            {
              name: "Abdesslame Abouibrahim",
              aka: "abida",
              position: "vice-secretary",
              srs: "abida"
            }
          ]
        },
        {
          title: "Tresory",
          icon: "cash-usd-outline",
          members: [
            {
              name: "Hamza Kchikech",
              aka: "kchkch lkbir",
              position: "Tresory",
              srs: "kchikech"
            },
            {
              name: "Hasnaa Elalam",
              aka: "7sna",
              position: "vice-tresory",
              srs: "hasna"
            }
          ]
        },
        {
          title: "Counslers",
          icon: "chat-outline",
          members: [
            {
              name: "Yahya Ez Zainabi",
              aka: "32 points",
              position: "Counsler",
              srs: "yahya"
            },
            {
              name: "Anas Massnaoui",
              aka: "Anas",
              position: "Counsler",
              srs: "anas"
            }
          ]
        }
      ]
    };
  }
};
</script>

<style>
.container {
  padding: 0;
}
.carousel {
  height: 100vh;
}
</style>
