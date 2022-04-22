<template>
  <div class="users">
    <ul class="users_list">
      <li class="users_item" v-for="user in users" :key="user.id">
        <div class="users_info">
          <div class="users_info--avatar">
            <img class="users_info--avatar" :src="avatar(user.avatar)" :alt="user.avatar">
          </div>
          <div class="users_info--wrapp">
            <p class="users_info--name">{{ user.user_name }} <span class="users_info--age">({{user.user_age}})</span></p>
            <p class="users_info--city">{{ user.city }}</p>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  methods: {
    avatar(content_id) {
      return `http://127.0.0.1:7000/avatar/${content_id}`
    }
  },
  data() {
    return {
      users: [
        {user_name: 'Daniil', avatar: 'stephan.jpeg', city: 'Moscow', id: 1, user_age: 18},
        {user_name: 'Artem', avatar: 'maksim.jpeg', city: 'Krasnodar', id: 12, user_age: 27},
        {user_name: 'Joe', avatar: 'joe.jpeg', city: 'Novosibirsk', id: 15, user_age: 21},
        {user_name: 'Stephan', avatar: 'joe.jpeg', city: 'Sochi', id: 35, user_age: 34},
        {user_name: 'Alina', avatar: 'alina.jpeg', city: 'Saint-Petersburg', id: 54, user_age: 23},
        {user_name: 'Maksim', avatar: 'maksim.jpeg', city: 'Moscow', id: 5, user_age: 19},
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.users {
  width: 960px;
  margin: 0 auto;
  margin-top: 24px;
  &_list {
    display: flex;
    flex-direction: column;
  }
  &_item {
    display: flex;
    align-items: center;
    margin-bottom: 12px;
    background-color: #ebebeb;
    border-radius: 6px;
    box-shadow: 1px 1px 7px #4e4e4e;
    transition: all .6s ease;
    &:hover {
      background-color: rgb(192, 219, 255);
      box-shadow: 5px 5px 14px #4e4e4e;
      transform: translateY(-3px) translateX(-10px);
    }
    &:last-child {
      margin-bottom: 0;
    }
  }
  &_info {
    display: flex;
    align-items: center;
    padding: 8px;
    &--avatar {
      width: 60px;
      height: 60px;
      border-radius: 4px;
      object-fit: cover;
    }
    &--name {
      margin-bottom: 6px;
    }
    // &--age {
      
    // }
    &--wrapp {
      margin-left: 12px;
    }
  }
}
</style>
