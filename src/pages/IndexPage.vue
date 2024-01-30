<script setup>
import FooterComponent from 'src/components/FooterComponent.vue';
import { ref } from 'vue';

const imagenes = ref([

  {
    marca: 'Masseube',
    src: 'src/assets/marcas/masseube.jpg',
    tiempo: 250
  },
  {
    marca: 'Chocolate Colonial',
    src: 'src/assets/marcas/colonial.jpg',
    tiempo: 500
  },
  {
    marca: 'Inti Zen',
    src: 'src/assets/marcas/inti-zen.jpg',
    tiempo: 750
  },
  {
    marca: 'Molé',
    src: 'src/assets/marcas/mole.jpg',
    tiempo: 1000
  },
  {
    marca: 'Samkya',
    src: 'src/assets/marcas/samkya.jpg',
    tiempo: 1250
  },
  {
    marca: 'Pirenco Patagonia',
    src: 'src/assets/marcas/pirenco.jpeg',
    tiempo: 1500
  },
  {
    marca: 'Pollo Cocido',
    src: 'src/assets/marcas/pollo-cocido.jpg',
    tiempo: 1750
  },
  {
    marca: 'Pariggi',
    src: 'src/assets/marcas/pariggi.jpg',
    tiempo: 2000
  },
  {
    marca: 'Smoke Cave',
    src: 'src/assets/marcas/smoke.jpg',
    tiempo: 2250
  }
])
</script>

<template>
  <q-page>
    <!-- Intro -->
    <div id="intro" class="flex column items-center justify-center">
      <img data-aos="zoom-in" data-aos-duration="1000" data-aos-easing="ease" alt="Fulcro" src="../assets/logo-fulcro-home.jpeg" style="width: 350px; height: 350px">

      <div class="flex column items-center q-mt-md">
        <p class="text-center q-mb-none">"Dame un punto de apoyo y moveré el mundo"</p>
        <span class="text-italic">(Arquímedes 287-212 AC)</span>
      </div>
    </div>

    <!-- Marcas  -->
    <div id="marcas">
      <div class="row container q-mb-xl">
        <div class="col-auto q-mx-auto">
          <div class="flex justify-center items-center q-gutter-md q-col-gutter-x-lg q-col-gutter-y-sm">
            <div v-for="imagen in imagenes" :key="imagen.marca" class="col-3 col-md-4">
              <img data-aos="zoom-in" data-aos-once="true" data-aos-easing="ease-in-sine" :data-aos-duration="500" data-offset="400" :data-aos-delay="imagen.tiempo" :src="imagen.src" :alt="imagen.marca" />
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

  p{
    font-size: clamp(1rem, 1vw, 2rem);
  }

}

#marcas {
  height: auto;
  max-width: 992px;
  margin: 0 auto;

  img{
    max-width: 300px;
  }
}

@media screen and (min-width: 1023.98px) {
  #marcas {
    max-width: 992px;

    img{
      max-width: 250px;
    }
  }
}

@media screen and (min-width: 1279.98px) {
  #marcas {
    max-width: 960px;

    img{
      max-width: 230px;
    }
  }
}

@media screen and (min-width: 1365.98px) {
  #marcas {


    img{
      max-width: 250px;
    }
  }
}

@media screen and (min-width: 1599.98px) {
  #marcas {
    max-width: 1100px;

  }
}
</style>
