<template>
  <div>
    <div class="breadcrumbs mt-6 mb-2">
      <ul class="d-flex">
        <li
          v-for="(item, i) in breadcrumbs" 
          :key="item.title + i" 
          class="breadcrumbs__item">
          <a href="#" class="breadcrumbs__item_link">
            {{ item.title }}
          </a>
          <span class="slash">{{ item.slash }}</span>
        </li>
      </ul>
    </div>

    <ul class="d-flex">
      <li 
        v-for="(item, i) in menu" 
        :key="item.title + i" 
        class="menu__item">
        <a href="#">
          {{ item.title }}
        </a>
        <span class="slash slash-menu">{{ item.slash }}</span>
      </li>
    </ul>

    <div class="inform mt-10">
      <ul class="d-flex">
        <li class="inform__item">
          <strong>Сегодня</strong> <p class="data">14.12.2023</p>
        </li>
        <li
          v-for="(inf, i) in information"
          :key="inf + i"
          class="inform__item"
        >
          <v-img :src="require(`@/assets/${inf.icon}`)" class="icon"></v-img>
          <span class="number">{{ inf.number }}</span>
          <span class="vert-line"></span>
        </li>
        <li class="inform__item">
          <p>VIN-код:</p>
          <span class="number">17</span>
        </li>
      </ul>
    </div>

    <div class="car">
      <v-row>
        <v-col cols="8">
          <v-carousel v-model="model">
            <v-carousel-item
              v-for="(img, i) in images"
              :key="img + i"
              :value="i"
            >
              <v-img :src="require(`@/assets/${img.img}`)"></v-img>
              <div class="d-flex number-image">
                  {{ i + 1 }} из {{ images.length }}
                </div>
              <div class="logo">
                <v-img src="@/assets/verified.png"></v-img>
              </div>
              <div class="youtube-link">
                <a href="#"><v-img src="@/assets/youtube-red.png"></v-img></a>
              </div>
            </v-carousel-item>
          </v-carousel>
        </v-col>
        <v-col cols="4">
          <div class="car-block">
            <div class="name d-flex justify-space-between align-center">
              <h2 class="title">Ford Edge 2016</h2>
              <div class="icons d-flex">
                <v-img src="@/assets/icons state.png" class="icon"></v-img>
                <v-img src="@/assets/bookmark.png" class="icon"></v-img>
              </div>
            </div>

            <div class="cod-block d-flex justify-space-between mt-4 pb-2">
              <v-text class="cod-product">Код товара: 40845</v-text>
              <v-text>Львов</v-text>
            </div>

            <div class="price-text-block d-flex mt-2 mb-6">
              <v-text><strong>Цена</strong></v-text>
              <v-text class="text">ГРН</v-text>
              <v-text class="text active-text-price">USD</v-text>
              <v-text class="text">EUR</v-text>
              <v-text class="text">CRYPTO</v-text>
            </div>

            <div class="price">
              <h2>62 490 USD</h2>
            </div>

            <div class="credit mb-3">
              <v-text>от 511$/мес</v-text>
            </div>

            <div class="text-iformation mb-3 pb-3">
              <v-text>
                *Ежемесячный платеж носит информационный характер и может меняться на момент получения детального расчета<br/>
                *Возможна оплата криптовалютой
              </v-text>
            </div>

            <div class="buttons">
              <v-btn variant="outlined">
                Все авто
              </v-btn>
              <v-btn variant="outlined">
                Официальное авто
              </v-btn>
              <v-btn variant="outlined">
                Авто с Европы
              </v-btn>
            </div>

            <div class="public-data mb-3 pb-3">
              <v-text>Опубликовано 14.12.2023</v-text>
            </div>

            <div class="btn-show-phone">
              <v-btn>
                <img src="../assets/phone.svg" class="btn-phone-icon" alt="phone" />
                Показать телефон
              </v-btn>
            </div>
          </div>
        </v-col>
      </v-row>
      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      breadcrumbs: [
        {
          title: 'Главная',
          href: '#',
          slash: '/'
        },
        {
          title: 'Купить',
          href: '#',
          slash: '/'
        },
        {
          title: 'Автомобили Ford',
          href: '#',
          slash: '/'
        },
        {
          title: 'Ford Edge 2016 - Код товара: 40845',
          href: '#',
        }
      ],
      menu: [
        {
          title: 'Все про авто',
          href: '#',
          slash: '|'
        },
        {
          title: 'Характеристики',
          href: '#',
          slash: '|'
        },
        {
          title: 'Дополнительно',
          href: '#',
          slash: '|'
        },
        {
          title: 'Салон',
          href: '#',
          slash: '|'
        },
        {
          title: 'Оптика',
          href: '#',
          slash: '|'
        },
        {
          title: 'Кузов',
          href: '#',
          slash: '|'
        },
        {
          title: 'Система помощи при парковке',
          href: '#',
          slash: '|'
        },
        {
          title: 'Безопасность',
          href: '#',
          slash: '|'
        },
        {
          title: 'Мультимедиа',
          href: '#',
          slash: '|'
        },
        {
          title: 'Отзывы',
          href: '#'
        }
      ],
      information: [
        {
          icon: 'user.svg',
          number: 20
        },
        {
          icon: 'bookmark.png',
          number: 50
        },
        {
          icon: 'phone.png',
          number: 17
        }
      ],
      images: [
        {
          img: 'main photo.jpg'
        },
        {
          img: 'img 2.jpg'
        },
        {
          img: 'img 3.jpg'
        }
      ],
      model: 0,
    }
  },
}
</script>

<style scoped lang="scss">
.slash {
  padding-right: 3px;
}
.slash-menu {
  color: grey;
}
.inform {
  &__item {
    display: flex;
    .data {
      margin: 0 15px;
      color: grey;
    }
    .icon {
      width: 25px;
      height: 25px;
    }
    .number {
      color: rgba(231, 58, 63, 1);
    }
    .vert-line {
      display: block;
      width: 1px;
      height: 25px;
      margin: 0 5px;
      background-color: grey;
    }
  }
}
.car {
  .number-image,
  .youtube-link {
    position: absolute;
    bottom: 0;
    border-radius: 5px;
    background-color: black;
    padding: 3px 5px;
  }
  .number-image {
    color: #fff;
    right: 50px;
  }
  .youtube-link {
    right: 0;
    padding: 6px 15px 7px 5px;
  }
  .logo {
    position: absolute;
    bottom: 0;
  }
  .car-block {
    .name {
      .title {
        text-transform: uppercase;
      }
      .icon {
        width: 20px;
        height: 20px;
      }
    }
  }
  .cod-block {
    border-bottom: 1px solid grey;
    .cod-product {
      color: grey;
    }
  }
  .price-text-block {
    .text {
      margin-left: 10px;
    }
    .active-text-price {
      color: rgba(231, 58, 63, 1);
      text-decoration: underline;
    }
  }
  .text-iformation {
    color: grey;
    font-size: 12px;
    border-bottom: 1px solid grey;
  }
  .buttons {
    .theme--light.v-btn.v-btn--has-bg {
      background-color: transparent;
      border: 1px solid rgba(231, 58, 63, 1);
      margin: 0 20px 20px 0;
    }
    :deep(.v-btn__content) {
      text-transform: math-auto;
    }
  }
  .public-data {
    color: grey;
    border-bottom: 1px solid grey;
  }
  .btn-show-phone {
    .theme--light.v-btn.v-btn--has-bg {
      width: 100%;
      text-transform: math-auto;
      background-color: rgba(231, 58, 63, 1);
      color: #fff;
      .btn-phone-icon {
        margin-right: 15px;
      }
    }
  }
}
</style>