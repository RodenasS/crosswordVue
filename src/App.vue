<template>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&display=swap" rel="stylesheet">
  <body>

  <header >
    <h1> Kryžiažodis </h1>
  </header>
  <div id="papildomas">
    <table class="puzzletable" id="puzzletable"></table>
    <table id="questions">
      <tr>
        <td><strong>Horizontalus klausimai:</strong></td><td><strong>Vertikalus klausimai:</strong></td>
      </tr>
      <tr>
        <td>1. Objektiskai orientuota skriptu programavimo kalba</td><td>2. Ford modelis dalyvaves 1991-1997 ralyje</td>
      </tr>
      <tr>
        <td>3. Vienas is populiariausiu italu automobiliu gamintojas</td><td>4. Viena is populiariausiu italijos lenktyniniu trasu</td>
      </tr>
      <tr>
        <td>5. 1988 C grupes toyota lenktyninio automobilio modelis</td><td>6. Variklio agregatas priverstinai ipuciantis ora i varikli</td>
      </tr>
      <tr>
        <td>7. Senos kartos elektrinis variklio ipurskimas</td><td>8. Tarptautinis vidaus degimo variklio pavadinimas</td>
      </tr>
      <tr>
        <td>9. Maziausias ford modelis</td><td>10. Koks skystis reikalingas palaikant optimalia automobilio darbine temperatura</td>
      </tr>
    </table>
    <EngineComponent></EngineComponent>
  </div>
  </body>
</template>

<script>
import EngineComponent from './components/Engine-Component.vue'
export default {
  name: 'App',
  components: {
    EngineComponent,
  },
}
</script>

<style lang="scss">
@import "./styles/styles.scss";
</style>
