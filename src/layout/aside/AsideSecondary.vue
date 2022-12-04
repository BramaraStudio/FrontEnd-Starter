<template>
  <div
    v-if="asideSecondaryDisplay"
    class="aside-secondary d-flex flex-row-fluid"
  >
    <div class="aside-workspace my-5 p-5" id="kt_aside_wordspace">
      <div class="d-flex h-100 flex-column">
        <div
          class="flex-column-fluid hover-scroll-y"
          data-kt-scroll="true"
          data-kt-scroll-activate="true"
          data-kt-scroll-height="auto"
          data-kt-scroll-wrappers="#kt_aside_wordspace"
          data-kt-scroll-dependencies="#kt_aside_secondary_footer"
          data-kt-scroll-offset="0px"
        >
          <div class="tab-content">
            <div
              class="tab-pane fade active show"
              id="kt_aside_nav_tab_master"
              role="tabpanel"
            >
              <KTMasterMenu></KTMasterMenu>
            </div>
          </div>
        </div>

        <div class="flex-column-auto pt-10 px-5" id="kt_aside_secondary_footer">
          <a
            href="https://preview.keenthemes.com/metronic8/vue/docs/#/doc-overview"
            class="
              btn
              btn-bg-light
              btn-color-gray-600
              btn-flex
              btn-active-color-primary
              flex-center
              w-100
            "
            data-bs-toggle="tooltip"
            data-bs-custom-class="tooltip-dark"
            data-bs-trigger="hover"
            data-bs-offset="0,5"
            data-bs-dismiss-="click"
          >
            <span class="btn-label"> Docs & Components </span>
            <span class="svg-icon btn-icon svg-icon-4 ms-2">
              <inline-svg src="media/icons/duotune/general/gen005.svg" />
            </span>
          </a>
        </div>
      </div>
    </div>
  </div>

  <button
    v-if="asideSecondaryDisplay && minimizationEnabled"
    :class="{ active: minimizedAsideSecondary }"
    class="
      btn btn-sm btn-icon btn-white btn-active-primary
      position-absolute
      translate-middle
      start-100
      end-0
      bottom-0
      shadow-sm
      d-none d-lg-flex
    "
    data-kt-toggle="true"
    data-kt-toggle-state="active"
    data-kt-toggle-target="body"
    data-kt-toggle-name="aside-minimize"
    style="margin-bottom: 1.35rem"
  >
    <span class="svg-icon svg-icon-2 rotate-180">
      <inline-svg src="media/icons/duotune/arrows/arr063.svg" />
    </span>
  </button>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import KTMasterMenu from "@/layout/aside/MasterMenu.vue";
import {
  minimizedAsideSecondary,
  asideSecondaryDisplay,
  minimizationEnabled,
} from "@/core/helpers/config";

export default defineComponent({
  name: "kt-aside-secondary",
  components: {
    KTMasterMenu,
  },
  setup() {
    return {
      minimizedAsideSecondary,
      asideSecondaryDisplay,
      minimizationEnabled,
    };
  },
});
</script>
