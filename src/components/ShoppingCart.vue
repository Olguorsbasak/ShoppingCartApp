<template>
  <div class="card">
    <Carousel
      :value="products"
      :numVisible="3"
      :numScroll="1"
      :responsiveOptions="responsiveOptions"
      circular
      :autoplayInterval="3000"
    >
      <template #item="slotProps">
        <div
          class="border-1 surface-border border-round m-2 text-center py-5 px-3"
        >
          <div class="mb-3">
            <img
              :src="slotProps.data.image"
              :alt="slotProps.data.title"
              class="w-5rem shadow-2 h-5rem"
            />
          </div>
          <div>
            <h4 class="mb-1">{{ slotProps.data.title }}</h4>
            <h6 class="mt-0 mb-3">
              {{ slotProps.data.price }} {{ slotProps.data.currency }}
            </h6>
            <div class="mt-5">
              <Button icon="pi pi-search" rounded class="mr-2" />
              <Button
                icon="pi pi-star-fill"
                rounded
                severity="success"
                class="mr-2"
              />
              <Button icon="pi pi-cog" rounded severity="help" />
            </div>
          </div>
        </div>
      </template>
    </Carousel>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
      responsiveOptions: [
        {
          breakpoint: "20px",
          numVisible: 3,
          numScroll: 3,
        },
        {
          breakpoint: "20px",
          numVisible: 2,
          numScroll: 2,
        },
        {
          breakpoint: "20px",
          numVisible: 1,
          numScroll: 1,
        },
      ],
    };
  },
  async mounted() {
    try {
      const response = await fetch("https://fakestoreapi.com/products");
      const data = await response.json();
      this.products = data;
    } catch (error) {}
  },
  methods: {
    getSeverity(status) {
      return status === "available" ? "success" : "danger";
    },
  },
};
</script>

<style scoped></style>
