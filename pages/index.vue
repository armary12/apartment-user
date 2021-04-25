<template>
<v-container grid-list-md>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center ma-4">
        <v-card>
          <v-row>
            <v-col cols="12" sm="4" align-self="center">
              <v-avatar size="50" color="grey"></v-avatar>
            </v-col>
            <v-col cols="12" sm="4">
              <v-list-item two-line>
                <v-list-item-content>
                  <v-list-item-title>ห้อง 3310</v-list-item-title>
                  <v-list-item-subtitle>คุณชลทิศ จิตรบุตรร</v-list-item-subtitle>
                </v-list-item-content>
              </v-list-item>
            </v-col>
          </v-row>
        </v-card>
      </div>
      <v-card class="ma-4">
        <v-row>
          <v-col align-self="center"><v-icon class="ml-15" color="yellow darken-2">mdi-flash</v-icon></v-col>
          <v-col align-self="center">203 Baht</v-col>
          <v-col align-self="center"><v-icon class="ml-15" color="blue">mdi-water</v-icon></v-col>
          <v-col align-self="center">30 Baht</v-col>
        </v-row>
      </v-card>
      <v-card class="ma-4">
        <v-list two-line>
          <v-list-item-group
            v-model="selected"
            active-class="pink--text"
            multiple
          >
            <template v-for="(item, index) in items">
              <v-list-item :key="item.title">
                <template v-slot:default="{ active }">
                  <v-list-item-content>
                    <v-list-item-title v-text="item.title"></v-list-item-title>

                    <v-list-item-subtitle
                      class="text--primary"
                      v-text="item.headline"
                    ></v-list-item-subtitle>

                    <v-list-item-subtitle>จำนวนเงิน : {{
                      item.subtitle
                     }} บาท</v-list-item-subtitle>
                  </v-list-item-content>

                  <v-list-item-action>
                    <v-list-item-action-text
                      v-text="item.action"
                    ></v-list-item-action-text>

                    <v-btn class="ma-2" v-if="active"> แจ้งชำระ</v-btn>
                    <v-icon v-if="!active" color="orange lighten-1">
                      mdi-check
                    </v-icon>

                    <v-icon v-else color="red darken-3">
                      mdi-close-outline
                    </v-icon>
                  </v-list-item-action>
                </template>
              </v-list-item>

              <v-divider
                v-if="index < items.length - 1"
                :key="index"
              ></v-divider>
            </template>
          </v-list-item-group>
        </v-list>
      </v-card>
    </v-col>
  </v-row>
  </v-container>

</template>

<script>
export default {
  components: {},
  data: () => ({
    selected: [2],
    items: [
      {
        action: "ยังไม่ชำระ",
        headline: "ห้อง 3310",
        subtitle: `2455`,
        title: "มิถุนายน"
      },
      {
        action: "ชำระแล้ว",
        headline: "ห้อง 3310",
        subtitle: `2784`,
        title: "เมษายน"
      },
      {
        action: "ชำระแล้ว",
        headline: "ห้อง 3310",
        subtitle: "3056",
        title: "มีนาคม"
      },
      {
        action: "ชำระแล้ว",
        headline: "ห้อง 3310",
        subtitle: "2400",
        title: "กุมภาพันธ์"
      },
      {
        action: "ชำระแล้ว",
        headline: "ห้อง 3310",
        subtitle: "2592",
        title: "มกราคม"
      }
    ]
  })
};
</script>
