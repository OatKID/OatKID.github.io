<template>
  <div class="Header">
        <div class="NavBar">
            <div class="leftBar">oatkid</div>
			<div class="rightBar">
                <NuxtLink class="goPage" to="/"><Icon name="ic:baseline-home" size="24px"/>Home</NuxtLink>
                <NuxtLink class="goPage" to="/SkillPage"><Icon name="hugeicons:laptop-programming" />Skill</NuxtLink>
                <NuxtLink class="goPage" to="#">Project</NuxtLink>
                <NuxtLink class="goPage" to="#">About</NuxtLink>
            </div>
            <div class="menuIcon" @click="showMenu"><Icon name="material-symbols:menu" /></div>
        </div>
        <div class="HomeImg">
            <img src="/assets/img/homepage.jpg"/>
            <div class="profile">
                <div class="speech" v-if="banner">
                    <h2>
                        <span>Hi</span>
                        <br>
                        I'm Siwakorn Pasawang (Oat).
                        <br>
                        I achieve my projects !!
                        
                    </h2>
                </div>
                <div class="profileImg" v-if="banner">
                    <img src="~/assets/img/profile.jpg" alt="" srcset="">
                </div>

                <div class="title" v-if="showTitle">
                    <h2>{{ titlePage }}</h2>
                </div>
            </div>
        </div>
    </div>

    <div class="menuPage" id="menuList">
            <div class="closeMark" @click="closeMenu"><Icon name="entypo:cross" size="32px"/></div>
            <div class="listGoPage">
                <NuxtLink class="goPage" to="/"><Icon name="ic:baseline-home" size="32px"/>Home</NuxtLink>
                <NuxtLink class="goPage" to="/SkillPage"><Icon name="hugeicons:laptop-programming" size="32px"/>Skill</NuxtLink>
                <NuxtLink class="goPage" to="#">Project</NuxtLink>
                <NuxtLink class="goPage" to="#">About</NuxtLink>
            </div>
    </div>

</template>

<script lang="ts" setup>

    defineProps({
      banner: {
        type: Boolean,
        default: false
      },
      titlePage: String,
      showTitle: {
        type: Boolean,
        default: false
      }
    })
    function showMenu(){
        const menuList = document.getElementById("menuList")!;
        menuList.style.width = "200px";
    };

    function closeMenu(){
        const menuList = document.getElementById("menuList")!;
        menuList.style.width = "0";
    };
</script>

<style>

</style>