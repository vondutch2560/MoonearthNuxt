<template>
  <header>
    <div class="top-bar">
      <div class="row row-top-bar">
        <p class="welcome">Welcome to Moon & Earth Shop</p>
      </div>
    </div>
    <div class="header">
      <div class="row">
        <div class="logo">
          <a href="javascript:;">
            <img src="~assets/images/logo-300x300.jpg" alt="Logo Moon&Earth" />
          </a>
        </div>
        <div class="menu">
          <ul class="parent-menu">
            <li><NuxtLink to="/">HOME</NuxtLink></li>
            <li>
              <a href="javascript:;">SẢN PHẨM</a>
              <ul>
                <li><a href="javascript:;">Đồng Hồ</a></li>
                <li><a href="javascript:;">Key Holder</a></li>
              </ul>
            </li>
            <li><a href="javascript:;">GÓC CHIA SẺ</a></li>
            <li><NuxtLink to="/contact">LIÊN HỆ</NuxtLink></li>
          </ul>
        </div>
      </div>
    </div>
  </header>
</template>
