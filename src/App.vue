<script setup>
import PageTitle from "./components/PageTitle.vue";
</script>

<template>
  <div class="container mx-auto h-screen flex items-center justify-center">
    <div class="grid grid-cols-3 gap-8 w-full h-full py-20">
      <div class="col-span-1 flex justify-center burger-image items-center">
        <div class="elements-wrapper relative">
          <img :src="pao[0]" class="pao-superior" />
          <img :src="cebola" class="cebola" />
          <img :src="tomate" class="tomate" />
          <img :src="alface" class="alface" />
          <img :src="hamburguer" class="burger" />
          <img :src="queijo" class="queijo" />
          <img :src="pao[1]" class="pao-inferior" />

          <!-- molhos -->
          <img :src="ketchup" class="molho ketchup" />
          <img :src="maionese" class="molho maionese" />
          <img :src="mostarda" class="molho mostarda" />
        </div>
      </div>

      <div class="col-span-2">
        <div class="mb-8 text-center">
          <PageTitle
            title="Make Your Burger"
            description="Choose your ingredientes:"
          />
        </div>

        <div class="bg-white opacity-90 p-8 gap-8">
          <!-- Tipo do pão -->
          <div class="element-card">
            <h4>TIPO DO PÃO</h4>
            <div class="flex items-center gap-4">
              <div>
                <input v-model="inputTipoPao" type="radio" value="gergelim" />
                <label class="ml-2">Gergelim</label>
              </div>
              <div>
                <input
                  v-model="inputTipoPao"
                  type="radio"
                  value="australiano"
                />
                <label class="ml-2">Australiano</label>
              </div>
            </div>
          </div>
          <!-- Toppings -->
          <div class="element-card mt-8">
            <h4>TOPPINGS</h4>
            <div class="flex items-center gap-4">
              <div>
                <input v-model="inputSalada" type="checkbox" value="alface" />
                <label class="ml-2">Alface</label>
              </div>
              <div>
                <input v-model="inputSalada" type="checkbox" value="tomate" />
                <label class="ml-2">Tomate</label>
              </div>
              <div>
                <input v-model="inputSalada" type="checkbox" value="queijo" />
                <label class="ml-2">Queijo</label>
              </div>
              <div>
                <input v-model="inputSalada" type="checkbox" value="cebola" />
                <label class="ml-2">Cebola</label>
              </div>
            </div>
          </div>
          <!-- Tipo do molho -->
          <div class="element-card mt-8">
            <h4>MOLHOS</h4>
            <div class="flex items-center gap-4">
              <div>
                <input v-model="inputMolhos" type="checkbox" value="ketchup" />
                <label class="ml-2">Ketchup</label>
              </div>
              <div>
                <input v-model="inputMolhos" type="checkbox" value="mostarda" />
                <label class="ml-2">Mostarda</label>
              </div>
              <div>
                <input v-model="inputMolhos" type="checkbox" value="maionese" />
                <label class="ml-2">Maionese</label>
              </div>
            </div>
          </div>
          <!-- Tipo do hamburguer -->
          <div class="element-card mt-8">
            <h4>TIPO DE HAMBURGUER</h4>
            <div class="flex items-center gap-4">
              <div>
                <input v-model="inputHamburguer" type="radio" value="bovino" />
                <label class="ml-2">Bovino</label>
              </div>
              <div>
                <input v-model="inputHamburguer" type="radio" value="frango" />
                <label class="ml-2">Frango</label>
              </div>
              <div>
                <input v-model="inputHamburguer" type="radio" value="soja" />
                <label class="ml-2">Soja</label>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    inputTipoPao: "",
    inputSalada: [],
    inputMolhos: [],
    inputHamburguer: "",
    etapa: 1,
    inputNome: "",
    inputEndereco: "",
    novoPedidoAssincrono: null,
  }),

  computed: {
    pao() {
      switch (this.inputTipoPao) {
        case "gergelim":
          return [
            "/src/assets/images/burger/pao-gergelim-superior.svg",
            "/src/assets/images/burger/pao-gergelim-inferior.svg",
          ];
        case "australiano":
          return [
            "/src/assets/images/burger/pao-australiano-superior.svg",
            "/src/assets/images/burger/pao-australiano-inferior.svg",
          ];
        default:
          return [
            "/src/assets/images/burger-base/pao-base-superior.svg",
            "/src/assets/images/burger-base/pao-base-inferior.svg",
          ];
      }
    },

    alface() {
      if (this.inputSalada.includes("alface")) {
        return "/src/assets/images/burger/alface.svg";
      }
      return "/src/assets/images/burger-base/alface-base.svg";
    },

    tomate() {
      if (this.inputSalada.includes("tomate")) {
        return "/src/assets/images/burger/tomate.svg";
      }
      return "/src/assets/images/burger-base/tomate-base.svg";
    },

    queijo() {
      if (this.inputSalada.includes("queijo")) {
        return "/src/assets/images/burger/queijo.svg";
      }
      return "/src/assets/images/burger-base/queijo-base.svg";
    },

    cebola() {
      if (this.inputSalada.includes("cebola")) {
        return "/src/assets/images/burger/cebola.svg";
      }
      return "/src/assets/images/burger-base/cebola-base.svg";
    },

    ketchup() {
      if (this.inputMolhos.includes("ketchup")) {
        return "/src/assets/images/burger/ketchup.svg";
      }
      return "";
    },

    maionese() {
      if (this.inputMolhos.includes("maionese")) {
        return "/src/assets/images/burger/maionese.svg";
      }
      return "";
    },

    mostarda() {
      if (this.inputMolhos.includes("mostarda")) {
        return "/src/assets/images/burger/mostarda.svg";
      }
      return "";
    },

    hamburguer() {
      switch (this.inputHamburguer) {
        case "bovino":
          return "/src/assets/images/burger/burger-bovino.svg";
        case "frango":
          return "/src/assets/images/burger/burger-frango.svg";
        case "soja":
          return "/src/assets/images/burger/burger-soja.svg";
        default:
          return "/src/assets/images/burger-base/burger-base.svg";
      }
    },
  },
};
</script>

<style scoped lang="css">
.elements-wrapper {
  width: 48%;
  display: flex;
  flex-direction: column;
}

img:not(:first-child) {
  margin-top: -1rem;
}

.molho {
  width: 50%;
}

.ketchup {
  position: absolute;
  bottom: 5%;
  left: -55%;
  z-index: 0;
}

.maionese {
  position: absolute;
  bottom: -5%;
  right: -38%;
  z-index: 0;
}

.mostarda {
  position: absolute;
  bottom: 7%;
  right: -60%;
  z-index: -2;
}

.pao-superior {
  z-index: 6;
}

.cebola {
  z-index: 5;
}

.tomate {
  z-index: 4;
}

.alface {
  z-index: 3;
  margin-top: -1.5rem !important;
}

.burger {
  z-index: 2;
  margin-top: -2.5rem !important;
}

.queijo {
  z-index: 1;
  margin-top: -1.5rem !important;
}

.pao-inferior {
  z-index: 0;
  margin-top: -2.5rem !important;
}
/* @media (min-width: 1024px) {
  
} */
</style>
