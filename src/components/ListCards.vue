<template>
  <section class="section__cards">
    <div class="button__container">
      <div class="btn__filter-wrap">
        <button class="title__btn">
          Rent <span class="color__blue">whatever</span>
        </button>
        <button class="btn__icon">
          <vectorIcon class="icon__vector" />
        </button>
      </div>

      <div class="btn__add-wrap">
        <p class="btn__text">Add new</p>
        <button @click="get" class="btn__add">
          <AddNnewIcon class="icon__plus" />
        </button>
      </div>
    </div>
    <ul class="card__list" v-if="cards.length > 0">
      <Card v-for="el in cards" :key="el.id" :card="el"></Card>
    </ul>
  </section>
</template>

<script>
import VectorIcon from "./SvgIcons/SvgVector.vue";
import AddNnewIcon from "./SvgIcons/SvgIconAddNnew.vue";
import Card from "./card.vue";

export default {
  name: "index",
  components: {
    VectorIcon,
    AddNnewIcon,
    Card,
  },
  data() {
    return {
      // параметры
      cards: [],
    };
  },
  methods: {
    // хранит функци компонента
    get() {
      const url = "https://jsonplaceholder.typicode.com/users";
      fetch(url, {
        methods: "GET",
        headers: {
          "Content-Type": "appLication/json",
        },
      })
        .then((response) => {
          return response.json();
        })
        .then((result) => {
          this.cards = result;
          console.log(result);
        });
    },
  },
  mounted() {
    this.get();
  },
};
</script>

<style lang="scss">
.section__cards {
  background: #f3f4f7;

  border-radius: 48px;
  max-width: 1341px;
  width: 100%;

  margin: 0 auto;
  padding-top: 56px;

  .button__container {
    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 0px 64px 40px;

    .btn__filter-wrap {
      display: flex;
      align-items: center;

      .title__btn {
        font-weight: bold;
        font-size: 40px;
        line-height: 120%;

        background: transparent;
        border: transparent;

        margin: 0px 18px 0px 0px;
        .color__blue {
          color: #4959ff;
        }
      }
      .btn__icon {
        padding: 4px 18px 0px 7px;

        background: transparent;
        border: #f3f4f7;
      }
    }
    .btn__add-wrap {
      display: flex;

      .btn__text {
        display: flex;
        align-items: center;

        margin: 0px 20px 0px 0px;

        font-weight: bold;
        font-size: 20px;
        line-height: 140%;
        color: #4959ff;
      }
      .btn__add {
        background: transparent;
        border: #f3f4f7;
      }
    }
  }

  .card__list {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    list-style: none;

    padding: 0px 32px 0px 64px;

    &-item {
      max-width: 320px;
      width: 100%;

      display: flex;

      background: #fcfcfc;
      border-radius: 32px;

      padding-left: 32px;
      margin: 0px 32px 32px 0px;

      .card__images-wrap {
        margin-right: 24px;

        display: flex;
        align-items: center;
        .card__img {
          display: flex;
        }
      }
      .card__inner-info {
        text-align: left;

        .card__title {
          margin: 40px 0px 12px 0px;
          font-weight: bold;
          font-size: 16px;
          line-height: 14px;
        }
        .card__description {
          margin: 0px 0px 16px 0px;

          font-weight: 300;
          font-size: 12px;
          line-height: 148%;
          color: #677b8f;
        }
        .card__text {
          margin: 0px 0px 25px 0px;

          font-weight: bold;
          font-size: 14px;
          line-height: 148%;
          color: #f84ab3;
        }
      }
    }
  }
}

@media screen and (max-width: 1023px) {
  .section__cards {
    .card__list {
      display: flex;
      justify-content: center;
      flex-wrap: wrap;
      list-style: none;

      padding: 0px 10px 0px 10px;

      &-item {
        max-width: 320px;
        width: 100%;

        display: flex;

        background: #fcfcfc;
        border-radius: 32px;

        padding: 0px 7px;
        margin: 0px 8px 32px 0px;
      }
      .card__images-wrap {
        margin-right: 20px;
      }
    }
    .button__container {
      display: flex;
      align-items: center;
      justify-content: space-between;

      padding: 0px 10px 25px;
    }
  }
}

@media screen and (max-width: 768px) {
  .section__cards {
    .button__container {
      .btn__filter-wrap {
        .title__btn {
          font-weight: bold;
          font-size: 24px;
          line-height: 120%;

          margin-right: 0px;
          padding: 0px;
        }
        .btn__text {
          font-weight: bold;
          font-size: 16px;
          line-height: 136%;

          margin-right: 5px;
        }
        .card__list-item {
          max-width: 320px;
          width: 100%;

          display: flex;

          background: #fcfcfc;
          border-radius: 32px;

          padding: 0px 20px;
          margin: 0px 0px 15px 0px;
        }
      }
    }
  }
}

@media screen and (max-width: 425px) {
  .section__cards {
    .button__container {
      .btn__add-wrap {
        .btn__text {
          margin-right: 12px;
          font-size: 16px;
        }
        .btn__add {
          padding: 0px;

          .icon__plus {
            width: 32px;
            height: 32px;
          }
        }
      }
    }
  }
}
@media screen and (max-width: 400px) {
  .section__cards {
    .card__list {
      &-item {
        margin-right: 0px;
      }
    }
  }
}
@media screen and (max-width: 374px) {
  .section__cards {
    .button__container {
      .btn__filter-wrap {
        .title__btn {
          font-size: 16px;
        }
        .btn__icon {
          width: 8px;
          height: 8px;
          padding: 0px 0px 12px 10px;
        }
      }
    }
  }
}
</style>
