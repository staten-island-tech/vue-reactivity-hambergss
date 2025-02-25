<template>
  <div>
    <header
      class="bg-[#f2ecea] text-[#15162d] p-10 text-center flex flex-col items-center space-y-2"
    >
      <h1 class="text-3xl font-bold">Welcome to Switch Store!</h1>
      <FilterButtons :filterSwitches="filterSwitches" />
    </header>
    <div class="flex mt-6">
      <div class="bg-[#fba5a0] w-3/4 p-6 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
        <SwitchCards v-for="item in switches" :key="item.name" :switchItem="item">
          <button
            class="btn btn-primary bg-[#28d6b0] hover:bg-[#2bb698] mt-4 rounded-lg shadow-sm outline outline-2 outline-[#15162d] text-[#15162d]"
            @click="addToCart(item)"
          >
            Add to Cart
          </button>
        </SwitchCards>
      </div>
    </div>
    <ShoppingCart
      :cart="cart"
      :quantityFinder="quantityFinder"
      :removeFromCart="removeFromCart"
      :totalPrice="totalPrice"
    />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'
import SwitchCards from '@/components/SwitchCards.vue'
import ShoppingCart from './components/ShoppingCart.vue'
import FilterButtons from './components/FilterButtons.vue'

const allSwitches = ref([
  {
    manufacturer: 'Gateron',
    name: 'Gateron Milky Red Pro (KS-3)',
    type: 'linear',
    sound: 'creamy',
    price: 1.99,
    imageUrl: '/images/gateronMRP.png',
  },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Milky Yellow Pro (KS-3)',
    type: 'linear',
    sound: 'creamy',
    price: 2.49,
    imageUrl: '/images/gateronMYP.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Poro',
    type: 'linear',
    sound: 'thocky',
    price: 4.99,
    imageUrl: '/images/hmxPoro.png',
  },
  {
    manufacturer: 'KTT',
    name: 'KTT Strawberry',
    type: 'linear',
    sound: 'creamy',
    price: 3.49,
    imageUrl: '/images/kttStrawberry.png',
  },
  {
    manufacturer: 'Wuque Studios',
    name: 'WS Morandi',
    type: 'linear',
    sound: 'creamy',
    price: 5.49,
    imageUrl: '/images/wsMorandi.png',
  },
  {
    manufacturer: 'Akko',
    name: 'V3 Cream Yellow Pro',
    type: 'linear',
    sound: 'creamy',
    price: 2.99,
    imageUrl: '/images/creamYP.png',
  },
  {
    manufacturer: 'Gateron',
    name: 'G Pro 3.0 Brown',
    type: 'tactile',
    sound: 'thocky',
    price: 2.19,
    imageUrl: '/images/gProBrown.png',
  },
  {
    manufacturer: 'Akko',
    name: 'Penguin',
    type: 'tactile',
    sound: 'thocky',
    price: 3.99,
    imageUrl: '/images/penguin.png',
  },
  {
    manufacturer: 'KTT',
    name: 'Sea Salt Lemon',
    type: 'tactile',
    sound: 'thocky',
    price: 2.79,
    imageUrl: '/images/ssLemon.png',
  },
  {
    manufacturer: 'Invyr',
    name: 'Holy Panda',
    type: 'tactile',
    sound: 'thocky',
    price: 5.99,
    imageUrl: '/images/holyPanda.png',
  },
  {
    manufacturer: 'Akko',
    name: 'V3 Creamy Purple Pro',
    type: 'tactile',
    sound: 'thocky',
    price: 3.29,
    imageUrl: '/images/creamPP.png',
  },
  {
    manufacturer: 'Outemu',
    name: 'Blue',
    type: 'clicky',
    sound: 'clicky',
    price: 1.89,
    imageUrl: '/images/outemuBlue.png',
  },
  {
    manufacturer: 'Gateron',
    name: 'Melodic',
    type: 'clicky',
    sound: 'clicky',
    price: 2.29,
    imageUrl: '/images/gateronMelodic.png',
  },
  {
    manufacturer: 'Akko',
    name: 'Creamy Cyan',
    type: 'clicky',
    sound: 'clicky',
    price: 2.59,
    imageUrl: '/images/creamCyan.png',
  },
  {
    manufacturer: 'Wuque Studios',
    name: 'WS POM+',
    type: 'linear',
    sound: 'thocky',
    price: 4.49,
    imageUrl: '/images/wsPom.png',
  },
  {
    manufacturer: 'Gateron',
    name: 'Smoothie',
    type: 'linear',
    sound: 'thocky',
    price: 2.99,
    imageUrl: '/images/gateronSmoothie.png',
  },
  {
    manufacturer: 'HMX',
    name: 'Silent Sakura',
    type: 'linear',
    sound: 'silent',
    price: 3.19,
    imageUrl: '/images/silentSakura.png',
  },
  {
    manufacturer: 'Wuque Studios',
    name: 'WS Silent Tactile',
    type: 'tactile',
    sound: 'silent',
    price: 2.79,
    imageUrl: '/images/wsSilentTact.png',
  },
  {
    manufacturer: 'TTC',
    name: 'Silent Bluish White V2',
    type: 'tactile',
    sound: 'silent',
    price: 3.49,
    imageUrl: '/images/silentBW.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Cheese',
    type: 'linear',
    sound: 'clacky',
    price: 4.79,
    imageUrl: '/images/hmxCheese.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Xinhai',
    type: 'linear',
    sound: 'clacky',
    price: 4.29,
    imageUrl: '/images/hmxXinhai.png',
  },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Quinn',
    type: 'tactile',
    sound: 'clacky',
    price: 3.99,
    imageUrl: '/images/gateronQuinn.png',
  },
  {
    manufacturer: 'Gateron',
    name: 'Gateron Baby Kangaroo (V2)',
    type: 'tactile',
    sound: 'clacky',
    price: 3.69,
    imageUrl: '/images/gateronBKang.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Swift',
    type: 'linear',
    sound: 'clacky',
    price: 4.89,
    imageUrl: '/images/hmxSwift.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Deep Navy',
    type: 'linear',
    sound: 'clacky',
    price: 4.59,
    imageUrl: '/images/hmxDeepNavy.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Macchiato',
    type: 'linear',
    sound: 'clacky',
    price: 5.29,
    imageUrl: '/images/hmxMacchiato.png',
  },
  {
    manufacturer: 'HMX',
    name: 'HMX Sunset Gleam',
    type: 'linear',
    sound: 'clacky',
    price: 4.99,
    imageUrl: '/images/hmxSunGleam.png',
  },
])

const cart = ref([])

const switches = ref(allSwitches.value)

const filterSwitches = (type) => {
  if (type === 'all') {
    switches.value = allSwitches.value
  } else {
    switches.value = allSwitches.value.filter((item) => item.type === type)
  }
}

const addToCart = (switchItem) => {
  const existingItem = cart.value.find((item) => item.name === switchItem.name) //finds if the item is already in the shoppin cart
  if (existingItem) {
    existingItem.quantity += 1
  } else {
    cart.value.push({
      name: switchItem.name,
      type: switchItem.type,
      price: switchItem.price,
      quantity: 1,
    })
  }
}

const removeFromCart = (item) => {
  const index = cart.value.findIndex((cartItem) => cartItem.name === item.name) //finds the index of the item in the cart
  if (index !== -1) {
    if (cart.value[index].quantity > 1) {
      cart.value[index].quantity -= 1
    } else {
      cart.value.splice(index, 1)
    }
  }
}

const quantityFinder = (item) => {
  const cartItem = cart.value.find((cartItem) => cartItem.name === item.name)
  return cartItem ? cartItem.quantity : 0 //returns the items quantity if found or 0 if not
}

const totalPrice = computed(() => {
  return cart.value.reduce((total, cartItem) => total + cartItem.price * cartItem.quantity, 0)
})
</script>

<style scoped>
body {
  font-family: 'Inter', sans-serif;
}
</style>
