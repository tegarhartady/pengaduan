<template>
  <section id="hero">
    <v-parallax dark src="@/assets/img/bgHero.jpg" height="750">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="6" xl="8">
              <h1 class="display-2 font-weight-bold mb-4">Vuetify.js</h1>
              <h1 class="font-weight-light">
                Lorem ipsum dolor sit amet consectetur <br />
                adipisicing elit. Maiores porro voluptatibus <br />
                delectus nam optio harum!
              </h1>
              <v-btn
                rounded
                outlined
                large
                dark
                @click="$vuetify.goTo('#features')"
                class="mt-5"
              >
                Saiba mais
                <v-icon class="ml-2">mdi-arrow-down</v-icon>
              </v-btn>
              <div class="video d-flex align-center py-4">
                <a @click.stop="dialog = true" class="playBut">
                  <svg
                    version="1.1"
                    xmlns="http://www.w3.org/2000/svg"
                    xmlns:xlink="http://www.w3.org/1999/xlink"
                    xmlns:a="http://ns.adobe.com/AdobeSVGViewerExtensions/3.0/"
                    x="0px"
                    y="0px"
                    width="60px"
                    height="60px"
                    viewBox="0 0 213.7 213.7"
                    enable-background="new 0 0 213.7 213.7"
                    xml:space="preserve"
                  >
                    <polygon
                      class="triangle"
                      id="XMLID_18_"
                      fill="none"
                      stroke-width="7"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-miterlimit="10"
                      points="73.5,62.5 148.5,105.8 73.5,149.1 "
                    />

                    <circle
                      class="circle"
                      id="XMLID_17_"
                      fill="none"
                      stroke-width="7"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      stroke-miterlimit="10"
                      cx="106.8"
                      cy="106.8"
                      r="103.3"
                    />
                  </svg>
                </a>
                <p class="subheading ml-2 mb-0">Assista o vídeo</p>
              </div>
            </v-col>
            <v-col cols="12" md="6" xl="4" class="hidden-sm-and-down"> </v-col>
          </v-row>
        </v-col>
      </v-row>
      <div class="svg-border-waves text-white">
        <v-img src="@/assets/img/borderWaves.svg" />
      </div>
    </v-parallax>
    <v-container fluid id="features" class="mt-2">
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="space-around">
            <!-- <v-col cols="12" class="text-center">
              <h1 class="font-weight-light display-2">Title</h1>
              <h1 class="font-weight-light">
                Lorem ipsum dolor sit amet consectetur adipisicing elit.
              </h1>
            </v-col> -->
            <v-col
              cols="12"
              sm="4"
              class="text-center"
              v-for="(feature, i) in features"
              :key="i"
            >
              <v-hover v-slot:default="{ hover }">
                <v-card
                  class="card"
                  shaped
                  :elevation="hover ? 10 : 4"
                  :class="{ up: hover }"
                >
                  <v-img
                    :src="feature.img"
                    max-width="100px"
                    class="d-block ml-auto mr-auto"
                    :class="{ 'zoom-efect': hover }"
                  ></v-img>
                  <h1 class="font-weight-regular">{{ feature.title }}</h1>
                  <h4 class="font-weight-regular subtitle-1">
                    {{ feature.text }}
                  </h4>
                </v-card>
              </v-hover>
            </v-col>
            <v-col
              cols="12"
              sm="4"
              class="text-center"

            >
              <v-hover v-slot:default="{ hover }">
                <v-card
                  class="card"
                  shaped
                  :elevation="hover ? 10 : 4"
                  :class="{ up: hover }"
                >
                  <h1 class="font-weight-regular">Nasabah</h1>
                  <v-sheet
                    class="position-relative"
                    min-height="50"
                  >
                    <div class="position-absolute d-flex align-center justify-center w-100 h-100">
                      <v-btn
                        color="deep-purple-darken-2"
                        size="x-large"
                        @click="dialog = !dialog"
                      >
                        Nasabah
                      </v-btn>
                    </div>
                  </v-sheet>
                </v-card>
              </v-hover>
            </v-col>
            <v-col
              cols="12"
              sm="4"
              class="text-center"

            >
              <v-hover v-slot:default="{ hover }">
                <v-card
                  class="card"
                  shaped
                  :elevation="hover ? 10 : 4"
                  :class="{ up: hover }"
                >
                  <h1 class="font-weight-regular">Non Nasabah</h1>
                  <!-- <h4 class="font-weight-regular subtitle-1">
                    Non Nasabah
                  </h4> -->
                  <v-sheet
                    class="position-relative"
                    min-height="50"
                  >
                    <div class="position-absolute d-flex align-center justify-center w-100 h-100">
                      <v-btn
                        color="deep-purple-darken-2"
                        size="x-large"
                        @click="dialog2 = !dialog2"
                      >
                        Non Nasabah
                      </v-btn>
                    </div>
                  </v-sheet>
                </v-card>
              </v-hover>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
    <v-dialog v-model="dialog" max-width="640px">
      <v-card
        v-if="dialog"
        append-icon="$close"
        class="mx-auto"
        elevation="16"
        max-width="640"
        title="Nasabah"
      >
        <template v-slot:append>
          <v-btn icon="$close" variant="text" @click="dialog = false"></v-btn>
        </template>

        <v-divider></v-divider>

        <div class="py-12 text-center">
          test
          <v-stepper v-model="e1">
            <v-stepper-header>
              <v-stepper-step
                :complete="e1 > 1"
                step="1"
              >
                Name of step 1
              </v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step
                :complete="e1 > 2"
                step="2"
              >
                Name of step 2
              </v-stepper-step>

              <v-divider></v-divider>

              <v-stepper-step step="3">
                Name of step 3
              </v-stepper-step>
            </v-stepper-header>

            <v-stepper-items>
              <v-stepper-content step="1">
                <v-card
                  class="mb-12"
                  height="200px"
                >
                  <v-form ref="form">
                    <v-text-field
                      v-model="nasabah.name.value.value"
                      :counter="10"
                      :error-messages="nasabah.name.errorMessage.value"
                      :rules="[v => !!v || 'Item is required']"
                      label="Nama Lengkap"
                      required
                    ></v-text-field>

                    <v-text-field
                      v-model="nasabah.email.value.value"
                      :error-messages="nasabah.email.errorMessage.value"
                      :rules="[v => !!v || 'Item is required']"
                      label="E-mail"
                      required
                    ></v-text-field>
                    
                    <v-text-field
                      v-model="nasabah.phone.value.value"
                      :counter="7"
                      :error-messages="nasabah.phone.errorMessage.value"
                      :rules="[v => !!v || 'Item is required']"
                      label="Nomor HP"
                      required
                    ></v-text-field>
                    
                    <v-text-field
                      v-model="nasabah.norek.value.value"
                      :error-messages="nasabah.norek.errorMessage.value"
                      :rules="[v => !!v || 'Item is required']"
                      label="Nomor Rekening"
                    ></v-text-field>

                    <!-- <v-btn
                      class="me-4"
                      type="button"
                      @click="aksinya"
                    >
                      submit
                    </v-btn> -->
                  </v-form>
                </v-card>
                <br>
                <v-btn
                  color="primary"
                  @click="e1 = 2"
                >
                  Continue
                </v-btn>

                <v-btn 
                  text
                >
                  Cancel
                </v-btn>
              </v-stepper-content>

              <v-stepper-content step="2">
                <v-card
                  class="mb-12"
                  color="grey lighten-1"
                  height="200px"
                ></v-card>

                <v-btn
                  color="primary"
                  @click="e1 = 3"
                >
                  Continue
                </v-btn>

                <v-btn 
                  @click="e1 = 1"
                >
                  Cancel
                </v-btn>
              </v-stepper-content>

              <v-stepper-content step="3">
                <v-card
                  class="mb-12"
                  color="grey lighten-1"
                  height="200px"
                ></v-card>

                <v-btn
                  color="primary"
                  @click="e1 = 1"
                >
                  Continue
                </v-btn>

                <v-btn text>
                  Cancel
                </v-btn>
              </v-stepper-content>
            </v-stepper-items>
          </v-stepper>
        </div>

        <v-divider></v-divider>

        <div class="pa-4 text-end">
          <v-btn
            class="text-none"
            color="medium-emphasis"
            min-width="92"
            variant="outlined"
            rounded
            @click="dialog = false"
          >
            Close
          </v-btn>
        </div>
      </v-card>
      <!-- <v-card>
        <youtube
          :video-id="videoId"
          @ready="ready"
          @playing="playing"
        ></youtube>
      </v-card> -->
    </v-dialog>
    <v-dialog v-model="dialog2" max-width="640px">
        <v-card
          v-if="dialog2"
          append-icon="$close"
          class="mx-auto"
          elevation="16"
          max-width="640"
          title="Send a receipt"
        >
          <template v-slot:append>
            <v-btn icon="$close" variant="text" @click="dialog = false"></v-btn>
          </template>

          <v-divider></v-divider>

          <div class="py-12 text-center">
            <form ref="form">
              <v-text-field
                v-model="nonnasabah.name.value.value"
                :counter="10"
                :error-messages="nonnasabah.name.errorMessage.value"
                label="Nama Lengkap"
                required
              ></v-text-field>

              <v-text-field
                v-model="nonnasabah.email.value.value"
                :error-messages="nonnasabah.email.errorMessage.value"
                label="E-mail"
                required
              ></v-text-field>
              
              <v-text-field
                v-model="nonnasabah.phone.value.value"
                :counter="7"
                :error-messages="nonnasabah.phone.errorMessage.value"
                label="Nomor HP"
                required
              ></v-text-field>
              
              <v-text-field
                v-model="nonnasabah.norek.value.value"
                :error-messages="nonnasabah.norek.errorMessage.value"
                label="Nomor Rekening"
                required
              ></v-text-field>

              <v-btn
                class="me-4"
                type="button"
                @click="aksinya2"
              >
                submit
              </v-btn>
            </form>
          </div>

          <v-divider></v-divider>

          <div class="pa-4 text-end">
            <v-btn
              class="text-none"
              color="medium-emphasis"
              min-width="92"
              variant="outlined"
              rounded
              @click="dialog2 = false"
            >
              Close
            </v-btn>
          </div>
        </v-card>
    </v-dialog>
    <div class="svg-border-waves">
      <img src="~@/assets/img/wave2.svg" />
    </div>
  </section>
</template>

<script>
export default {

  data() {
    return {
      nasabah: {
        name: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        phone: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        select: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        email: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        norek: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
      },
      nonnasabah: {
        name: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        phone: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        select: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        email: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
        norek: {
          value: {
            value: "",
          },
          errorMessage: {
            value: [],
          },
        },
      },
      datanya: '',
      dialog: false,
      dialog2: false,
      konsul: false,
      tab:null,
      videoId: "i8IvvHJssWE",
      features: [
        {
          img: require("@/assets/img/icon2.png"),
          title: "Design Limpo",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
        {
          img: require("@/assets/img/icon1.png"),
          title: "Dados Seguros",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
        {
          img: require("@/assets/img/icon3.png"),
          title: "Código Aberto",
          text: "Lorem ipsum dolor sit amet consectetur adipisicing elit.",
        },
      ],
      e1: 1,
    };
  },
  watch: {
    // dialog(value) {
    //   // if (!value) {
    //   //   this.pause();
    //   // }
    // },
  },
  methods: {
    ready(event) {
      // this.player = event.target;
    },
    playing(event) {
      // The player is playing a video.
    },
    subimt() {
    close();
    },
    change() {
      // when you change the value, the player will also change.
      // If you would like to change `playerVars`, please change it before you change `videoId`.
      // If `playerVars.autoplay` is 1, `loadVideoById` will be called.
      // If `playerVars.autoplay` is 0, `cueVideoById` will be called.
      this.videoId = "another video id";
    },
    stop() {
      this.player.stopVideo();
    },
    pause() {
      // this.player.pauseVideo();
    },
    async aksinya() {
      // console.log(this.$refs.form.aksinya());
      // const { valid } = await this.$refs;

      console.log(this.konsul);
      this.datanya = this.nasabah;
      
      // if (valid) alert('Form is valid')
      console.log(this.datanya);
    },
    async validate () {
      const { valid } = await this.$refs.form.validate()

      if (valid) alert('Form is valid')
    },
    reset () {
      this.$refs.form.reset()
    },
    resetValidation () {
      this.$refs.form.resetValidation()
    },
    handleSubmit() {
      // validate form
      if (!this.$v.$invalid) {
        // submit form
        console.log('Form submitted successfully');
      } else {
        this.$v.$touch(); // touch all fields to display error messages
        console.log('Form has errors, please correct them.');
      }
    }
  },
  computed: {
    subtotal () {
      return this.products.reduce((acc, product) => acc + product.quantity * product.price, 0)
    },
    total () {
      return this.subtotal + Number(this.shipping ?? 0)
    },
  }
};
</script>

<style lang="scss">
.circle {
  stroke: white;
  stroke-dasharray: 650;
  stroke-dashoffset: 650;
  -webkit-transition: all 0.5s ease-in-out;
  opacity: 0.3;
}

.playBut {
  /*  border: 1px solid red;*/
  display: inline-block;
  -webkit-transition: all 0.5s ease;

  .triangle {
    -webkit-transition: all 0.7s ease-in-out;
    stroke-dasharray: 240;
    stroke-dashoffset: 480;
    stroke: white;
    transform: translateY(0);
  }

  &:hover {
    .triangle {
      stroke-dashoffset: 0;
      opacity: 1;
      stroke: white;
      animation: nudge 0.7s ease-in-out;

      @keyframes nudge {
        0% {
          transform: translateX(0);
        }
        30% {
          transform: translateX(-5px);
        }
        50% {
          transform: translateX(5px);
        }
        70% {
          transform: translateX(-2px);
        }
        100% {
          transform: translateX(0);
        }
      }
    }

    .circle {
      stroke-dashoffset: 0;
      opacity: 1;
    }
  }
}
</style>

<style>
.btn-play {
  transition: 0.2s;
}

.svg-border-waves .v-image {
  position: absolute;
  bottom: 0;
  left: 0;
  height: 3rem;
  width: 100%;
  overflow: hidden;
}

#hero {
  z-index: 0;
}
.svg-border-waves img {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  margin-bottom: -2px;
  z-index: -1;
}

.card {
  min-height: 300px;
  padding: 10px;
  transition: 0.5s ease-out;
}

.card .v-image {
  margin-bottom: 15px;
  transition: 0.75s;
}

.card h1 {
  margin-bottom: 10px;
}

.zoom-efect {
  transform: scale(1.1);
}

.up {
  transform: translateY(-20px);
  transition: 0.5s ease-out;
}
</style>

<style>
section {
  position: relative;
}
</style>
