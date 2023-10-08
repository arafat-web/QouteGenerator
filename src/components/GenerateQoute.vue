<template>
  <div class="container">
    <div class="neato-header rounded">
      <h1>
        {{ category.toUpperCase() }}
        <i style="cursor: pointer;" class="fa fa-refresh" aria-hidden="true" @click="getQoute"></i>
      </h1>
    </div>
    <div class="row">
      <!-- <div class="text-center bg-secondary text-white p-4 category">  </div> -->
      <div class="col-md-6 col-lg-4 pt-5 mt-5 mb-3 mb-md-0" v-for="(quoteData, index) in quotes" :key="index">
        <div :class="'card bg-' + quoteData.color + ' card-hover h-100 d-flex flex-column'">
          <div class="card-body text-center pb-0">
            <div :class="'card-icon-border-large border-' + quoteData.color + ' mtn-80'">
              <i class="fa fa-quote-left" :class="'text-' + quoteData.color" aria-hidden="true"></i>
            </div>
            <blockquote class="blockquote blockquote-sm mt-2">
              <p class="font-normal mb-5">{{ quoteData.quote }}</p>
            </blockquote>
          </div>
          <div class="card-footer border-white">
            <!-- <footer class="blockquote-footer text-uppercase text-white">
              
            </footer> -->
            <div class="row">
              <div class="col-3 text-start">
                <i class="fa fa-share-alt" style="color: white;" aria-hidden="true"></i>
              </div>
              <div class="col-6 text-white text-center">{{ quoteData.author }}</div>
              <div class="col-3 text-end">
                <i class="fa fa-copy" style="color: white;" aria-hidden="true"></i>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="footer mt-5 text-white">
      <p class="text-center">Made with <i class="fa fa-heart" aria-hidden="true"></i> by <a
          href="https://www.arafatdev.com" target="_blank"> Arafat Hossain Ar</a></p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GenerateQuote',
  data() {
    return {
      quotes: [],
      category: '',
    };
  },
  mounted() {
    this.getQoute();
  },
  methods: {
    async getQoute() {
      const wordsArray = [
        "age", "alone", "amazing", "anger", "architecture", "art", "attitude", "beauty", "best", "birthday",
        "business", "change", "communications", "computers", "cool", "courage", "dad", "dating",
        "death", "design", "dreams", "education", "environmental", "equality", "experience", "failure",
        "faith", "family", "famous", "fear", "fitness", "food", "forgiveness", "freedom", "friendship",
        "funny", "future", "god", "good", "government", "graduation", "great", "happiness", "health",
        "home", "hope", "humor", "imagination", "inspirational", "intelligence", "jealousy", "mom",
        "knowledge", "leadership", "learning", "legal", "life", "love", "marriage", "medical", "men",
        "money", "morning", "movies", "success"
      ];
      const randomIndex = Math.floor(Math.random() * wordsArray.length);
      this.category = wordsArray[randomIndex];

      try {
        const response = await fetch('https://api.api-ninjas.com/v1/quotes?category=' + wordsArray[randomIndex] + '&limit=3', {
          headers: { 'X-Api-Key': 'CsEjBGFzMdwAqyq0DNS+dw==myiH1A3xI5tDg9fr' },
          contentType: 'application/json'
        });

        const data = await response.json();
        const colors = ['primary', 'success', 'danger', 'info', 'purple', 'pink'];
        let colorIndex = 0;

        data.forEach(quote => {
          quote.color = colors[colorIndex % colors.length];
          colorIndex++;
        });

        this.quotes = data;
      } catch (error) {
        alert('Error fetching data');
      }
    }
  }
};
</script>