<template>
  <div id="app">
    <h1>Z</h1>
      <div class="user" v-for="review in reviews.data" :key="review.id">

      <div class="user-details">
        <h2 class="user-name">
            userName: {{ review.attributes.userName }}<br>
        </h2>
        <ul>
          <li>Title: {{ review.attributes.title }}</li>
          <li>Review: {{ review.attributes.review }}</li>
          <li><strong>Date:</strong> {{ review.attributes.date }}</li>
          <li><strong>Rating:</strong> {{ review.attributes.rating }}</li>
        </ul>
      </div>


        <div id="ember152" class="ember-view l-column--grid l-column small-12 medium-6 large-4 small-valign-top l-column--equal-height"><div data-test-we-modal="page-overlay" id="ember153" class="ember-view"><!---->
<!----></div>


          <div role="article" aria-labelledby="we-customer-review-1" aria-posinset="2" aria-setsize="-1" id="ember154" class="we-customer-review lockup ember-view" tabindex="0"><figure aria-label="{{ review.attributes.rating }} out of 5" id="ember155" class="we-star-rating ember-view we-customer-review__rating we-star-rating--large"><span class="we-star-rating-stars-outlines">
  <span class="we-star-rating-stars we-star-rating-stars-{{ review.attributes.rating }}"></span>
</span>
<!----></figure>

<div class="we-customer-review__header we-customer-review__header--user">
  <span dir="ltr" id="ember156" class="we-truncate we-truncate--single-line ember-view we-customer-review__user">  {{ review.attributes.userName }}
</span>

  <span class="we-customer-review__separator">, </span>

  <time data-test-customer-review-date="" datetime="2020-07-12T18:33:49.000Z" aria-label="July 12, 2020" class="we-customer-review__date">07/12/2020</time>
</div>

<h3 dir="ltr" id="we-customer-review-1" class="we-truncate we-truncate--single-line ember-view we-customer-review__title">  {{ review.attributes.title }}
</h3>

  <blockquote id="ember157" class="we-truncate we-truncate--multi-line we-truncate--interactive we-truncate--truncated ember-view we-customer-review__body">    

      <div data-clamp="" id="ember159" class="we-clamp ember-view" ismorertl="false" style="height: 72px; -webkit-mask: linear-gradient(0deg, rgba(0, 0, 0, 0) 0px, rgba(0, 0, 0, 0) 18.0001px, rgb(0, 0, 0) 18.0001px), linear-gradient(270deg, rgba(0, 0, 0, 0) 0px, rgba(0, 0, 0, 0) 32.8px, rgb(0, 0, 0) 68.8002px);"><p dir="ltr" data-test-bidi="">{{ review.attributes.review }}</p>
</div>

    <button aria-hidden="true" tabindex="-1" class="we-truncate__button link" data-metrics-click="{&quot;actionType&quot;:&quot;more&quot;,&quot;targetType&quot;:&quot;button&quot;,&quot;targetId&quot;:&quot;More&quot;}" data-ember-action="" data-ember-action-251="251">
      more
    </button>
</blockquote>

<!----></div>

</div>
        <div id="ember162" class="ember-view l-column--grid l-column small-12 medium-6 large-4 small-valign-top l-column--equal-height"><div data-test-we-modal="page-overlay" id="ember163" class="ember-view"><!---->
<!----></div>

</div>
    </div><!-- v-for="review in reviews.data" -->
  </div><!-- id="app" -->
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      reviews: [],
    };
  },
  methods: {
    getInitialReviews() {
      axios.get(`/review-data/trump_10.json`).then((response) => {
        this.reviews = response.data;
      });
    },
    formatDate(dateString) {
      let convertedDate = new Date(dateString);
      return convertedDate.toDateString();
    }
  },
  beforeMount() {
    this.getInitialReviews();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
