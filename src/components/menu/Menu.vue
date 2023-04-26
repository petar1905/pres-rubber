<script>
import Option from "./Option.vue"
import Gallery from "../gallery/Gallery.vue"
import Photo from "../gallery/Photo.vue"
import Quiz from "../quiz/Quiz.vue"
export default {components: {Option, Gallery, Photo, Quiz}}
</script>

<template>
  <div>
    <Option Title="Естествен<br>каучук" Subtitle="Какво представлява<br>естествения каучук?<br><br><b>ДА РАЗБЕРЕМ!<b>" 
    Background="linear-gradient(0deg, rgba(115,56,200,1),rgba(0,212,255,1))"
    Thumbnail="photos/rubber.webp">
     <h1>1.Естествен каучук</h1>
      <Gallery>
        <Photo Content="photos/Collecting-Natural-Rubber.jpg" Alt="Добив на латекс. Латексът е съставен от 40% каучук."></Photo>
        <Photo Content="photos/Natural-Rubber-Formula.png" Alt="Формула на каучука. Каучукът е също известен като полиизопрен."></Photo>
      </Gallery>
      <h3>a) Недостатъци</h3>
      <Gallery>
        <Photo Content="photos/Cold-Rubber.jpg" Alt="При ниска температура каучукът става крехък и чуплив."></Photo>
        <Photo Content="photos/Worn-Out-Keys.jpg" Alt="При висока употреба или висока темп. каучукът става лепкав и износен."></Photo>
      </Gallery>
      <h3>б) Вулканизация</h3>
      <Gallery style="margin-left: -125px">
        <Photo Content="photos/Vulcanization.jpg" Alt="Вулканизацията е процес, който подобрява надеждността на каучука."></Photo>
        <Photo Width="550px" Content="photos/Vulcanization2.webp" Alt="Реакцията се осъществява чрез нагряване на каучука в присъствие на сяра."></Photo>
      </Gallery><br>
      <Gallery>
        <Photo Alt="Сервиз/Вулканизатор в гр.Червен Бряг" Content="photos/Vulcanizator.png"></Photo>
      </Gallery>
      <h3>Вулканизация - Видео пример</h3>
      <Gallery>
        <video controls src="/videos/Tire-Vulcanizing.mp4" style="width:360px; height:640px; border-radius: 20px;"></video>
      </Gallery>
      <h3>в) Факти</h3>
      <Gallery style="margin-bottom: 150px">
        <Photo Content="photos/KP-Holding-Tire.png" Alt="Зим. гуми имат по-голямо съдърж. на каучук, което ги поддържа в студ. време."></Photo>
        <Photo Content="photos/Burnout.gif" Alt="Бърнаут с продължение 90 сек. може да разруши гумите на кола."></Photo>
      </Gallery>
    </Option>
    
    <Option Title="Изкуствен<br>каучук"
    Subtitle="Изкуствено каучук?<br>Какво е това?<br>По-добър ли е от естетсвения?<br><br> <b>Тепърва ви предстои да научите!<b>"
    Background="linear-gradient(147deg, #e4d545, #3b8751)"
    Thumbnail="photos/mechanic.jpg">
      <h1>2.Синтетичен каучук</h1>
      <Gallery>
        <Photo Content="/photos/Synthetic-Rubber-Factory.jpg" Alt="Син. каучук има по-ниска надеждност от ест., но по-лесно се произвежда."></Photo>
        <Photo Content="/photos/Ice-Cream-Mold.jpg" Alt="Синтетичният каучук се среща навсякъде в домакинството."></Photo>
      </Gallery>
      <h3>а) Видове синтетичен каучук</h3>
      <Gallery style="margin-bottom: 150px">
        <Photo Content="/photos/Nitrile-Glove.jpg" Alt="Нитрилов каучук. От него се създават ръкавици за еднократна употреба."></Photo>
        <Photo Content="/photos/Garden-Hose.webp" Alt="Полиизопренов каучук. От него се създават маркучи и гуми."></Photo>
        <Photo Content="/photos/Wetsuit.webp" Alt="Неопренът е създаден чрез синтез на хлоропренов каучук."></Photo>
      </Gallery>
    </Option>

    <Option Title="Екологични<br>проблеми" 
    Subtitle="Как каучуковите изделия замърсяват природата?<br><br>Как отговаря човечеството на подобно действие?" 
    Background="linear-gradient(201deg, #462711, #c43a45)"
    Thumbnail="photos/Rainbow-Tires.webp">
      <h1>3. Екологични проблеми</h1>
      <Gallery>
        <Photo Content="/photos/Man-Front-Tires.png" Alt="Между 1 и 1.8 милярда гуми се изхвърлят всяка година."></Photo>
      </Gallery>
      <br>
      <Gallery>
        <video controls src="/videos/Recycling.mp4" style="width:360px; height:640px; border-radius: 20px;"></video>
        <video controls src="/videos/Recycling1.mp4" style="width:360px; height:640px; border-radius: 20px;"></video>
      </Gallery>
      <br>
      <Gallery>
        <video controls src="/videos/Recycling2.mp4" style="width:720; height:720px; border-radius: 20px;"></video>
      </Gallery>
    </Option>


    <Option id="Quiz" Title="Стани Химик!" Subtitle="Забавна и интерактивна<br>образователна игра<br>съдържаща въпроси за<br>материала от урока!" 
    Thumbnail="photos/quiz.webp"
    Background="radial-gradient(circle, hsla(310, 51%, 51%, 1) 0%, hsla(277, 78%, 47%, 1) 100%)">
      <Quiz></Quiz>
    </Option>
  </div>
</template>

<style scoped>
div {
  display: flex;
  justify-content: center;
  column-gap: 30px;
  align-content: center;
}

.Option:link, .Option:visited, .Option:active {
  text-decoration: none;
}

</style>