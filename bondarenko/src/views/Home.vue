<template>
  <div class="grid-container">
    <div id="nav" class="nav"></div>
    <div class="h1">
      <h1>Галереи автомобилей</h1>
      <hr />
    </div>
    <div class="main">
      Если вы хотите оценить дизайн популярных брендов машин или сравнить внешний вид новинок с предыдущими моделями, используйте раздел фото автомобилей на портале VERcity. Здесь представлены все марки и модели автомобилей, начиная с 1884 года. Качественные картинки авто дадут вам полное представление, как изменялась мода в конкретный период времени.
      В общий список вошли современные производители машин и компании, давно прекратившие выпуск транспортных средств. Чтобы оценить модели автомобилей со всего мира на фото, вам не нужна регистрация на портале. Заходите в удобное время и узнавайте отличительные черты дизайна американских, европейских, японских, российских и других марок.
    </div>
    <div class="footer">
      <h2>ФИО: Бондаренко Илья Андреевич</h2>
      <hr />
      <h2>Группа: 181-362</h2>
      <hr />
      <h2>Дата выполнения задания: 17.06.2020</h2>
      <hr />
      <div>
        <p>
          Cсылки:
          <a href="http://htmlbook.ru/css/">http://htmlbook.ru/css/</a>
        </p>
      </div>
      <a href></a>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {}
};
</script>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=MuseoModerno&display=swap");
.grid-container {
  background-color: #f1a43e;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-template-rows: 1fr 1fr 1fr 1fr 1fr 1fr 1fr;
  gap: 1px 1px;
  grid-template-areas:
    "nav nav nav"
    "h1 h1 h1"
    "main main main"
    "main main main"
    "footer footer footer"
    "footer footer footer"
    "footer footer footer";
}
.nav {
  grid-area: nav;
}
.main {
  grid-area: main;
  text-align: justify;
  color: rgb(100, 76, 44);
  font-family: "MuseoModerno", cursive;
  font-size: 130%;
}
.footer {
  grid-area: footer;
  text-align: justify;
  font-size: 70%;
}
.h1 {
  grid-area: h1;

  color: rgb(252, 252, 252);
}
p {
  font-size: 160%;
}

@media screen and (max-width: 992px) {
  .grid-container {
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 0.2fr 0.5fr 1fr 1fr 1fr 1fr 1fr;
    gap: 1px 1px;
    grid-template-areas:
      "nav nav"
      "h1 h1"
      "main main"
      "main main"
      "footer footer"
      "footer footer"
      "footer footer";
  }
  .main {
    padding: 10%;
  }
  .footer {
    padding: 3%;
  }
}
@media screen and (max-width: 576px) {
  .grid-container {
    grid-template-columns: 1fr;
    grid-template-rows: 0.2fr 0.5fr 1fr 1fr 1fr;
    gap: 1px 1px;
    grid-template-areas:
      "nav"
      "h1"
      "main"
      "main"
      "footer";
  }
  .main {
    padding: 10%;
    font-size: 80%;
  }
  .footer {
    padding: 3%;
  }
}
</style>
