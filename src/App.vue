<template>
  <!-- 追加 1 -->
  <authenticator>
      <main>
        <header>
          <h2>Amplify × Vue × Vite</h2>
          <nav class="nav">
            <ul class="list">
              <li><router-link class="routerLink" to="/">Home</router-link></li>
              <li><router-link class="routerLink" to="/chat">Chat</router-link></li>
              <li><router-link class="routerLink" to="/ai">AI</router-link></li>
              <li><router-link class="routerLink" to="/geo">Geo</router-link></li>
            </ul>
          </nav>
        </header>
        <section>
          <router-view/>
        </section>
      </main>
  <!-- 追加 2 -->
  </authenticator>
</template>

<style>
@import '@/assets/base.css';
</style>
