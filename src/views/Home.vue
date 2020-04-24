<template>
  <div class="home">
    <div class="header text-light">
      <Navbar class="text-light" />
      <div class="jumbotron">
        <h1 class="display-4">Armstrong Realty</h1>
        <p class="lead">
          Make your Reality
        </p>
        <hr class="my-4" />

        <p class="lead">
          <a class="btn btn-primary btn-lg" href="#" role="button">Contact</a>
        </p>
      </div>
    </div>
    <div class="container info py-1">
      <div class="row">
        <div class="col-sm">
          <span>Listing Type</span>
        </div>
        <div class="col-sm">Offer Type</div>
        <div class="col-sm">Location</div>
        <div class="col-sm"></div>
      </div>
      <div class="row pb-2">
        <div class="col-sm">
          <select class="form-control">
            <option>Condo</option>
            <option>House</option>
            <option>Apartment</option>
          </select>
        </div>
        <div class="col-sm">
          <select class="form-control">
            <option>For Sale</option>
            <option>For Lease</option>
            <option>Sub Let</option>
          </select>
        </div>
        <div class="col-sm">
          <input
            class="form-control mr-sm-2"
            type="search"
            placeholder="City/Location Name"
            aria-label="Search"
          />
        </div>
        <div class="col-sm text-center">
          <button type="button" class="btn btn-secondary btn-block">
            Search
          </button>
        </div>
      </div>
    </div>
    <div class="container-fluid content">
      <ForSale />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import ForSale from "@/components/ForSale.vue";

export default {
  name: "Home",
  components: {
    Navbar,
    ForSale,
  },
};
</script>

<style>
.header {
  background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0)),
    url(../assets/beach.jpg);
  background-size: cover;
}
.jumbotron {
  background-color: transparent !important;
}
.info {
  background-color: #c99972;
  position: relative;
  top: -3rem;
  border-radius: 0.2rem;
  z-index: 1;
}
.content {
  background-color: #efeae7;
  position: relative;
  top: -6.9rem;
}
</style>
