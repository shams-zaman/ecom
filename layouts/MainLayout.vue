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
          ></div>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
let isAccountMenue = ref(false);
</script>
