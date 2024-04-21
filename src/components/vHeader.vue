<template>
  <header class="header">
    <v-row class="v-row align-center">

      <v-col class="header__icons d-flex" cols="9">
        <a
          v-for="(item, i) in socialsIcons"
          :key="item.title + i"
          :href="item.href"
          class="mr-3"
        >
        <v-img
          :src="require(`../assets/${item.icon}`)"
          :alt="item.title"
          :title="item.title"
          class="my-3"
          contain
          height="20"
        />
        </a>
      </v-col>

      <v-col class="header__phone d-flex" cols="3">
        <v-btn rounded width="160">
          <v-avatar color="green" size="30" class="mr-2">
            <img src="../assets/phone.svg" class="btn-phone-icon" alt="phone" />
          </v-avatar>
          067-322-16-63
        </v-btn>

        <div class="languages d-flex align-center">
          <a href="#">RU</a>
          <span></span>
          <a href="#" class="ua d-flex align-center">
            <img src="../assets/ukraine.svg" alt="ukraine" class="mr-1" />
            UA
          </a>
        </div>

        <div class="bookmark ml-7">
          <v-img src="../assets/bookmark.svg"></v-img>
        </div>
      </v-col>
    </v-row>
   
  </header>
</template>

<script>
export default {
  data() {
    return {
      socialsIcons: [
        {
          title: 'instagram',
          icon: 'inst.svg',
          href: '#'
        },
        {
          title: 'telegram',
          icon: 'telegram.svg',
          href: '#'
        },
        {
          title: 'facebook',
          icon: 'facebook.svg',
          href: '#'
        },
        {
          title: 'viber',
          icon: 'viber.svg',
          href: '#'
        },
        {
          title: 'youtube',
          icon: 'youtube.svg',
          href: '#'
        },
        {
          title: 'tiktok',
          icon: 'tiktok.svg',
          href: '#'
        }
      ]
    }
  }
}
</script>

<style scoped lang="scss">
  .btn-phone-icon {
    width: 20px;
  }
  .languages {
    margin-left: 20px;
    a {
      font-size: 16px;
      color: #000;
    }
    span {
      display: inline-block;
      margin: 0 10px;
      background: grey;
      height: 40px;
      width: 1px;
    }
    .ua {
      color: grey;
    }
  }
</style>