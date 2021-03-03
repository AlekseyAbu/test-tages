<template>
    <section class="catalog-header">
        <h2 class="catalog-header__title">Комплекты стеллажных систем</h2>
        <div class="catalog-header__sorts">
            <div class="catalog-header__sort">
                <span class="catalog-header__select-title">Сортировать по:</span>
                <select class="catalog-header__select" v-model="price" @change="handleSelectPrice">
                    <option class="catalog-header__option" value="ascending">По возрастанию</option>
                    <option class="catalog-header__option" value="descending">По убыванию</option>
                </select>
            </div>
            <div class="catalog-header__sort">
                <span class="catalog-header__select-title">Материал</span>
                <select class="catalog-header__select" v-model="material" @change='handleSelectMaterial'>
                    <option class="catalog-header__option" value="metal">Металл</option>
                    <option class="catalog-header__option" value="wood">Дерево</option>
                </select>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return{
            material: '',
            price: ''
        }
    },
    methods: {
        handleSelectMaterial() {
            console.log(this.material)
            this.$emit('handleMaterial', this.material)
        },
        handleSelectPrice() {
            this.$emit('handlePrice', this.price)
        }
    },
    computed: {

    }
    
}
</script>

<style scoped>
    .catalog-header{
        max-width: 1488px;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        margin: 0 auto;
        padding: 0 60px;
    }

    .catalog-header__title{
        font-family: SF Pro Display;
        font-style: normal;
        font-weight: 600;
        font-size: 36px;
        line-height: 48px;
        margin: 0;
        margin-top: 32px;
    }

    .catalog-header__select{
        position: relative;
        border: none;
        padding-left: 16px;
        
    }

    .catalog-header__select-title{
        font-family: SF Pro Display;
        font-style: normal;
        font-weight: normal;
        font-size: 12px;
        line-height: 150%;
    }

    .catalog-header__sorts{
        display: flex;
        flex-direction: row;
    }

    .catalog-header__sort{
        display: flex;
        flex-direction: column;
        margin-right: 24px;
        margin-top: 32px;
        align-items: flex-start;
    }

    .catalog-header__select-title{
        padding-left: 15px;
    }

    .catalog-header__select{
        height: 40px;
        width: 288px;
        background-color: #F2F2F2;
        
    }

    .catalog-header__option{
        font-family: SF Pro Display;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 150%;
    }
</style>