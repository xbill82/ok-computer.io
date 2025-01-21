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
  <section class="container About">
    <div class="Separator"></div>
    <h1 class="mt-7 mb-4">luca marchesini</h1>
    <h3 class="About-email">luca@ok-computer.io</h3>
    <div class="About-socials mt-4">
      <a href="https://www.linkedin.com/in/luca-marchesini-738a1816/"
        ><i class="pi pi-linkedin mr-4" style="font-size: 2.5rem"></i
      ></a>
      <a href="https://github.com/xbill82"
        ><i class="pi pi-github mr-4" style="font-size: 2.5rem"></i
      ></a>
    </div>
  </section>
  <section v-if="theySay.length > 0" class="container Claims">
    <div class="Separator"></div>
    <h1 class="mb-4">they say</h1>
    <Carousel
      :value="theySay"
      :items-per-page="1"
      :circular="true"
      autoplay-interval="10000"
    >
      <template #item="slotProps">
        <div class="Claim mx-4">
          <Avatar
            class="Avatar"
            :image="slotProps.data.image"
            size="small"
            shape="circle"
          />
          <p class="Feature-description mt-4">"{{ slotProps.data.quote }}"</p>
          <h4 class="mt-4">
            {{ slotProps.data.name }} - {{ slotProps.data.title }}
          </h4>
        </div>
      </template>
    </Carousel>
  </section>
  <section class="container">
    <div class="Separator"></div>
    <h1 class="mb-4">I have spoken</h1>
    <iframe
      width="560"
      height="315"
      src="https://www.youtube.com/embed/uYwikKPHGbU?si=LIWuyEn78OJ5zXku"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen
    ></iframe>
    <div class="mb-4"></div>
    <iframe
      width="560"
      height="315"
      src="https://www.youtube.com/embed/wtURpqTgtUs?si=OqmNI-7coqbWAN70"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen
    ></iframe>
    <div class="mb-4"></div>
    <iframe
      width="560"
      height="315"
      src="https://www.youtube.com/embed/FI4FrMBRjgQ?si=PFRk0U2RatkwqDqi"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen
    ></iframe>
  </section>
  <section class="Contact container">
    <div class="Separator"></div>
    <h1 class="mb-4">get in touch</h1>
    <p>I'm always looking for new challenges to help you achieve your goals.</p>
    <PVTextarea v-model="message" class="HireMeTextarea" />
    <div class="mt-4 flex align-items-center">
      <a
        :href="`mailto:luca@ok-computer.io?body=${encodeURIComponent(message)}`"
        ><Logo class="HireMeBtn"
      /></a>
      <span class="ml-2 HireMeBtnCaption">(just sends an email)</span>
    </div>
  </section>
  <section class="Footer">
    <div class="container mt-4">
      <div>ok-computer.io is owned and operated by Luca Marchesini.</div>
      <div class="my-2">
        <a href="https://www.linkedin.com/in/luca-marchesini-738a1816/"
          >LinkedIn</a
        >
        ·
        <a href="https://github.com/xbill82">GitHub</a>
      </div>
      <div class="mt-4">Handcrafted with ❤️ in Montpellier, France.</div>
    </div>
  </section>
</template>

<script>
import IconLLM from "@/components/IconLLM.vue";
import IconCog from "@/components/IconCog.vue";
import IconCTO from "@/components/IconCTO.vue";
import Avatar from "primevue/avatar";
import Carousel from "primevue/carousel";
import Textarea from "primevue/textarea";

export default {
  components: {
    IconLLM,
    IconCog,
    IconCTO,
    Avatar,
    Carousel,
    PVTextarea: Textarea,
  },
  data() {
    return {
      message: "",
      theySay: [
        // {
        //   image:
        //     "https://media.licdn.com/dms/image/v2/C4E03AQG8upjZBjy23w/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1617115166383?e=1743033600&v=beta&t=0CQTPMMPpxnvccL6pqLhmnHpCANwK7wMWV4cxjo5SzI",
        //   name: "Françoise Nauton-Inglis",
        //   title: "CEO, Spiriit.com",
        //   quote:
        //     "Luca is a true professional. He is a great problem solver and has a knack for finding creative solutions to complex issues. He is also a great communicator and always keeps his clients updated on the progress of their projects.",
        // },
        // {
        //   image:
        //     "https://media.licdn.com/dms/image/v2/D4E03AQGPG7FUZAILLA/profile-displayphoto-shrink_400_400/profile-displayphoto-shrink_400_400/0/1673954685532?e=1743033600&v=beta&t=zfyVPAHnXw-eBbxLsqCMu3mQzy6VGLU6n8MzAcqOiao",
        //   name: "Benjamin Vergnet",
        //   title: "Founder & CEO, Tresovista.com",
        //   quote:
        //     "Luca is a true professional. He is a great problem solver and has a knack for finding creative solutions to complex issues. He is also a great communicator and always keeps his clients updated on the progress of their projects.",
        // },
      ],
    };
  },
  methods: {
    scrollToJumbotron() {
      document
        .getElementById("jumbotron")
        .scrollIntoView({ behavior: "smooth" });
    },
  },
};
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

// .About {
//   padding-bottom: 0;
// }

.About-socials a {
  color: #33363f;
  opacity: 0.8;
  transition: opacity 0.3s ease;

  &:hover {
    opacity: 1;
  }
}

// .Claims {
//   padding-bottom: 0;
// }

.Avatar {
  --p-avatar-width: 100px;
  --p-avatar-height: 100px;

  img {
    filter: grayscale(100%);
  }
}

.Footer {
  background-color: #dfd8bd;
  color: #5a5d6d;
  font-size: 0.8rem;
}

.HireMeBtn {
  cursor: pointer;
  height: 50px;
}

.HireMeBtnCaption {
  font-size: 0.7rem;
  font-family: Helvetica, Arial, sans-serif;
  color: #5a5d6dcd;
  opacity: 0.8;
}

.HireMeTextarea {
  width: 100%;
  height: 250px;
  --p-textarea-background: #dfd8bd;
  --p-textarea-padding-x: 15px;
  --p-textarea-padding-y: 15px;
  --p-textarea-color: #5a5d6d;
  --p-textarea-border-radius: 5px;
}
</style>
