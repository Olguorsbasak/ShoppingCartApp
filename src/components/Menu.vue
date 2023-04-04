<template>
  <div class="min-h-screen flex relative lg:static bg-bluegray-200">
    <div
      class="h-screen hidden lg:block flex-shrink-0 absolute lg:static left-0 top-0 z-1 select-none w-8rem bg-bluegray-800 animation-duration-300 animation-ease-in-out"
    >
      <div class="flex flex-column h-full">
        <div
          class="flex align-items-center justify-content-center flex-shrink-0"
          style="height: 60px"
        >
          <img
            class="mt-8"
            src="../assets/images/homeicons.png"
            alt="ShoppingCartIcon"
            height="40"
          />
        </div>
        <div class="my-3 p-3 pt-5">
          <span class="p-input-icon-left">
            <i class="pi pi-search text-bluegray-200"></i>
            <InputText
              type="text"
              class="appearance-none border-none bg-bluegray-700 text-bluegray-200 w-full"
            />
          </span>
        </div>
        <div class="overflow-y-auto">
          <ul class="list-none p-3 m-0 flex flex-wrap">
            <li class="w-12 text-center">
              <a
                v-ripple
                class="cursor-pointer inline-flex align-items-center justify-content-center border-3 border-bluegray-900 hover:bg-bluegray-700 active:bg-bluegray-400 text-bluegray-200 hover:text-bluegray-100 transition-colors transition-duration-150 p-ripple"
                style="width: 80px; height: 80px; border-radius: 50px"
              >
                <i class="pi pi-home text-2xl"></i>
              </a>
              <div class="mt-4 mb-5 text-bluegray-200 font-medium text-sm">
                Home
              </div>
            </li>
            <li class="w-12 text-center">
              <a
                v-ripple
                class="cursor-pointer inline-flex align-items-center justify-content-center border-3 border-bluegray-900 hover:bg-bluegray-700 active:bg-bluegray-400 text-bluegray-200 hover:text-bluegray-100 transition-colors transition-duration-150 p-ripple"
                style="width: 80px; height: 80px; border-radius: 50px"
              >
                <i class="pi pi-star-fill text-2xl"></i>
              </a>
              <div class="mt-4 mb-4 text-bluegray-200 font-medium text-sm">
                Favorites
              </div>
            </li>
            <li class="w-12 text-center mt-3">
              <a
                v-ripple
                class="cursor-pointer inline-flex align-items-center justify-content-center border-3 border-bluegray-900 hover:bg-bluegray-700 active:bg-bluegray-400 text-bluegray-200 hover:text-bluegray-100 transition-colors transition-duration-150 p-ripple"
                style="width: 80px; height: 80px; border-radius: 50px"
              >
                <i class="pi pi-calculator text-2xl"></i>
              </a>
              <div class="mt-4 text-bluegray-200 font-medium text-sm">Sale</div>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="min-h-screen flex flex-column relative flex-auto">
      <div
        class="flex justify-content-between align-items-center px-5 bg-bluegray-200 relative lg:static bg-bluegray-200"
        style="height: 80px"
      >
        <p class="font-bold text-2xl text-white-alpha-90">Shopping Cart</p>
      </div>
      <div class="flex flex-column flex-auto">
        <div class="border-2 surface-border border-round bg-gray-200 flex-auto">
          <ShoppingCart :shoppingcart="shoppingcart" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ShoppingCart from "/src/components/ShoppingCart.vue";
export default {
  components: {
    ShoppingCart,
  },
};
</script>
