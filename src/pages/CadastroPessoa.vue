<template>
  <q-page class="q-pa-md">
    <div class="q-pa-md q-my-md">
      <div class="text-h6">Cadastro</div>
      <div class="text-subtitle2">Militar</div>
    </div>

    <div class="q-pa-md q-my-md">
      <q-card>
        <q-card-section horizontal>
          <div class="q-pa-lg row items-start q-gutter-md">
            <q-card class="my-card" flat bordered>
              <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" />

              <q-card-section>
                <div class="text-overline text-orange-9">Nome de Guerra</div>
                <div class="text-h5 q-mt-sm q-mb-xs">Posto</div>
                <div class="text-caption text-grey">Resumo de dados</div>
              </q-card-section>

              <q-card-actions>
                <q-btn flat color="primary" label="Atualizar Foto" />
                <q-btn flat color="secondary" label="Delet" />
                <q-space />
              </q-card-actions>

              <q-slide-transition>
                <div v-show="expanded">
                  <q-separator />
                  <q-card-section class="text-subitle2">
                    {{ lorem }}
                  </q-card-section>
                </div>
              </q-slide-transition>
            </q-card>
          </div>
          <div class="q-pa-md row items-start q-gutter-md">
            <form-militar />
          </div>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import FormMilitar from "src/components/FormMilitar.vue";
import { defineComponent } from "vue";

export default defineComponent({
  name: "IndexPage",
  components: {
    FormMilitar,
  },
});
</script>

<style lang="sass" scoped>
.my-card
  width: 100%
  max-width: 400px
</style>
