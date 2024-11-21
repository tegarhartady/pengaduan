<template>
  <section id="about">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="7">
              <h1 class="font-weight-light display-2">Sobre</h1>
              <h1 class="font-weight-light display-1 mb-3">Lorem ipsum dolor!</h1>
              <v-row>
                <v-col cols="12" class="d-flex align-center">
                  <v-img src="@/assets/img/icon1.svg" max-width="60px" class="mr-4" />
                  <p class="text-justify">
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit. Lorem ipsum
                    dolor sit amet consectetur, adipisicing elit. Lorem ipsum dolor sit
                    amet consectetur, adipisicing elit.
                  </p>
                </v-col>
                <v-col cols="12" class="d-flex align-center">
                  <v-img src="@/assets/img/icon2.svg" max-width="60px" class="mr-4" />
                  <p class="text-justify">
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit. Lorem ipsum
                    dolor sit amet consectetur, adipisicing elit. Lorem ipsum dolor sit
                    amet consectetur, adipisicing elit.
                  </p>
                </v-col>
                <v-col cols="12" class="d-flex align-center">
                  <v-img src="@/assets/img/icon3.svg" max-width="60px" class="mr-4" />
                  <p class="text-justify">
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit. Lorem ipsum
                    dolor sit amet consectetur, adipisicing elit. Lorem ipsum dolor sit
                    amet consectetur, adipisicing elit.
                  </p>
                </v-col>
                <v-col cols="12" class="d-flex align-center">
                  <v-tabs
                    v-model="tab"
                    :items="tabs"
                    align-tabs="center"
                    color="white"
                    height="60"
                    slider-color="#f78166"
                  >
                    <template v-slot:tab="{ item }">
                      <v-tab
                        :prepend-icon="item.icon"
                        :text="item.text"
                        :value="item.value"
                        class="text-none"
                      ></v-tab>
                    </template>

                    <template v-slot:item="{ item }">
                      <v-tabs-window-item :value="item.value" class="pa-4">
                        Lorem ipsum dolor sit amet consectetur adipisicing elit. Commodi,
                        ratione debitis quis est labore voluptatibus! Eaque cupiditate
                        minima, at placeat totam, magni doloremque veniam neque porro
                        libero rerum unde voluptatem!
                      </v-tabs-window-item>
                    </template>
                  </v-tabs>
                </v-col>
              </v-row>
            </v-col>
            <v-col cols="12" md="5" class="d-none d-md-flex">
              <v-img
                src="@/assets/img/ill1.svg"
                class="d-block ml-auto mr-auto"
                max-width="400px"
              />
            </v-col>
            <v-col cols="12" md="5" class="d-none d-md-flex"> </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>
<script>
export default {
  data: () => ({
    tab: "tab-1",
    tabs: [
      {
        icon: "mdi-book-open-page-variant",
        text: "Readme",
        value: "tab-1",
      },
      {
        icon: "mdi-handshake-outline",
        text: "Code of Conduct",
        value: "tab-2",
      },
      {
        icon: "mdi-license",
        text: "MIT License",
        value: "tab-3",
      },
      {
        icon: "mdi-shield-lock-outline",
        text: "Security",
        value: "tab-4",
      },
    ],
  }),
};
</script>

<style scoped>
#about {
  background-color: #f4f7f5;
}
</style>
