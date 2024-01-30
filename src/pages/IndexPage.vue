<script setup>
import { ref } from 'vue';
import FooterComponent from 'src/components/FooterComponent.vue';

const dialog = ref(false)
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

const contact = () => {
  console.log('abriendo modal imaginario');
}
</script>

<template>
  <q-page>
    <!-- Intro -->
    <div id="intro" class="row items-center justify-center">
      <div class="logo col-10 col-md-5 flex column items-center">
        <img data-aos="zoom-in" data-aos-duration="1000" data-aos-easing="ease" alt="Fulcro"
          src="../assets/logo-fulcro-home.jpeg" style="width: 350px; height: 350px">

        <div data-aos="zoom-in" data-aos-duration="1000" data-aos-delay="500" data-aos-easing="ease"
          class="flex column items-center q-mt-md">
          <p class="text-center q-mb-none">"Dame un punto de apoyo y moveré el mundo"</p>
          <span class="text-italic">(Arquímedes 287-212 AC)</span>
        </div>
      </div>

      <div data-aos="zoom-in-left" data-aos-duration="1000" data-aos-easing="ease" data-aos-delay="1000"
        class="intro-text col-10 col-md-5">
        <h4 class="q-my-none">Somos tu punto de <span>Apoyo</span> donde <span>Productores y Distribuidores</span>
          encuentran el mejor apalancamiento en el comercio mayorista regional en alimentos con alto valor agregado.</h4>

        <button @click="dialog = true" class="q-mt-lg btn-contact">Contactanos</button>
        <!-- Modal de contacto -->
        <q-dialog v-model="dialog">
          <q-card>
            <q-card-section class="row items-center q-pb-none">
              <div class="text-body1">Completá estos pocos datos y te contactaremos a la brevedad.</div>
              <q-space />
              <q-btn icon="close" flat round dense v-close-popup />
            </q-card-section>

            <q-card-section>
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate voluptas eveniet
              porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam exercitationem aut, natus minima, porro
              labore.
            </q-card-section>
          </q-card>
        </q-dialog>
      </div>
    </div>

    <!-- Marcas  -->
    <div id="marcas">
      <div class="row container q-mb-xl">
        <div class="col-auto q-mx-auto">
          <div class="flex justify-center items-center q-gutter-md q-col-gutter-x-lg q-col-gutter-y-sm">
            <div v-for="imagen in imagenes" :key="imagen.marca" class="col-3 col-md-4">
              <img data-aos="zoom-in" data-aos-once="true" data-aos-easing="ease-in-sine" :data-aos-duration="500"
                data-offset="400" :data-aos-delay="imagen.tiempo" :src="imagen.src" :alt="imagen.marca" />
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

  .logo {
    font-family: $taviraj;
    font-style: italic;
    font-weight: 300;
    font-size: clamp(0.9rem, 1.4vw, 3rem);

  }

  .intro-text {
    position: relative;
    margin-top: -10rem;

    h4 {
      font-family: $taviraj;
      font-size: clamp(1rem, 1.85vw, 3rem);
      line-height: 2rem;
      font-weight: 300;
      font-style: italic;

      span {
        font-size: clamp(1.35rem, 2vw, 2rem);
        font-weight: 800;
        font-family: $montserrat;
        font-style: normal;
        color: #515151;
      }
    }

    .btn-contact {
      font-family: $montserrat;
      font-size: clamp(1rem, 1.2vw, 2rem);
      text-transform: uppercase;
      cursor: pointer;
      font-weight: 600;
      border: 2px solid $blue-grey-10;
      padding: 7px 30px;
      background-color: transparent;
      transition: all .15s ease-in-out;

      &:hover {
        background-color: $blue-grey-10;
        color: white;
      }
    }

  }

}

#marcas {
  height: auto;
  max-width: 992px;
  margin: 0 auto;

  img {
    max-width: 300px;
  }
}

@media screen and (min-width: 1023.98px) {
  #intro {

    .intro-text {
      margin-top: 0;
    }
  }

  #marcas {
    max-width: 992px;

    img {
      max-width: 250px;
    }
  }
}

@media screen and (min-width: 1279.98px) {
  #marcas {
    max-width: 960px;

    img {
      max-width: 230px;
    }
  }
}

@media screen and (min-width: 1365.98px) {
  #marcas {


    img {
      max-width: 250px;
    }
  }
}

@media screen and (min-width: 1599.98px) {
  #marcas {
    max-width: 1100px;

  }
}</style>
