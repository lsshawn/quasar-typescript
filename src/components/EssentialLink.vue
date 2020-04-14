<template>
  <q-item clickable tag="a" target="_blank" :href="link">
    <q-item-section v-if="icon" avatar>
      <q-icon :name="icon" />
    </q-item-section>

    <q-item-section>
      <q-item-label>{{ title }}</q-item-label>
      <q-item-label caption>{{ caption }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import { Prop } from 'vue-property-decorator';

@Component
export default class EssentialLink extends Vue {
  @Prop({
    type: String,
    required: true
  })
  title!: string;

  @Prop({
    type: String
  })
  caption: string = '';

  @Prop({
    type: String
  })
  link: string = '#';

  @Prop({
    type: String
  })
  icon: string = '';
}
</script>
