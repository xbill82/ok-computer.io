<template>
  <section class="SupaBtn">
    <Logo class="Logo" @click="scrollToJumbotron" />
  </section>
  <section class="Jumbotron container" id="jumbotron">
    <h1 class="mb-4">ok-computer</h1>
    <h2 class="mb-7">freelance software engineer</h2>
    <div class="Separator"></div>
  </section>
  <section class="Features container grid">
    <div class="Feature-LLM col-4">
      <IconLLM />
      <h3 class="mt-4">LLM Engineering</h3>
      <p class="Feature-description font-bold">
        Building transformative applications with state-of-the-art AI models.
      </p>
      <p class="Feature-description">
        Unlock the full potential of artificial intelligence with cutting-edge
        Large Language Models.
      </p>
    </div>
    <div class="Feature-Tech col-4">
      <IconCog />
      <h3 class="mt-4">Tech Consulting</h3>
      <p class="Feature-description font-bold">
        Strategic guidance to bridge your technology and business goals.
      </p>
      <p class="Feature-description">
        Achieve your vision with expert consulting that aligns technology with
        your strategic objectives.
      </p>
    </div>
    <div class="Feature-CTO col-4">
      <IconCTO />
      <h3 class="mt-4">CTO as a Service</h3>
      <p class="Feature-description font-bold">
        Your on-demand CTO for innovation and sustainable growth.
      </p>
      <p class="Feature-description">
        Access experienced technical leadership without the overhead of a
        full-time hire.
      </p>
    </div>
  </section>
  <section class="About container">
    <div class="Separator"></div>
    <h1 class="mt-7 mb-4">luca marchesini</h1>
    <h3 class="About-email">luca@ok-computer.io</h3>
  </section>
</template>

<script setup>
import IconLLM from "@/components/IconLLM.vue";
import IconCog from "@/components/IconCog.vue";
import IconCTO from "@/components/IconCTO.vue";

function scrollToJumbotron() {
  document.getElementById("jumbotron").scrollIntoView({ behavior: "smooth" });
}
</script>

<style lang="scss">
.container {
  width: 100vw;
  padding: 5em 25%;
}

.SupaBtn {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}

.Separator {
  height: 1px;
  width: 50%;
  background-color: #33363f;
}

.Logo {
  width: 50%;
  cursor: pointer;
}

.Feature-description {
  font-size: 1.2rem;
  font-family: Helvetica, Arial, sans-serif;
}

.About-email {
  font-family: "LDN Modern No2 Italic", sans-serif;
}
</style>
