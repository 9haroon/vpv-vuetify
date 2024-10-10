<script setup>
import { ref } from 'vue'
import { VPdfViewer } from "@vue-pdf-viewer/viewer";

</script>
<template>
    <v-dialog max-width="500">
        <template v-slot:activator="{ props: activatorProps }">
          <v-btn
            v-bind="activatorProps"
            color="surface-variant"
            text="Open Dialog"
            variant="flat"
          ></v-btn>
        </template>

        <template v-slot:default="{ isActive }">
          <v-card title="Dialog">
            <v-card-text>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua.
            </v-card-text>
            <div :style="{ height : '400px', width: '400px', margin: '20px auto' }">
                <VPdfViewer src="https://mozilla.github.io/pdf.js/web/compressed.tracemonkey-pldi-09.pdf" />
            </div>
            <v-card-actions>
              <v-spacer></v-spacer>

              <v-btn
                text="Close Dialog"
                @click="isActive.value = false"
              ></v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
</template>
<style>
@media print {
    .v-overlay-scroll-blocked{
        position: relative !important;
    }
    .v-overlay-container{
        position: relative; /* Ensure it's not fixed or absolute */
        display: block !important; /* Ensure it's visible */
        z-index: auto; /* Adjust z-index if needed */
        overflow: visible; /* Ensure no content is clipped */
    }
}
</style>