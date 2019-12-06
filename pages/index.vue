<template>
  <v-row align="center" justify="center">
    <v-col>
      <v-row class="pl-5 pb-5" align="center" justify="center">
        <v-avatar color="#fafafa" size="200">
          <v-img :src="require('~/assets/images/logo.svg')" alt="logo">
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0" align="center" justify="center">
                <v-progress-circular size="100" indeterminate color="primary darken-1"></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </v-avatar>
      </v-row>
      <v-row align="center" justify="center">
        <h1 class="pl-5 display-1 font-weight-thin text-center black--text">The Congress you need</h1>
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
        <v-row v-for="(depart, i) in departs" :key="i" align="center" justify="center" class="py-0">
          <v-col
            v-for="(member, j) in depart.members"
            :key="j"
            class="text-center"
            :lg="depart.title === 'Main' ? '4' : '6'"
            xs="10"
          >
            <v-card class="mx-5 my-0" shaped elevation="3" color="rgb(255, 255, 255, 0.15)">
              <v-row align="center" justify="center">
                <v-col cols="8">
                  <v-icon color="white" class="py-3">mdi-{{depart.icon}}</v-icon>
                  <v-card-title primary-title class="justify-center pt-1">
                    <div>
                      <h3
                        class="white--text font-weight-bold text-uppercase member-name cursor"
                        @click="gotoIntra(member.intra)"
                      >{{member.name}}</h3>
                      <p class="white--text overline">( aka {{member.aka}} )</p>
                      <div
                        class="body-2 font-italic white--text font-weight-light text-uppercase"
                      >{{member.position}}</div>
                    </div>
                  </v-card-title>
                </v-col>
                <v-col>
                  <v-avatar
                    class="px-0 pb-2 cursor"
                    size="150"
                    tile
                    @click="gotoIntra(member.intra)"
                  >
                    <v-hover v-slot:default="{ hover }">
                      <v-img
                        v-if="member.srs"
                        height="130%"
                        width="150%"
                        :src="require(`~/assets/images/avatars/`+ (hover ? `fun/${member.srs}_fun.png` : `srs/${member.srs}.png`))"
                      >
                        <template v-slot:placeholder>
                          <v-row class="fill-height ma-0" align="center" justify="center">
                            <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                          </v-row>
                        </template>
                      </v-img>
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
              intra: "msanabi",
              srs: "ozaazaa"
            },
            {
              name: "Ayman Biri",
              aka: "rasbiri",
              intra: "abiri",
              position: "president",
              srs: "biri"
            },
            {
              name: "Mariam Fanna",
              aka: "Mariam",
              intra: "fmariam",
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
              intra: "mouyizme",
              position: "internal",
              srs: "toxic"
            },
            {
              name: "Alaa Zorkane",
              aka: "droven",
              intra: "azorkane",
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
              aka: "7fsa, bimo, chniwla",
              intra: "hessabra",
              position: "external",
              srs: "hafsa"
            },
            {
              name: "Aicha Laafia",
              aka: "fofo",
              intra: "alaafia",
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
              intra: "slyazid",
              position: "secretary",
              srs: "souad"
            },
            {
              name: "Abdesslame Abouibrahim",
              aka: "abida",
              intra: "aabouibr",
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
              intra: "hkchikec",
              position: "Tresory",
              srs: "kchikech"
            },
            {
              name: "Hasnaa Elalam",
              aka: "7sna",
              intra: "helalam",
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
              aka: "30 points",
              intra: "yez-zain",
              position: "Counselor",
              srs: "yahya"
            },
            {
              name: "Anas Massnaoui",
              aka: "Anas",
              intra: "amassnao",
              position: "Counselor",
              srs: "anas"
            }
          ]
        }
      ]
    };
  },
  methods: {
    gotoIntra: function(name) {
      window.open(`https://profile.intra.42.fr/users/${name}`, "_blank");
    }
  }
};
</script>

<style>
.member-name {
  font-size: calc(10px + 0.5vh) !important;
}
.container {
  padding: 0;
}
.carousel {
  height: 100vh;
}
.cursor {
  cursor: pointer;
}
</style>
