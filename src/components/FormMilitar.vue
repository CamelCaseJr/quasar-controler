<template>
  <div class="q-pa-sm" style="max-width: 28rem">
    <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-sm">
      <div style="width: 28rem">
        <q-input
          filled
          v-model="name"
          label="Your name *"
          hint="Name and surname"
          lazy-rules
          :rules="[(val) => (val && val.length > 0) || 'Please type something']"
        />
      </div>

      <div style="display: flex; justify-content: space-between; width: 28rem">
        <q-input
          filled
          type="number"
          v-model="age"
          label="Your Cpf *"
          lazy-rules
          :rules="[
            (val) => (val !== null && val !== '') || 'Please type your age',
            (val) => (val > 0 && val < 100) || 'Please type a real age',
          ]"
        />

        <q-input
          filled
          v-model="name"
          label="Your sex *"
          hint="M or F"
          lazy-rules
          :rules="[(val) => (val && val.length > 0) || 'Please type something']"
        />
      </div>
      <div style="display: flex; justify-content: space-between; width: 28rem">
        <q-input
          filled
          type="number"
          v-model="age"
          label="Your saram *"
          lazy-rules
          :rules="[
            (val) => (val !== null && val !== '') || 'Please type your age',
            (val) => (val > 0 && val < 100) || 'Please type a real age',
          ]"
        />

        <q-input
          filled
          v-model="name"
          label="Your nome de guerra*"
          hint="M or F"
          lazy-rules
          :rules="[(val) => (val && val.length > 0) || 'Please type something']"
        />
      </div>
      <div style="display: flex; justify-content: space-between; width: 28rem">
        <q-input
          filled
          v-model="name"
          label="Your OM*"
          hint="Digite o nome da OM"
          lazy-rules
          :rules="[(val) => (val && val.length > 0) || 'Please type something']"
        />

        <q-input
          filled
          v-model="name"
          label="Your posto/graduação*"
          hint=""
          lazy-rules
          :rules="[(val) => (val && val.length > 0) || 'Please type something']"
        />
      </div>

      <q-space />

      <div class="q-pt-md">
        <q-btn label="Submit" type="submit" color="primary" />
        <q-btn
          label="Reset"
          type="reset"
          color="primary"
          flat
          class="q-ml-sm"
        />
      </div>
    </q-form>
  </div>
</template>

<script>
import { useQuasar } from "quasar";
import { ref } from "vue";

export default {
  setup() {
    const $q = useQuasar();

    const name = ref(null);
    const age = ref(null);
    const accept = ref(false);

    return {
      name,
      age,
      accept,

      onSubmit() {
        if (accept.value !== true) {
          $q.notify({
            color: "red-5",
            textColor: "white",
            icon: "warning",
            message: "You need to accept the license and terms first",
          });
        } else {
          $q.notify({
            color: "green-4",
            textColor: "white",
            icon: "cloud_done",
            message: "Submitted",
          });
        }
      },

      onReset() {
        name.value = null;
        age.value = null;
        accept.value = false;
      },
    };
  },
};
</script>
