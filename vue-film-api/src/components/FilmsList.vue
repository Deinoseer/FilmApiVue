<template>
  <div class="card" @click="showMovie">
    <div class="card-image">
      <img :src="poster" alt="" />
    </div>
    <div class="right-block">
      <div class="first-block">
        <div class="main-h2">
          <h2>{{ title }}</h2>
        </div>
        <div class="main-flag">
          <div class="rectangle"></div>
        </div>
      </div>
      <div class="description">
        <div class="first-desc">
          <div class="inline">
            <p>{{ year }},</p>
            <p v-for="(gen, index) in genres" :key="index">{{ gen }},</p>
          </div>
        </div>
        <div class="second-desc">
          <p>РЕЖИСЁР:</p>
          <p v-for="(der, index) in directors" :key="index">{{ der }},</p>
        </div>
        <div class="second-desc">
          <p>Актеры:</p>
          <p v-for="(actor, index) in actors" :key="index">{{ actor }},</p>
        </div>
        <div class="third-desc">
          <p>{{ description }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FilmList",
  components: {},
  data() {
    return {
      image: "//images.kinopoisk.cloud/posters/435.jpg",
    };
  },
  props: {
    id: Number,
    poster: String,
    title: {
      type: String,
      default: "Где то заголовок",
    },
    genres: Array,
    actors: Array,
    directors: Array,
    year: Number,
    description: String,
    destination: String,
  },
  methods: {
    showMovie() {
      this.$emit("showMovie");
    },
  },
};
/*
<div class="card">
    <div class="cardImage"></div>
    1
    <h2 style="float: left">{{ title }}</h2>
    <p>{{ id }} ид {{ destination }}</p>
  </div>
*/
</script>

<style lang="scss" scoped>
.card {
  margin: 52px 0 52px 0;
  background-color: #4d4747;
  width: 1400px;
  min-height: 168px;
  display: flex;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}
.card:hover {
  box-shadow: 0px 8px 20px rgba(0, 0, 0, 0.35);
  cursor: pointer;
}
.card-image {
  margin: 0;
  flex: 0 1 168px;
  background-color: #c4c4c4;
  display: flex;
  align-items: center;
  justify-content: center;
  img {
    max-width: 112px;
    display: block;
  }
}
.right-block {
  margin: 0;
  flex: 0 1 100%;
}
.first-block {
  display: flex;
  width: 100%;
  height: auto;
}
.main-h2 {
  flex: 3 1 auto;
  margin: 32px 0 0 24px;
  h2 {
    font-style: normal;
    font-weight: bold;
    font-size: 36px;
    line-height: 36px;
    color: #ffffff;
    margin: 0;
  }
}
.main-flag {
  flex: 1 1 auto;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
.rectangle {
  height: 0px;
  width: 177px;
  border-bottom: 30px solid rgb(196, 196, 196);
  border-left: 7px solid transparent;
}
.description {
  margin-left: 24px;
}
.first-desc {
  margin-top: 12px;
  height: 12px;
  p {
    font-size: 12px;
    margin: 0;
    font-weight: 700;
    color: #988f8f;
    float: left;
  }
}
.inline {
  overflow: hidden;
}
.second-desc {
  margin-top: 8px;
  height: 12px;
  p {
    font-size: 12px;
    margin: 0;
    font-weight: 700;
    color: #988f8f;
    float: left;
  }
}
.third-desc {
  margin-top: 20px;
  p {
    font-size: 16px;
    margin: 0;
    font-weight: normal;
    color: #ffffff;
    float: left;
    margin-bottom: 20px;
  }
}
</style>