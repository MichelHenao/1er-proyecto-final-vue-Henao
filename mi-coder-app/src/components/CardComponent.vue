<template>
    <div>
      <b-card
        v-for="(card, index) in cardData"
        :key="index"
        :title="card.title"
        :img-src="card.imgSrc"
        :img-alt="card.imgAlt"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-2"
      >
        <b-card-text>{{ card.description }}</b-card-text>
        <b-button @click="addToCart(card)" variant="primary">Agregar al carrito</b-button>
      </b-card>
    </div>
  </template>
  
  <script>
  export default {
    name:'CardComponent',
    data() {
      return {
        cardData: [
          {
            title: "Card Title 1",
            imgSrc: "https://picsum.photos/600/300/?image=25",
            imgAlt: "Image 1",
            description: "Some quick example text for card 1",
            link: "#"
          },
          {
            title: "Card Title 2",
            imgSrc: "https://picsum.photos/600/300/?image=26",
            imgAlt: "Image 2",
            description: "Some quick example text for card 2",
            link: "#"
          },
          {
            title: "Card Title 1",
            imgSrc: "https://picsum.photos/600/300/?image=25",
            imgAlt: "Image 1",
            description: "Some quick example text for card 1",
            link: "#"
          },
          {
            title: "Card Title 2",
            imgSrc: "https://picsum.photos/600/300/?image=26",
            imgAlt: "Image 2",
            description: "Some quick example text for card 2",
            link: "#"
          },
          {
            title: "Card Title 1",
            imgSrc: "https://picsum.photos/600/300/?image=25",
            imgAlt: "Image 1",
            description: "Some quick example text for card 1",
            link: "#"
          },
          {
            title: "Card Title 2",
            imgSrc: "https://picsum.photos/600/300/?image=26",
            imgAlt: "Image 2",
            description: "Some quick example text for card 2",
            link: "#"
          },
          // Agrega más elementos al array según necesites
        ]
      };
    },
    methods: {
      addToCart(card) {
        // Aquí puedes realizar la lógica para agregar el elemento al carrito
        // Puedes acceder a los datos de la card a través del parámetro 'card'
        console.log("Agregado al carrito:", card);
        // Redirecciona al componente del carrito
        this.$router.push("/carrito");
      }
    }
  };
  </script>

<style scoped>
.card-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.card-item {
  width: 20rem;
  margin: 10px;
  max-width: 20rem;
}
</style>
  