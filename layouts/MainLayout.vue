<template>
  <div id="MainLayout" class="w-full fixed z-50">
    <div id="TopMenu" class="w-full bg-[#FAFAFA] border-b md:block hidden">
      <ul
        class="flex items-center justify-end text-xs text[-#333333] font-light px-2 h-10 bg-[#fafafa] max-w-[1200px]"
      >
        <li
          class="border-r border-r-gray-400 px-3 hover:text-[#ff4646] cursor-pointer"
        >
          Sell On AliExpress
        </li>
        <li
          class="border-r border-r-gray-400 px-3 hover:text-[#ff4646] cursor-pointer"
        >
          Coockie Preferrance
        </li>
        <li
          class="border-r border-r-gray-400 px-3 hover:text-[#ff4646] cursor-pointer"
        >
          Buyer protection
        </li>
        <li
          class="border-r border-r-gray-400 px-3 hover:text-[#ff4646] cursor-pointer"
        >
          Help
        </li>
        <li class="px-3 hover:text-[#ff4646] cursor-pointer">
          <Icon name="ic:sharp-install-mobile" size="17" />
          App
        </li>
        <li
          class="relative flex items-center px-2.5 hover:text-[#ff4646] h-full cursor-pointer"
          :class="
            isAccountMenue
              ? 'bg-white border z-40 shadow-[0_15px_100px_40px_rgba(0,0,0,0.3)]'
              : 'border border-[#fafafa]'
          "
          @mouseenter="isAccountMenue = true"
          @mouseleave="isAccountMenue = false"
        >
          <Icon name="ph:user-thin" size="17" />Account
          <Icon name="mdi:chevron-down" size="15" class="ml-5" />
          <div
            v-if="isAccountMenue"
            id="AccountMenu"
            class="absolute bg-white w-[220px] text-[#333333] z-40 top-[38px] -left-[100px] border-x border-b"
          >
            <div v-if="true">
              <div class="text-semibold text-[15px] my-4 px-3">
                Welcome to AliExpress
              </div>
              <div class="flex items-center gap-1 px-3 mb-3">
                <NuxtLink
                  to="/auth"
                  class="text-white font-semibold p-2 bg-[#ff4646] text-center w-full text-[16px] rounded-sm"
                  >Login / Register
                </NuxtLink>
              </div>
            </div>
            <div class="border-b">
              <ul class="bg-white">
                <li
                  @click="navigateTo('/orders')"
                  class="text-[13px] py-2 px-4 w-full hover:bg-gray-200"
                >
                  My Orders
                </li>
                <li
                  v-if="true"
                  @click="navigateTo('/orders')"
                  class="text-[13px] py-2 px-4 w-full hover:bg-gray-200"
                >
                  Sign-out
                </li>
              </ul>
            </div>
          </div>
        </li>
      </ul>
    </div>
    <div class="flex items-center w-full bg-white" id="MainHeader">
      <div
        class="flex bg-white lg:justify-start justify-between gap-10 max-w-[1150px] w-full px-3 py-5 mx-auto"
      >
        <NuxtLink to="/" class="min-w-[170px]">
          <img src="/AliExpress-logo.png" width="170" />
        </NuxtLink>
        <div class="max-w-[700px] w-full md:block hidden">
          <div class="relative">
            <div
              class="flex items-center border-2 border-[#FF4646] rounded-md w-full"
            >
              <input
                class="w-full placeholder-gray-400 text-sm pl-3 focus:outline-none"
                placeholder="kitchen accessories"
                type="text"
                v-model="searchItem"
              />
              <Icon
                v-if="isSearching"
                name="eos-icons:loading"
                size="25"
                class="mr-2"
              />
              <button
                class="flex items-center h-[100%] p-1.5 px-2 bg-[#FF4646]"
              >
                <Icon name="ph:magnifying-glass" size="20" color="#ffffff" />
              </button>
            </div>
          </div>
        </div>
        <!-- cut -->
      </div>
    </div>
  </div>
</template>

<script setup>
let isAccountMenue = ref(false);
let isSearching = ref(true);
let searchItem = ref("");
</script>
