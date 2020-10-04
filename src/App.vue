<template>
  <div id="app">
    <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from "@/components/Header"

export default {
  components: {
    Header
  }
}

</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300;0,400;0,600;0,700;0,800;1,300;1,400;1,600;1,700;1,800&display=swap');
// font-family: 'Open Sans', sans-serif;

$color-secondary: #708598;
$color-btn: #050F19;
$bg-btn-menu: #FED83D;
$bg-avatar: #9B51E0;

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Open Sans', sans-serif;
}
a{
  text-decoration: none;
  color: inherit;
  display: flex;
  align-content: center;
}
button{
  display: flex;
  align-items: center;
  color: $color-btn;
  font-weight: 600;
  font-size: 14px;
  border: none;
}
.container{
  display: flex;
  width: 100%;
  max-width: 1110px;
  margin: 0 auto;
  padding: 6px;
}
.small-text{
  font-size: 12px;
  display: flex;
  align-items: center;
  color: $color-secondary;
}
.icon-wrap{
  padding: 0 6px;
  display: flex;
  align-items: center;
}
.btn{
  padding: 8px 16px;
  display: flex;
  align-items: center;
  border-radius: 4px;
}
.btn-menu{
  background-color: $bg-btn-menu;
}
.btn-list{
  border: 1px solid #ECEFF1;
  background: #FAFBFC;
}

.user-avatar{
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
  font-weight: 600;
  font-size: 14px;
  background-color: $bg-avatar;
  text-transform: uppercase;
}
.form-search{
  display: flex;
  position: relative;
  align-items: center;
  input{
    min-width: 526px;
  }
  button{
    position: absolute;
    right: 8px;
    background-color: #fff;
    i{
      padding: 0;
    }
  }
}
input{
  padding: 12px 14px;
  font-size: 14px;
  border-radius: 4px;
  border: 1px solid #ECEFF1;
  &::placeholder{
    color: $color-secondary;
  }
}
.search-list{
  position: absolute;
  top: 47px;
  width: 100%;
  padding: 0 5px;
  background-color: #fff;
  border: 1px solid #ECEFF1;
  border-radius: 4px;
  .item-search{
    padding: 3px 5px;
    border-bottom: 1px solid #ECEFF1;
    width: 100%;
    &:last-child{
      border: none;
    }
    &:hover{
      background-color: #ECEFF1;
    }
  }
}
</style>
