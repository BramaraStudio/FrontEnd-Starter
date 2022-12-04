<template>
  <TableBasic widget-classes="mb-5 mb-xl-8"></TableBasic>
</template>

<script lang="ts">
import { defineComponent, onMounted } from "vue";
import TableBasic from "@/components/master-basic/Table.vue";
import { setCurrentPageBreadcrumbs } from "@/core/helpers/breadcrumb";
import { MenuComponent } from "@/assets/ts/components";

export default defineComponent({
  name: "widgets-tables",
  components: {
    TableBasic,
  },
  setup() {
    onMounted(() => {
      setCurrentPageBreadcrumbs("Basic Form V1", ["Master"]);

      MenuComponent.reinitialization();
    });
  },
});
</script>
