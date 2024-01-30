<script setup>
import FooterComponent from 'src/components/FooterComponent.vue';
import { ref } from 'vue';

const imagenes = ref([

  {
    marca: 'Masseube',
    src: 'src/assets/marcas/masseube.jpg',
    tiempo: 100
  },
  {
    marca: 'Chocolate Colonial',
    src: 'src/assets/marcas/colonial.jpg',
    tiempo: 400
  },
  {
    marca: 'Pariggi',
    src: 'src/assets/marcas/pariggi.jpg',
    tiempo: 700
  },
  {
    marca: 'Pollo Cocido',
    src: 'src/assets/marcas/pollo-cocido.jpg',
    tiempo: 1000
  },
  {
    marca: 'Inti Zen',
    src: 'src/assets/marcas/inti-zen.jpg',
    tiempo: 1300
  },
  {
    marca: 'Gauchada',
    src: 'src/assets/marcas/gauchada.jpg',
    tiempo: 1600
  },
  {
    marca: 'Sendero Sur',
    src: 'src/assets/marcas/senderoSur.jpg',
    tiempo: 1900
  },
  {
    marca: '27',
    src: 'src/assets/marcas/27.jpg',
    tiempo: 2200
  },
  {
    marca: 'Michelob',
    src: 'src/assets/marcas/michelob.jpg',
    tiempo: 2500
  },
  {
    marca: 'Inti Zen',
    src: 'src/assets/marcas/verde-negro.jpg',
    tiempo: 2800
  },
  {
    marca: 'Inti Hebras',
    src: 'src/assets/marcas/inti-hebras.jpg',
    tiempo: 3100
  },
  {
    marca: 'Smoke Cave',
    src: 'src/assets/marcas/smoke.jpg',
    tiempo: 3400
  }
])
</script>

<template>
  <q-page>
    <!-- Intro -->
    <div id="intro" class="flex column items-center justify-center">
      <img alt="Fulcro" src="../assets/logo-fulcro-home.jpeg" style="width: 400px; height: 400px">
      <p class="text-center">Dame un punto de apoyo y moveré el mundo.</p>
      <span class="text-italic">(Arquímedes 287-212 AC)</span>
    </div>

    <!-- Marcas  -->
    <div id="marcas">
      <div class="row container q-mb-xl">
        <div class="col-auto q-mx-auto">
          <div class="flex justify-center items-center q-gutter-md">
            <div v-for="imagen in imagenes" :key="imagen.marca" class="col-3">
              <img data-aos="zoom-in" :data-aos-duration="imagen.tiempo" data-offset="200" :src="imagen.src" :alt="imagen.marca" />
            </div>
          </div>
        </div>
      </div>
    </div>

    <FooterComponent />
  </q-page>
</template>

<style lang="scss">
#intro {
  height: 100vh;
  font-family: $montserrat;
  color: $blue-10;

}

#marcas {
  max-width: 992px;
  margin: 0 auto;
}

@media screen and (min-width: 1023.98px) {
  #marcas {

    img{
      max-width: 250px;
    }
  }
}

@media screen and (min-width: 1279.98px) {
  #marcas {
    max-width: 1200px;

    img{
      max-width: 275px;
    }
  }
}

@media screen and (min-width: 1365.98px) {
  #marcas {
    max-width: 1280px;
  }
}
</style>
