<template>
  <div>
    <hr />
    <h3>Composition API vue3</h3>
    <div>
      <input type="text" v-model="message" />
      <p>{{ message }}</p>
      <button @click="alertMessage(message)">alertMessage 버튼입니다</button>
    </div>
    <div>
      <input type="text" placeholder="name" v-model="myUser.name" />
      <input type="text" placeholder="age" v-model="myUser.age" />
      <button @click="addUser(myUser)">addUser 버튼입니다</button>
      <ul>
        <li>입력될 사용자 : {{ myUser.name }} / {{ myUser.age as number }}</li>
        <li v-for="(myUser, index) in myUserList" :key="index">
          {{ myUser.name }} / {{ myUser.age }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { ref, reactive } from "vue";
export default {
  name: "CompositionApi",
  setup() {
    // logic1 group
    const message = ref("Hello Vue 3");
    const alertMessage = (msg: string | null) => {
      alert(msg);
    };

    // logic2 group
    interface User {
      name: string;
      age: number;
      ispeople?: boolean;
    }

    let myUser = reactive<User>({
      name: "",
      age: 0,
      ispeople: true,
    });
    const myUserList = reactive<User[]>([]);

    const addUser = (myUser: User) => {
      myUserList.push({ ...myUser });
      myUser = {} as User;
    };

    return {
      message,
      alertMessage,
      myUser,
      myUserList,
      addUser,
    };
  },
};
</script>

<style lang="scss" scoped></style>
