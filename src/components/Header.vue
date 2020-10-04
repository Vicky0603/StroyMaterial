<template>
  <header>
    <div class="top">
      <div class="container">
        <div class="left">
          <div class="location">
            <a href="#" class="small-text">
              <i class="icon-wrap"><img src="../assets/icon/location-icon.svg" alt="Локация"></i>
              <span>Волгоградская область</span>
            </a>
          </div>
        </div>
        <div class="right">
          <a href="#" class="small-text">Тендеры</a>
          <a href="#" class="small-text">База подрядчиков</a>
          <a href="#" class="small-text">
            Другие сервисы
            <i class="icon-wrap"><img src="../assets/icon/chevron-icon.svg" alt="Другие сервисы"></i>
          </a>
        </div>
      </div>
    </div>

    <div class="bottom">
      <div class="container">
        <router-link to="/" class="logo">
          <img src="../assets/img/logo.svg" alt="Стройпортал">
        </router-link>

        <button class="btn btn-menu">
          <i class="icon-wrap">
            <img src="../assets/icon/menu-icon.svg" alt="Каталог">
          </i>
          Каталог
        </button>

        <div class="form-search">
          <input type="text"
                 placeholder="Хочу найти..."
                 v-model="str"
                 @keyup="getSearch">
          <button >
            <i class="icon-wrap">
              <img src="../assets/icon/search-icon.svg" alt="Найти">
            </i>
          </button>

          <div class="search-list"
               v-if="afterSearchArr !== null">
            <div class="item-search"
                 v-for="item in afterSearchArr"
                 :key="item.id"
                 :itemSearch="item">
              {{item.title}}
            </div>
          </div>

        </div>

        <button class="btn btn-list">
          <i class="icon-wrap">
            <img src="../assets/icon/list-icon.svg" alt="Список">
          </i>
          Список
        </button>
        <div class="user-avatar">
          a
        </div>
      </div>
    </div>

  </header>
</template>

<style lang="scss">
header{
  .container{
    justify-content: space-between;
  }
  .top{
    display: flex;
    background: #FAFBFC;
    font-size: 12px;
    line-height: 20px;
    .right,
    .left{
      display: flex;
      width: fit-content;
    }
    .right{
      .small-text{
        margin: 0 24px;
        &:last-child{
          margin-right: 0;
        }
      }
    }
  }
  .bottom{
    padding: 18px 0;
    border: 1px solid #ECEFF1;
  }
}
</style>
<script>

export default {
  name: 'app-header',
  data: () => ({
    str: '',
    searchArr: [
      {
        title: 'a',
        id: 1
      },
      {
        title: 'as',
        id: 2
      },{
        title: 'asd',
        id: 3
      },{
        title: 'asdf',
        id: 4
      },{
        title: 'asdfg',
        id: 5
      },
    ],
    afterSearchArr: null
  }),
  methods: {
    async getSearch() {
      if(this.str !== ''){
        this.afterSearchArr = await this.searchArr
            .filter( item => {
              if(item.title.toLowerCase().indexOf(this.str.toLowerCase()) !== -1){
                return item;
              }
            })
      } else {
        this.afterSearchArr = null
      }
    }
  }
}
</script>
