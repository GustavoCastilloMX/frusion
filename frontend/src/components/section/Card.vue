<template>
  <v-card elevation="3">
    <v-img src="../../assets/img/producto.png"></v-img>
    <v-divider></v-divider>
    <v-card-title class="d-flex justify-center">
      <h4>Papaya maradol</h4>
    </v-card-title>
    <v-card-text class="d-flex justify-center">
      <strong>$29.90/kg</strong>
    </v-card-text>
    <v-card-actions class="card-actions-size">
      <v-row>
        <v-col v-if="!showBtnCustomized" @click="showAll" cols="12">
          <v-btn block depressed color="success">
            <v-icon left>mdi-cart-plus</v-icon>Agregar
          </v-btn>
        </v-col>
        <v-col v-if="showBtnCustomized" cols="12">
          <BtnCustomized />
        </v-col>
      </v-row>
    </v-card-actions>
    <v-snackbar color="grey darken-3" right v-model="showSnackBar"><span class="font-weight-medium">Producto agregado</span> <v-btn
        color="primary"
        icon
        @click="showSnackBar = false"
      >
      <v-icon>mdi-close</v-icon>
      </v-btn>  </v-snackbar>
  </v-card>
</template>

<script>
export default {
  data: () => ({
    showBtnCustomized: false,
    showSnackBar: false
  }),
  components: {
    BtnCustomized: () => import("./BtnCustomized")
  },
  methods: {
    showAll() {
      this.showBtnCustomized = true;
      this.showSnackBar = true;
    }
  }
};
</script>

<style lang="scss" scoped>
.card-actions-size {
  height: 88px;
}
</style>