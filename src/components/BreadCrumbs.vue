<template>
   <section class="bread-crumbs">
       <ul class="bread-crumbs__list">
           <li class="bread-crumbs__item">
               <a class="bread-crumbs__link">Главная</a>
           </li>
           <li class="bread-crumbs__item">
               <a class="bread-crumbs__link">Системы хранения</a>
           </li>
           <li class="bread-crumbs__item bread-crumbs__item_last">
               <a class="bread-crumbs__link">Комплекты стеллажных систем</a>
           </li>
       </ul>
   </section>
</template>

<style scoped>
    .bread-crumbs{
        max-width: 1488px;
        margin: 32px auto 0;
        padding: 0 60px;
    }

    .bread-crumbs__list{
        display: flex;
        flex-direction: row;
        padding: 0;
        margin: 0;
    }

    .bread-crumbs__item{
        list-style-type: none;
        font-family: SF UI Text;
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 16px;
        color: #828282;
    }

    .bread-crumbs__item:not(:last-child)::after{
        content: '/';
        margin-left: 20px;
    }

    .bread-crumbs__item:nth-last-child(n+2){
        margin-right: 20px;
    }

    .bread-crumbs__item_last{
        color: black;
    }
</style>