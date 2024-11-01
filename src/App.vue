<script setup lang="ts">
import "@webcomponents/scoped-custom-element-registry"
import "@govtechsg/sgds-web-component/themes/night.css";
import "@govtechsg/sgds-web-component/themes/day.css";
import "@govtechsg/sgds-web-component"

</script>
<template>

  <div class="container p-5">
    <h1 class="label-event"> Event Registration Form</h1>
    <sgds-stepper  :steps="stepMetadata"
      ></sgds-stepper>
    <section>
      <component :is="currentComponent" v-bind="componentProps"></component>
      <div class="btn-group">

        <sgds-button class="me-3" variant="primary">
          Next
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M3 12C3 11.8295 3.06773 11.666 3.18828 11.5455C3.30883 11.4249 3.47233 11.3572 3.64282 11.3572H18.8043L14.7584 7.31258C14.6377 7.19187 14.5699 7.02817 14.5699 6.85746C14.5699 6.68676 14.6377 6.52305 14.7584 6.40235C14.8791 6.28165 15.0428 6.21384 15.2135 6.21384C15.3842 6.21384 15.5479 6.28165 15.6686 6.40235L20.8111 11.5449C20.871 11.6046 20.9185 11.6755 20.9509 11.7536C20.9833 11.8317 21 11.9154 21 12C21 12.0845 20.9833 12.1683 20.9509 12.2464C20.9185 12.3245 20.871 12.3954 20.8111 12.4551L15.6686 17.5976C15.5479 17.7183 15.3842 17.7861 15.2135 17.7861C15.0428 17.7861 14.8791 17.7183 14.7584 17.5976C14.6377 17.4769 14.5699 17.3132 14.5699 17.1425C14.5699 16.9718 14.6377 16.8081 14.7584 16.6874L18.8043 12.6428H3.64282C3.47233 12.6428 3.30883 12.5751 3.18828 12.4545C3.06773 12.334 3 12.1705 3 12Z"
              fill="currentColor" />
          </svg>

        </sgds-button>

      </div>
    </section>
  </div>
</template>

<script lang="ts">
import { defineComponent, markRaw } from 'vue'
import PersonalDetails from "./components/PersonalDetails.vue";

export default defineComponent({
  components: {
    PersonalDetails,
  },
  data() {
    return {
      activeStep: 0,
      stepMetadata: [
        {
          stepHeader: 'Personal Details',
          component: markRaw(PersonalDetails)
        },
        {
          stepHeader: 'Contact Details',
          
        },
        {
          stepHeader: 'Payment Details',
          
        }
      ],
      currentComponent: markRaw(PersonalDetails),
      componentProps: {
        details: {
          firstName: '',
          lastName: '',
          gender: '',
        },
      }
    };
  },

});
</script>

<style>
section {
  padding: 2rem;
}

.root {


}

.btn-group {
  display: flex;
  justify-content: flex-end;
  margin-top: 1rem;
}

.container {
  max-width: 550px;
  margin: 0 auto;
  padding-left: 20px;
}

.label-event {
  font-family: var(--sgds-font-family-brand);
  font-size: var(--sgds-font-size-6);
  font-weight: var(--sgds-font-weight-bold);
  padding-bottom: var(--sgds-padding-xl);
  text-align: center;
}

</style>
