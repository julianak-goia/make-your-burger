<script setup>
// import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <!-- <header>
    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header> -->

  <div class="grid grid-cols-3 gap-8">
    <div class="col-span-1 bg-stone-500">
      <h3>imagens</h3>
    </div>

    <div class="col-span-2">
      <div class="mb-8 text-center">
        <h1 class="text-6xl text-white">Make Your Burger</h1>
        <h4 class="text-2xl text-white mt-2">Choose your ingredientes:</h4>
      </div>

      <div
        class="border-2 border-solid border-white p-8 gap-8"
      >
        <!-- Tipo do pão -->
        <div class="element-card">
          <h4 class="text-white">TIPO DO PÃO</h4>
          <div class="flex items-center gap-2">
            <div>
              <input type="radio" />
              <label class="text-white ml-2">Gergelim</label>
            </div>
            <div>
              <div>
                <input type="radio" />
                <label class="text-white ml-2">Australiano</label>
              </div>
            </div>
          </div>
        </div>
        <!-- Tipo do salada -->
        <div class="element-card mt-8">
          <h4 class="text-white">SALADAS</h4>
          <div>
            <input type="radio" />
            <label class="text-white ml-2">Alface</label>
          </div>
        </div>
        <!-- Tipo do molho -->
        <div class="element-card mt-8">
          <h4 class="text-white">MOLHOS</h4>
          <div class="flex items-center gap-2">
            <div>
              <input type="checkbox" />
              <label class="text-white ml-2">Ketchup</label>
            </div>
            <div>
              <input type="checkbox" />
              <label class="text-white ml-2">Mostarda</label>
            </div>
            <div>
              <input type="checkbox" />
              <label class="text-white ml-2">Maionese</label>
            </div>
          </div>
        </div>
        <!-- Tipo do hamburguer -->
        <div class="element-card mt-8">
          <h4 class="text-white">TIPO DE HAMBURGUER</h4>
          <div class="flex items-center gap-2">
            <div>
              <input type="radio" />
              <label class="text-white ml-2">Bovino</label>
            </div>
            <div>
              <input type="radio" />
              <label class="text-white ml-2">Frango</label>
            </div>
            <div>
              <input type="radio" />
              <label class="text-white ml-2">Soja</label>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.burger-elements {
  border: 2px solid #ffffff;
  padding: 2rem;
}

/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
