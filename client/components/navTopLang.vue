<template>
    <ul class="lang_parrent">
        <li class="lang_child" @click.prevent="langActive = true">
            <nuxt-link to="#!" class="lang_link" :class="{'active' : langActive}">RU</nuxt-link>
        </li>
            <span class="splash">/</span>
        <li class="lang_child" @click.prevent="langActive = false">
            <nuxt-link to="#!" class="lang_link" :class="{'active' : !langActive}" >UZ</nuxt-link>
        </li>
    </ul>
</template>
<script>
export default {
    data:()=>({
        langActive:true
    })
}
</script>
<style lang="scss" scoped>
.lang_parrent{
 display: flex;
 align-items: center;
 .lang_child{
     list-style: none;
    .lang_link{
        font-style: normal;
        font-weight: bold;
        font-size: 15px;
        line-height: 18px;
        color: #C0C0C0;
        text-decoration: none;
        &.active{
         color: #01BEDE;
        }
    }
 }
 .splash{
     margin-left: 10px;
     margin-right: 10px;
     color: #C0C0C0;
     font-weight: bold;
     font-size: 15px;
     line-height: 18px;
 }
}
</style>