<template>
    <li class="card">
        <!-- <a class="card__link" href="#"></a> -->
        <p class="card__sale" v-if='card.price.old_price'>Скидка</p>
        <img class="card__img" :src='card.image.url' alt="Товар">
        <p class="card__article">{{card.code}}</p>
        <p class="card__title">{{card.name}}</p>
        <div class="card__price">
           <p class="card__price-old" v-if='card.price.old_price' >{{card.price.old_price}}₽</p> 
           <p class="card__price-new">{{card.price.current_price}}₽</p> 
        </div>
        <button class="card__btn-favorites"></button>
        <button class="card__btn-basket"></button>
    </li>
</template>

<script>
export default {
    props:{
        card: {
            type: Object,
            required: true
        }
    }
}
</script>

<style scoped>
     .card{
        border: 1px solid #EEEEEE;
        position: relative;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding: 9px 12px;
    }

    .card__sale{
        position: absolute;
        display: flex;
        justify-content: center;
        align-items: center;
        background: #EB5757;
        color: white;
        left: 0;
        top: 8px;
        width: 81px;
        height: 24px;
        margin: 0;
        
    }

    .card__sale_none{
        display: none;
    }

    .card__link{
        position: absolute;
        top: 0;
        right: 0;
        bottom: 0;
        left: 0;
        z-index: 1;
    }

    .card__img{
        width: 238px;
        height: 238px;
        margin: 0 auto 23px;
    }

    .card__article{
        font-family: SF UI Text;
        font-style: normal;
        font-weight: normal;
        font-size: 10px;
        line-height: 140%;
        margin: 0 0 5px;
    }

    .card__title{
        font-family: SF UI Text;
        font-style: normal;
        font-weight: 500;
        font-size: 16px;
        line-height: 140%;
        margin: 0 0 9px;
    }

    .card__price{
        display: flex;
        flex-direction: row;
    }

    .card__price-new{
        font-family: SF UI Text;
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 140%;
        margin: 0;
    }

    .card__price-old{
        font-family: SF UI Text;
        font-style: normal;
        font-weight: normal;
        font-size: 16px;
        line-height: 140%;
        margin: 0;
        text-decoration: line-through;
        margin-right: 10px;
    }

    .card__price-old_none{
        display: none;
    }

    .card__btn-favorites{
        position: absolute;
        right: 70px;
        bottom: 13px;
        border: none;
        width: 20px;
        height: 18px;
        background: url(../images/like.png);
    }

    .card__btn-basket{
        position: absolute;
        bottom: 13px;
        right: 22px;
        border: none;
        width: 19px;
        height: 18px;
        background: url(../images/basket.png);
    }
</style>