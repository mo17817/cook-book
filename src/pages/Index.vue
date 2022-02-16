<template>
  <q-page class="flex flex-center">
    <div class="row" id="title">
      <Mediacard> </Mediacard>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import Mediacard from "components/Mediacard";
export default defineComponent({
  name: "PageIndex",
  component: { Mediacard },
});
</script>
