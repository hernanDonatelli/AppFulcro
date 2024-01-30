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
  <section id="footer" class="q-px-md q-pt-xl q-pb-md bg-blue-10">
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
              <q-tooltip self="center middle" style="color: #e8e8e8; background-color: transparent;"
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
      <p class="text-center q-mb-none">Fulcro Foods & Retails © Copyright {{ oldYear }} - {{ actualYear }}.</p>
      <p class="text-center q-mb-none">Todos los derechos reservados</p>
    </div>
  </section>
</template>


<style lang="scss" scoped>
#footer {
  color: #82b1ff;
  font-size: clamp(1rem, 1.5vw, 3rem);

  .copy {
    font-size: clamp(.8rem, 1.2vw, 1.2rem);
  }
  .mail {
    order: 2;
  }

  .links {
    order: 3;

    a {
      font-size: clamp(1rem, 1.5vw, 3rem);
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

@media screen and (min-width: 1599.98px) {
  .main-container {
    max-width: 1440px;
    margin: 0 auto;


  }
}

</style>
