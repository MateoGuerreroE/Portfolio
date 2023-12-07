<script setup>
const { data: posts } = await useAsyncData("latest-posts", () =>
  queryContent("/blog").sort({ data: 1 }).limit(3).find()
);
</script>

<template>
  <section>
    <h1 class="text-5xl font-bold mt-20">👋🏻 Hello, I'm Mateo Guerrero!</h1>
    <p class="text-base text-gray-900 p-2 italic">Full Stack Web Developer</p>
  </section>
  <section class="flex flex-col md:flex-row">
    <div class="md:w-3/4">
      <h2 class="text-3xl font-bold mt-8">My Story</h2>
      <p class="text-lg py-2">
        I am a student of Software Engineering at Saint Leo University USA,
        currently living in Colombia's capital Bogota. I started programming
        really early in school and have gather some skills by myself and also
        some great Bootcamps to start this programing journey on Web
        Development. My background.
      </p>
      <p class="text-lg py-2">
        During my life journey, I discovered a great passion about finance,
        which in 2018 made me start studing about financial markets and has led
        me to participate in great projects on positions as great as Risk
        management director. I've been a teacher on this matter for several
        years, educating hundreds of students in a US academy for two long
        years, and now as an independent teacher for just some small groups.
      </p>
      <p class="text-lg py-2">
        My background, my studies and my ease with mathematics and logic
        problems, makes me a really enthusiastic student of languages and
        technologies, and I am eager to be part of important projects to learn
        and provide my skills.
      </p>
    </div>
    <img
      src="../assets/images/profile-picture.JPG"
      alt="Profile Photo"
      class="w-1/2 h-1/2 md:max-w-sm p-8 mx-auto"
    />
  </section>
  <section>
    <h2 class="text-3xl font-bold mt-8">Latest Blog Posts</h2>
    <div class="grid md:grid-cols-3 pt-8 gap-5">
      <Post :posts="posts" />
    </div>
  </section>
</template>
