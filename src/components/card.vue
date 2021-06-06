<template>
  <div>
    <li class="card__list-item">
      <div class="card__images-wrap">
        <img class="card__img" alt="" src="../assets/images/plane.jpg" />
      </div>
      <div class="card__inner-info">
        <h3 class="card__title">{{ card.name }}</h3>
        <p class="card__description">
          {{ card.website }}
        </p>
        <p class="card__text">{{ card.company }}</p>
      </div>
    </li>
  </div>
</template>

<script>
export default {
  props: {
    card: Object,
    name: {
      type: String,
      default: null,
    },
  },
};
</script>
