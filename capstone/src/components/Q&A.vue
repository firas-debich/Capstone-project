<template>
  <div id="app">
    <div class="container px-6 py-3 mx-auto text-left">
      <div>
        <div class="flex">
          <div class="flex font-bold">
            <p>
              Q:
            </p>
            <div class="ml-2 text-lg">
              <div v-for="product in products" v-bind:key="product.id">
                <div>{{ product[0].question_body }}</div>
              </div>
            </div>
          </div>
          <div class="mr-9 absolute right-60 text-xs">
            <span
              >Helpful?
              <a v-on:click="counter += 1" class="ml-2 underline">Yes</a>
              <span>({{ counter }})</span><span class="ml-3">|</span>
              <a class="ml-3 underline">Add answer</a>
            </span>
          </div>
        </div>
        <br />
        <div>
          <div class="flex">
            <p class="font-bold ">A:</p>
            <p class="ml-2 text-lg">
              Lorem ipsum dolor sit eum dolorum corruptdbdv vdbds dvgsdbv
              dbqbdsb fbsbfb vbfdbsf fbsfdi.
            </p>
          </div>
          <br />
          <div class="flex font-thin text-xs ml-6">
            <div>By</div>
            <div v-for="product in products" v-bind:key="product.id">
              <div class=" mr-2">
                {{ product[0].asker_name }} {{ product[0].question_date }}
              </div>
            </div>
            <div class="ml-3">Helpful?</div>
            <a v-on:click="counter2 += 1" class="ml-2 underline">Yes</a>
            <span>({{ counter2 }})</span><span class="ml-3">|</span>
            <a class="ml-3 underline">Report</a>
          </div>
        </div>
        <br />
        <div class="flex">
          <div class="flex font-bold">
            <p>
              Q:
            </p>
            <div class="ml-2 text-lg">
              <div v-for="product in products" v-bind:key="product.id">
                {{ product[1].question_body }}
              </div>
            </div>
          </div>
          <div class="mr-9 absolute right-60 text-xs">
            <span
              >Helpful?
              <a v-on:click="counter3 += 1" class="ml-2 underline">Yes</a>
              <span>({{ counter3 }})</span><span class="ml-3">|</span>
              <a class="ml-3 underline">Add answer</a>
            </span>
          </div>
        </div>
        <br />
        <div class="flex">
          <p class="font-bold ">A:</p>
          <p class="ml-2 text-lg">
            Lorem ipsum dolor sit eum dolorum corruptdbdv vdbds dvgsdbv dbqbdsb
            fbsbfb vbfdbsf fbsfdi.
          </p>
        </div>
        <br />
        <div class="flex font-thin text-xs ml-6">
          <div>By</div>
          <div v-for="product in products" v-bind:key="product.id">
            <div class=" mr-2">
              {{ product[1].asker_name }} {{ product[1].question_date }}
            </div>
          </div>
          <div class="ml-3">Helpful?</div>
          <a v-on:click="counter4 += 1" class="ml-2 underline">Yes</a>
          <span>({{ counter4 }})</span><span class="ml-3">|</span>
          <a class="ml-3 underline">Report</a>
        </div>
        <br />

        <p class="text-lg ml-6">Yes,as you can see in these photos.</p>
        <br />
        <div class="flex ml-6 ">
          <img class="object-contain h-20 w-32 hover:bg-gray-200 " />
          <img class="object-contain h-22 w-32 ml-3 hover:bg-gray-200" />
          <img class="object-contain h-22 w-32 ml-3 hover:bg-gray-200" />
        </div>

        <br />
        <div class="flex font-thin text-xs ml-6">
          <div>By User 1337 - <a class="font-bold">Seller</a>, May 1 2019</div>
          <div class="ml-3">Helpful?</div>
          <a v-on:click="counter5 += 1" class="ml-2 underline">Yes</a>
          <span>({{ counter5 }})</span><span class="ml-3">|</span>
          <a class="ml-3 underline">Report</a>
        </div>

        <!-- <li v-for="(val,i) in test1 " :key="i">{{val}}</li> -->
      </div>
      <br />
    </div>
  </div>
</template>

<script>
export default {
  // props:['test1'],

  data: function() {
    return {
      counter: this.$store.state.products.results[0].question_helpfulness,
      // counter2: this.$store.state.products.results[1].answers,
      counter3: this.$store.state.products.results[2].question_helpfulness,
      // counter4: this.$store.state.products.results[3].question_helpfulness,
      // counter5: this.$store.state.products.results[4].question_helpfulness,j
    };
  },
  computed: {
    products() {
      return this.$store.getters.products;
    },
  },
  created() {
    this.$store.dispatch("loadProducts");
  },
};
</script>
