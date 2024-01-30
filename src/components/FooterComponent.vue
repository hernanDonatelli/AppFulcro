<script setup>
import { onMounted, ref } from 'vue'

const oldYear = ref('2013')
const actualYear = ref(null)

onMounted(() => {
  const fecha = new Date()
  actualYear.value = fecha.getFullYear()

})
</script>

<template>
  <section id="footer" class="q-px-md q-pt-xl q-pb-md">
    <div class="wrapper">
      <div class="row justify-center main-container">
        <div class="col-12">
          <div class="row items-center justify-between">
            <div class="mail flex justify-center items-center col-12 col-md-4">
              <q-icon name="las la-envelope" />
              <p class="text-center q-mb-none q-pl-sm">web@fulcro.com.ar</p>
            </div>

            <div class="links text-center col-12 col-md-2">
              <a class="q-px-md" href="https://ar.linkedin.com/company/fulcro-foods-retails" target="_blanck">
                <q-icon name="lab la-linkedin" />
                <q-tooltip anchor="top middle" self="center middle" style="color: #e8e8e8; background-color: transparent;"
                  transition-show="scale" transition-hide="scale">
                  Linkedin
                </q-tooltip>
              </a>
            </div>

            <div class="phone flex justify-center items-center text-center col-12 col-md-4">
              <q-icon name="las la-phone" />
              <p class="q-mb-none">11 5109-0509</p>
            </div>
          </div>
        </div>
      </div>

      <div class="copy row justify-center q-mt-lg">
        <p class="text-center q-mb-none">Fulcro Foods & Retails © Copyright {{ actualYear }}.</p>
        <p class="text-center q-mb-none">Todos los derechos reservados</p>
      </div>
    </div>
  </section>
</template>


<style lang="scss" scoped>
#footer {
  background-color: #0a0c29;
  font-family: $montserrat;
  font-size: clamp(.9rem, 1.1vw, 2rem);
  color: #82b1ff;

  .copy {
    font-size: clamp(.8rem, 1vw, 1.2rem);
  }
  .mail {
    order: 2;
  }

  .links {
    order: 3;

    a {

      i{
        font-size: clamp(2.5rem, 3vw, 4rem);

      }
    }

    a {
      color: #82b1ff;
      transition: all .2s ease-in-out;
    }

    a:hover {
      color: #bad4ff;
    }
  }


  .phone {
    order: 1;
  }

  .q-icon {
    font-size: clamp(2rem, 1.75vw, 1rem);
  }

}

@media screen and (min-width: 1023.98px) {
  #footer {

    .mail {
      order: 1;
    }

    .links {
      order: 2;
    }

    .phone {
      order: 3;
    }
  }
}

@media screen and (min-width: 1279.98px) {
  #footer {

    .wrapper{
      max-width: 1100px;
      margin: 0 auto;
    }
  }
}

@media screen and (min-width: 1599.98px) {
  .main-container {
    max-width: 1440px;
    margin: 0 auto;


  }
}

</style>
