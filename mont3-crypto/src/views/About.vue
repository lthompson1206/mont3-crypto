<template>
  <div class="about">
    <h1>My Bitcoin Data</h1>
    <!-- <img alt="Vue logo" src="../assets/bitcoin.png" /> -->
    <div id="border">
      <div id="card">
        <EventCard msg="Bitcoin takes a dive... " />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue";
export default {
  name: "About",
  components: {
    EventCard
  }
};
</script>
<style>
h1 {
  color: white;
  font-weight: bold;
}
#border {
  border: 1px solid gold;
  background-color: black;
  padding: 10px 10px 10px 10px;
  margin-top: 200px;
  margin-bottom: 200px;
  margin-right: 200px;
  margin-left: 200px;
}
.about {
 
}
@media screen and (max-width: 1024px) {
  /* Specific to this particular image */
  .about {
    left: 50%;
    margin-left: -512px; /* 50% */
  }
}
</style>
