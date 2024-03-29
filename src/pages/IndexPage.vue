<script setup>
import { ref } from 'vue';
import FooterComponent from 'src/components/FooterComponent.vue';

const nombre = ref(null)
const email = ref(null)
const mobile = ref(null)
const dialog = ref(false)
const imagenes = ref([

  {
    marca: 'Masseube',
    src: '/marcas/masseube.jpg',
    tiempo: 250
  },
  {
    marca: 'Chocolate Colonial',
    src: '/marcas/colonial.jpg',
    tiempo: 500
  },
  {
    marca: 'Inti Zen',
    src: '/marcas/inti-zen.jpg',
    tiempo: 750
  },
  {
    marca: 'Molé',
    src: '/marcas/mole.jpg',
    tiempo: 1000
  },
  {
    marca: 'Samkya',
    src: '/marcas/samkya.jpg',
    tiempo: 1250
  },
  {
    marca: 'Pirenco Patagonia',
    src: '/marcas/pirenco.jpeg',
    tiempo: 1500
  },
  {
    marca: 'Pollo Cocido',
    src: '/marcas/pollo-cocido.jpg',
    tiempo: 1750
  },
  {
    marca: 'Pariggi',
    src: '/marcas/pariggi.jpg',
    tiempo: 2000
  },
  {
    marca: 'Smoke Cave',
    src: '/marcas/smoke.jpg',
    tiempo: 2250
  }
])
const rulesEmail = [
  (v) => !!v || "El e-mail es requerido",
  (v) => /.+@.+\..+/.test(v) || "El e-mail debe ser válido",
];
const nombreRules = [
  (v) => !!v || "Nombre es requerido",
  (v) => (v && v.length <= 30) || "El nombre debe contener menos de 30 caracteres",
];
const rulesMobile = [
  (v) => !!v || "El numero de móvil es requerido",
];

const enviarMensaje = () => {
  console.log('enviando mensaje');
}
</script>

<template>
  <q-page>
    <!-- Intro -->
    <div id="intro" class="row items-center justify-center">
      <div class="logo col-10 col-md-5 col-lg-5 flex column items-center">
        <img data-aos="zoom-in" data-aos-duration="1000" data-aos-easing="ease" alt="Fulcro" src="/logo-fulcro-home.jpeg"
          style="width: 300px; height: 300px">

        <div data-aos="zoom-in" data-aos-duration="1000" data-aos-delay="500" data-aos-easing="ease"
          class="flex column items-center q-mt-md">
          <p class="text-center q-mb-none">"Dame un punto de apoyo y moveré el mundo"</p>
          <span class="text-italic">(Arquímedes 287-212 AC)</span>
        </div>
      </div>

      <div data-aos="zoom-in" data-aos-duration="1000" data-aos-easing="ease" data-aos-delay="1000"
        class="intro-text col-10 col-md-5 col-lg-6">
        <h4 class="q-my-none">Somos el punto de <span>Apoyo</span> donde <span>Productores y Distribuidores</span>
          encuentran el mejor apalancamiento en el comercio mayorista regional en alimentos con alto valor agregado.</h4>

        <button @click="dialog = true" class="q-mt-lg btn-contact">Contactanos</button>

        <!-- Modal de contacto -->
        <q-dialog v-model="dialog">
          <q-card style="width: 400px; max-width: 85vh" class="bg-blue-grey-10">
            <q-card-section class="row items-center q-pb-none flex items-center justify-between">
              <p style="font-family: 'Taviraj'; font-size: clamp(1.5rem, 1.5vw, 2rem);" class="contact-title text-white q-mb-none">Sigamos en Contacto</p>
              <q-btn icon="close" color="blue-grey-8" flat round dense v-close-popup />
            </q-card-section>

            <q-card-section>
              <q-form @submit.prevent="enviarMensaje">
                <hr>
                <q-input dark bg-color="blue-grey-9" filled dense color="blue-10" class="q-mt-lg" type="text"
                  v-model.trim="nombre" label="Nombre *" lazy-rules :rules="nombreRules">
                  <template v-slot:append>
                    <q-icon name="las la-at" />
                  </template>
                </q-input>

                <q-input dark bg-color="blue-grey-9" filled dense color="blue-10" type="email"
                  v-model.trim="email" label="Mail *" lazy-rules :rules="rulesEmail">
                  <template v-slot:append>
                    <q-icon name="las la-at" />
                  </template>
                </q-input>

                <q-input dark bg-color="blue-grey-9" filled dense color="blue-10" type="number" v-model.trim="mobile"
                  label="Telefono" lazy-rules :rules="rulesMobile">
                  <template v-slot:append>
                    <q-icon name="las la-phone" />
                  </template>
                </q-input>

                <div class="q-ml-none flex justify-center">
                  <q-btn label="Enviar" padding="7px 40px" outline color="white" type="submit" class="btn-contact" />
                </div>
              </q-form>
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

  p.contact-title{
    font-family: $montserrat;
  }

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
      font-size: clamp(1rem, 1.4vw, 3rem);
      line-height: 1.5rem;
      font-weight: 300;
      font-style: italic;
      text-align: center;

      span {
        // font-size: clamp(1rem, 1.3vw, 2rem);
        font-weight: 800;
        font-family: $montserrat;
        font-style: normal;
        color: #515151;
      }
    }

    .btn-contact {
      display: flex;
      justify-content: center;
      width: 100%;
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

@media screen and (min-width: 599.98px) {
  #intro {
    .intro-text {

      .btn-contact {
        width: 50%;
        margin: 3rem auto 0;
      }
    }
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

  #intro {

    .intro-text {

      h4 {
        font-size: clamp(1rem, 1.85vw, 3rem);
        line-height: 2.3rem;
      }
    }
  }

  #marcas {
    max-width: 1100px;

  }
}
</style>
