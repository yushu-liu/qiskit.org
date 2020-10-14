<template>
  <article class="capability-card">
    <div class="capability-card__container">
      <h3 class="capability-card__title">
        {{ title }}
      </h3>
      <div class="capability-card__description">
        {{ description }}
      </div>
    </div>
    <div
      class="capability-card__image"
      :lazy-background="image"
    />
  </article>
</template>

<script lang="ts">
import Vue from 'vue'
import { Component, Prop } from 'vue-property-decorator'

@Component
export default class extends Vue {
  @Prop(String) image
  @Prop(String) title
  @Prop(String) description
}
</script>

<style lang="scss" scoped>
@import '~carbon-components/scss/globals/scss/typography';

.capability-card {
  display: flex;
  min-height: 20rem;

  @include mq($until: medium) {
    flex-direction: column;
  }

  &__container {
    display: flex;
    flex: 1;
    padding-right: $spacing-07;

    @include mq($until: large) {
      flex-direction: column;
    }
  }

  &__title {
    @include type-style('productive-heading-02');
    flex: 0 0 12rem;
    padding-right: $spacing-07;

    @include mq($until: large) {
      flex: 0 0 auto;
      padding-right: 0;
      padding-bottom: $spacing-07;
    }
  }
  &__description {
    @include type-style('body-long-01');
    flex: 1;

    @include mq($until: large) {
      padding-bottom: $spacing-05;
    }
  }

  &__image {
    flex: 0 0 32rem;
    width: 100%;
    height: 100%;
    background-size: contain;
    background-position: center top;
    background-repeat: no-repeat;

    @include mq($from: medium, $until: large) {
      flex: 1.5;
    }

    @include mq($from: medium) {
      display: none;
    }

    @include mq($until: medium) {
      flex: 0 0 16rem;
      margin: $spacing-06 0 0 0;
    }
  }
}
</style>