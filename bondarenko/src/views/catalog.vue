<template>
  <div class="about">
    <h1>Каталог</h1>
    <img src="../assets/images/car.jpg" alt />
    <!-- <nav>
      <ul>
        <li>
          <a href></a>Astra
        </li>
        <li>
          <a href></a>Audi
        </li>
        <li>
          <a href></a>BAW
        </li>
      </ul>
    </nav>-->
    <label>Название</label>
    <input type="text" v-model="name" />
    <label>Цена</label>
    <input type="text" v-model="rub" />
    <button v-if="isEdit" @click="saveEdit(id)">Сохранить</button>
    <button v-if="isEdit" @click="EditModOff">Отмена</button>
    <button v-if="isEdit" @click="save">Сохранить</button>
    <div v-for="(note, index) in posts" :key="note.id">
      <div>{{note.name}}</div>
      <div>{{note.rub}}</div>
      <div>
        <button @click="del(note.id)">Удалить</button>
      </div>
      <div>
        <button @click="EditModOn(index)">Редактировать</button>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "App",
  data: function() {
    return {
      posts: [],
      name: "",
      rub: "",
      id: 0,
      isEdit: false
    };
  },
  components: {},
  methods: {
    async up() {
      try {
        let res = await this.$http.get("http://localhost:3000/posts");
        this.posts = await res.json();
        this.errMsg = "";
      } catch (e) {
        console.error(e);
      }
    },
    async save() {
      let note = {
        name: this.name,
        rub: this.rub
      };
      try {
        await this.$http.post("http://localhost:3000/posts", note);
        this.up();
      } catch (e) {
        console.error(e);
      }
    },
    async del(id) {
      try {
        await this.$http.delete("http://localhost:3000/posts" + id);
        this.up();
      } catch (e) {
        console.error(e);
      }
    },
    EditModOn(index) {
      this.name = this.posts[index].name;
      this.rub = this.posts[index].rub;
      this.id = this.posts[index].id;
      this.isEdit = true;
    },
    EditModOff() {
      this.name = "";
      this.rub = "";
      this.id = 0;
      this.isEdit = false;
    },
    async saveEdit(id) {
      let note = {
        name: this.name,
        rub: this.rub,
        id: this.id
      };
      try {
        await this.$http.post("http://localhost:3000/posts" + id, note);
        this.up();
      } catch (e) {
        console.error(e);
      }
    }
  },
  created() {
    this.up();
  }
};
</script>

<style scoped>
</style>
