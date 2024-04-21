<template>
  <nav class="navigation d-flex justify-space-between align-center mt-8">
    <div class="logo">
      <v-img src="../assets/logo.svg" title="autopark" alt="autopark"></v-img>
    </div>
    <div class="menu d-flex">
      <v-list
        v-for="item in list"
        :key="item.id"
      >
        <v-list-item class="list-item">
          <a href="#">{{ item.title }}</a>
        </v-list-item>
      </v-list>
    </div>
   
    <v-btn class="entrance">
      Войти
    </v-btn>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      list: [
        {
          id: 1, title: 'Купить'
        },
        {
          id: 2, title: 'Продать'
        },
        {
          id: 3, title: 'Услуги'
        },
        {
          id: 4, title: 'Блог'
        },
        {
          id: 5, title: 'Вакансии'
        },
        {
          id: 6, title: 'Контакты'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
.navigation {
  height: 50px;
  box-shadow: 0px 0px 6px 0px rgba(0,0,0,0.6);
  .logo {
    width: 270px;
    height: auto;
    img {
      width: 100%;
      height: 100%;
    }
  }
  .menu {
    .theme--light.v-sheet {
      background: transparent;
    }
    .list-item {
    a {
      color: #000;
    } 
    }
  }
  .entrance {
    width: 200px;
    height: 50px;
    background-color: rgba(231, 58, 63, 1);
    color: #fff;
  }
}
</style>