<template lang="en">
    <div class="container">
        <CallSidebar heading="Projects"/>
        <div class="content">
          <section class="sub-container" id="section1">section 1</section>
          <section class="sub-container" id="section2">section 2</section>
          <section class="sub-container" id="section3">section 3</section>
          <section class="sub-container" id="section4">section 4</section>
          <section class="sub-container" id="section5">section 5</section>
          <section class="sub-container" id="section6">section 6</section>
        </div>
      <navigationBlock class="navbar sub-container" />
    </div>
</template>
<script>
export default {
  name: 'projects',
}
</script>
<style scoped>
.content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr;
}

.sub-container {
  width: 20rem;
  height: 20rem;

}

.navigationBlock {
  width: 44rem;
  justify-self: center;
  height: fit-content;
}

#section2 {
  grid-row: 1 / 3;
  grid-column: 2;
  height: 42rem;

}

#section3 {
  display: none;
}

#section5 {
  grid-column: 1 / 3;
  width: 44rem;
}

#section6 {
  display: none;
}

@media (min-width: 1080px) {
  .sub-container {
    width: 30rem;
    height: 30rem;
  }

  #section2 {
    height: 62rem;
  }

  #section5 {
    width: 64rem;
  }

  .navigationBlock {
    width: 64rem;
  }


}
</style>