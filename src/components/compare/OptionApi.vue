<template>
  <div>
    <hr />
    <h3>Option API vue2</h3>
    <div>
      <input type="text" v-model="message" />
      <p>{{ message }}</p>
      <button @click="alertMessage(message)">alertMessage 버튼입니다</button>
    </div>
    <div>
      <input type="text" placeholder="name" v-model="user.name" />
      <input type="text" placeholder="age" v-model="user.age" />
      <button @click="addUser(user)">addUser 버튼입니다</button>
      <ul>
        <li>입력될 사용자 : {{ user.name }} / {{ user.age as number }}</li>
        <li v-for="(user, index) in userList" :key="index">
          {{ user.name }} / {{ user.age }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
interface User {
  name: string;
  age: number;
  ispeople?: boolean;
}
export default {
  name: "OptionApi",
  data() {
    return {
      // logic1 data
      message: "Hello Vue 2",
      // logic2 data
      userList: [] as User[],
      user: {
        name: "",
        age: 0,
      } as User,
    };
  },
  methods: {
    // logic1 methods
    alertMessage(msg = this.message) {
      alert(msg);
    },
    // logic2 methods
    addUser(user: User) {
      this.userList.push({ ...user });
    },
  },
};
</script>

<style lang="scss" scoped></style>
