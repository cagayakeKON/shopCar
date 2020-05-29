<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>购物车</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-contact-mail</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>个人信息</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app color="green" dark>
      <v-toolbar-title>点餐系统</v-toolbar-title>
       <v-spacer />
    </v-app-bar>

    <v-content>
      <v-container class="fill-height" fluid>
        <v-row>
          <v-col v-for="n in 3" :key="n" cols="12" md="4">
            <v-card class="mx-auto" max-width="344" outlined>
              <v-list-item three-line>
                <v-list-item-content>
                  <div class="overline mb-4">产品</div>
                  <v-list-item-title class="headline mb-1">包子</v-list-item-title>
                  <v-list-item-subtitle>
                    包子
                  </v-list-item-subtitle>
                </v-list-item-content>

                <v-list-item-avatar tile size="80" color="grey"> <v-img src="data:image/jpeg;base64,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" aspect-ratio="1.7"></v-img></v-list-item-avatar>
              </v-list-item>

              <v-card-actions>
                <v-btn text>加入购物车</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
         <v-row>
          <v-col v-for="n in 3" :key="n" cols="12" md="4">
            <v-card class="mx-auto" max-width="344" outlined>
              <v-list-item three-line>
                <v-list-item-content>
                  <div class="overline mb-4">OVERLINE</div>
                  <v-list-item-title class="headline mb-1">Headline 5</v-list-item-title>
                  <v-list-item-subtitle>
                    Greyhound divisely hello coldly
                    fonwderfully
                  </v-list-item-subtitle>
                </v-list-item-content>

                <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
              </v-list-item>

              <v-card-actions>
                <v-btn text>Button</v-btn>
                <v-btn text>Button</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
         <v-row>
          <v-col v-for="n in 3" :key="n" cols="12" md="4">
            <v-card class="mx-auto" max-width="344" outlined>
              <v-list-item three-line>
                <v-list-item-content>
                  <div class="overline mb-4">OVERLINE</div>
                  <v-list-item-title class="headline mb-1">Headline 5</v-list-item-title>
                  <v-list-item-subtitle>
                    Greyhound divisely hello coldly
                    fonwderfully
                  </v-list-item-subtitle>
                </v-list-item-content>

                <v-list-item-avatar tile size="80" color="grey"></v-list-item-avatar>
              </v-list-item>

              <v-card-actions>
                <v-btn text>Button</v-btn>
                <v-btn text>Button</v-btn>
              </v-card-actions>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
export default {
  props: {
    source: String
  },
  data: () => ({
    drawer: null
  })
};
</script>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {}
};
</script>
