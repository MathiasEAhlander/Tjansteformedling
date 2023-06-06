<template>
  <div class="main">
    <div class="sort">
      <h2>Sort</h2>
      <p class="sortbtn" @click="sortingTitle()">Service</p>
      <p class="sortbtn" @click="sortingPrice()">Price</p>
      <p class="sortbtn" @click="sortingDist()">Distance</p>
      <p class="sortbtn" @click="sortingTime()">Time</p>
    </div>
    <div class="Filter">
      <h2>Filter</h2>
      <label for="search">Search: </label>
      <input
        type="text"
        id="search"
        v-model="textSearch"
        @input="searchList()"
      />
    </div>
    <div class="listing-column">
      <div class="listing" v-for="offer in offers">
        <h3>{{ offer.service }}</h3>
        <ul>
          <li>{{ offer.seller }}</li>
          <li>{{ offer.distance }} km</li>
          <li>{{ offer.time }} min</li>
          <li>€{{ offer.price }}</li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      offers: [
        {
          service: "Moving",
          seller: "Bob",
          distance: 10,
          time: 90,
          price: 120,
        },
        {
          service: "Grass cutting",
          seller: "John",
          distance: 2,
          time: 15,
          price: 10,
        },
        {
          service: "Window cleaning",
          seller: "Jerry",
          distance: 30,
          time: 150,
          price: 200,
        },
        {
          service: "Dogwalking",
          seller: "Nick",
          distance: 1,
          time: 60,
          price: 20,
        },
      ],
      textSearch: "",
    };
  },
  methods: {
    searchList() {
      console.log(this.textSearch);

      let asdf = this.offers.toLowerCase;
      let sadf = this.textSearch.toLowerCase;
      let reslt = this.asdf.includes(sadf);

      if (this.reslt) {
        console.log("hg");
      }
    },
    sortingTitle() {
      this.offers.sort(
        (a, b) => a.service.charCodeAt(0) - b.service.charCodeAt(0)
      );

      console.log("service");
      console.table(this.offers);
    },
    sortingPrice() {
      this.offers.sort((a, b) => a.price - b.price);

      console.log("price");
      console.table(this.offers);
    },
    sortingDist() {
      this.offers.sort((a, b) => a.distance - b.distance);

      console.log("dist");
      console.table(this.offers);
    },
    sortingTime() {
      this.offers.sort((a, b) => a.time - b.time);

      console.log("time");
      console.table(this.offers);
    },
  },
};
</script>

<style>
.main {
  margin-top: 200px;
}

h2 {
  font-size: 1.5em;
  margin-left: 1em;
}

.sort {
  display: block;
}

.listing-column {
  margin-right: 70px;
  float: right;
  display: block;
}

.listing {
  border: solid black 2px;
  background-color: lightgray;
  border-radius: 25px;
  width: 500px;
  margin-bottom: 20px;
  padding: 2em;
}

.sortttl {
  font-size: 1.2em;
  font-weight: bold;
}

.sortbtn {
  font-size: 1em;
  font-weight: 100;
  margin-left: 2em;
  color: dimgrey;
}

.sortbtn:hover {
  cursor: pointer;
}
</style>
