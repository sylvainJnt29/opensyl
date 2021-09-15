<template>
  <div id="mainContainer">
    <!-- <div id="navbar" sticky class="navbar" :class="{'navbar--hidden': !showNavbar}">
        <ul>
          <li>téléphone</li>
          <li>connexion</li>
          <li>===</li>
        </ul>
    </div>      -->
    <div id="container1">
        
      <!-- intro  -->
      <div id="leftContainer1">
        <h2>OpenSyl</h2>
        <p>Le junior sur mesure responsable et accessible</p>
        <p>Bienvenue à bord !</p>
      </div>
      <div id="rightContainer1">
        <h2>Envie de me recruter ?</h2>
        <a href="https://sylvain-janot.fr" target="blank">Me contacter gratuitement</a>
      </div>
    </div>
    <div id="container2">
      <!-- comment ça marche -->
      <h2>Pourquoi recruter Sylvain en tant que dev junior ?</h2>
      <div id="cards">
        <div class="card">
          <img src="../assets/souple.svg" alt="">
          <h3>Souple</h3>
          <p>Sait se rendre disponible pour les autres</p>
        </div>
        <div class="card">
          <img src="../assets/rapide.svg" alt="">
          <h3>Rapide</h3>
          <p>Possède une bonne capacité d'apprentissage</p>
        </div>
        <div class="card">
          <img src="../assets/responsable.svg" alt="">
          <h3>Responsable</h3>
          <p>Sait rester professionnel en toute circonstance</p>
        </div>
        <div class="card">
          <img src="../assets/accessible.svg" alt="">
          <h3>Accessible</h3>
          <p>Ne demande qu'a être adopté :)</p>
        </div>
      </div>
      
      <button><a href="https://sylvain-janot.fr" target="blank">En savoir plus</a></button>
      <h2>Ils (ne) parlent (pas encore) de moi</h2>
        <div id="mepLogos">    
          <img src="../assets/1.png" alt="">
          <img src="../assets/2.png" alt="">
          <img src="../assets/3.png" alt="">
          <img src="../assets/4.png" alt="">
          <img src="../assets/5.png" alt="">
          <img src="../assets/6.png" alt="">
        </div>
    </div>    
    <div id="container3">
      <!-- votre tempes est précieux + quelques avions -->
      <h2>Comment ça marche ?</h2>
      <p>Découvrez comment me rencontrer !</p>
      <ul>
        <li>1 Contactez moi</li>
        <li>2 Echangeons</li>
        <li>3 Embarquons ensemble</li>
      </ul>
    </div>    
    <div id="container4">
      <!-- témoignage = lm + actualité = projets -->
      <h2>"Témoignage"</h2>
      <p> " Embarquer avec vous dans cette aventure sera une joie immense pour moi! J'ai hâte de monter en compétences
        en travaillant avec des professionnels et pouvoir m'investir à fond et prouver ce que je vaut à l'entreprise qui 
        voudra bien m'aider à faire ce premier saut dans le monde profesionnel. "<br><br>
        <b>Sylvain Janot</b><br>
        <i>Dev Junior</i>
      </p>
      <div id="projectsCards">
        <div class="projetCard">
          <img src="../assets/ecole1.png" alt="">
          <h3>Ecole Roger Bazille</h3>
          <p>Projet de fin de formation Développeur Web</p>
        </div>
        <div class="projetCard">
          <img src="../assets/logo_final_reduction.png" alt="">
          <h3>RadioCLub</h3>
          <p>Refonte d'un site de radio amateurs (Symfony)</p>
        </div>        
        <div class="projetCard">
          <img src="../assets/site1.png" alt="">
          <h3>Mon premier site perso</h3>
          <p>Site perso en PHP, architecture MVC</p>
        </div>
      </div>
      <button><a href="https://github.com/sylvainJnt29" target="blank">Lien Github</a></button>
    </div>
    <footer>
      <ul>
        <div id="mepFooterGauche">
          <li><a href="mailto:sylvain.jnt@gmail.com" target="_blank">Contact eMail</a></li>
          <li><a href="tel:+0683928542">06 83 95 85 42</a></li>
          <li><a href="https://sylvain-janot.fr" target="blank">Mon site perso</a></li>
        </div>
        <div id="mepFooterDroit">
          <li><a href="https://github.com/sylvainJnt29" target="_blank">Lien Github</a></li>
          <li><a href="https://www.linkedin.com/in/sylvain-janot-8240b416b/" target="_blank">Lien Linkedin</a></li>
          <li><a :href="`${publicPath}cv_sylvain_janot_dev_web.pdf`" target="_blank">Voir mon CV</a></li>
        </div>
      </ul>
      <p>Site fictif et éphémère inspiré par (et pour) OpenFly.fr - En aucun cas destiné à être malveillant</p>
    </footer>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      showNavbar: true,
      lastScrollPosition: 0,
      publicPath: process.env.BASE_URL
    }
  },
  mounted: function() {
    window.addEventListener('scroll', this.onScroll);
    this.startAnimations();
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.onScroll)
  },
  methods:{
    onScroll(){
      // Récupérer la position du scroll actuelle
      const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop
      // A cause du scroll sur mobile, on ne doit pas continuer si c'est moins que zéro
      if ( currentScrollPosition < 0 ){
        return
      }
      if(Math.abs(currentScrollPosition - this.lastScrollPosition) < 60){
        return
      }
      //On determine si on montre ou cache la navbar
      this.showNavbar = currentScrollPosition < this.lastScrollPosition
      //On set la position actuelle comme étant la dernière
      this.lastScrollPosition = currentScrollPosition
    },
  props: {
    msg: String
  }
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

#mainContainer{
  background-size: cover;
  /* background: url("../assets/background.jpg")no-repeat;   */
  background-image: linear-gradient(180deg,#273b64 0,rgba(0,160,127,.5) 70%); 
  position: relative;
  background-attachment: fixed;
}
#navbar ul{
  display: flex;
  flex-direction: row;
  margin: auto;
}
#container1{
  font-size: 200%;
  display: flex;
  color:white;
  margin: 0% 5% 5% 5%;
  padding-top: 5%;
  justify-content: space-around;
}
#leftContainer1{
  margin: 2%;
}
#rightContainer1{
  margin: 4%;
  padding: 1%;
  background-color: white;
  border-radius:  30px;
}
#rightContainer1 h2{
  color: rgb(36, 189, 125);
}
#rightContainer1 a{
  color:white;
  text-decoration: none;
  background-color: rgb(36, 189, 125);
  border-radius:  5px;
  padding-left: 10%;
  padding-right: 10%;
}
#container2{
  font-size: 200%;
  background-color: white;
  padding-top: 5%;
  padding-left: 10%;
  padding-right: 10%;
}
#cards{
  display: flex;
  font-size: 90%;
}
#container2 button,#container4 button{
  background-color: rgb(9, 43, 98);
  padding: 1% 3%;
  border-radius:  10px;
  font-size: 75%;
  margin-bottom: 2%;
  margin-top: 2%;
  color: white;
}
#container2 a,#container4 a{
  color: white;
  text-decoration: none;
}
#container2 img{
  width: 150px;
  height: 150px;
}
#mepLogos{
  display: flex;
  justify-content: space-around;
  padding-bottom: 5%;
}
#container3{
  padding: 8%;
  font-size: 200%;
  text-align: center;
  color:white;
}
#container4{
  font-size: 200%; 
  background-color: white;
  padding: 5%;
}
#projectsCards{
  flex-basis: 30%;
  display: flex;
  padding:5%
}
.projetCard{
  /* padding-top: 5%;
  box-shadow: 1px solid black;
  border: 1px solid black; */
    -webkit-box-orient: vertical;
    -webkit-box-direction: normal;
    -ms-flex-direction: column;
    flex-direction: column;
    -ms-flex-preferred-size: 30%;
    flex-basis: 30%;
    background-color: #fff;
    border-radius: 10px;
    -webkit-box-shadow: 0 2px 4px -1px rgba(0,0,0,.05),0 4px 5px 0 rgba(0,0,0,.05),0 1px 10px 0 rgba(0,0,0,.12);
    box-shadow: 0 2px 4px -1px rgba(0,0,0,.05),0 4px 5px 0 rgba(0,0,0,.05),0 1px 10px 0 rgba(0,0,0,.12);
    color: #273b64;
    width: 100%;
    padding: 15px;
}
.projetCard img{
  width: 150px;
  height: 150px;
}
footer{
  width: 100%;
  padding: 2%;
  font-size: 200%;
  color:white;
  background-image: -webkit-gradient(linear,left top,left bottom,from(#273b64),color-stop(70%,rgba(0,160,127,.5)));
  background-image: linear-gradient(180deg,#273b64 0,rgba(0,160,127,.5) 70%);
}
footer ul{
  display: flex;
  justify-content:space-around;
}
footer a{
  text-decoration: none;
  color: white;
}
ul{
  list-style-type: none;
  padding: 0;
}
li{
  margin: 0 10px;
}
.progress-bar-container--container {
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
}
#navbar{
  font-size: 2.4em;
  color:white;
}
.navbar{
  height: 60px;
  width: 100%;
  background: rgba(128, 128, 128, 0.342);
  position: fixed;
  box-shadow: 0 2px 15px rgba(71, 120, 120, 0.5);
  transform: translate3d(0, 0, 0);
  transition: 0.1s all ease-out;
}
.navbar.navbar--hidden{
  box-shadow: none;
  transform: translate3d(0, -100%, 0);
}

/* Responsive */ 
@media (max-width: 991px){

#container1,#container2,#container3,#container4,#cards,#projectsCards{
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
#mepLogos{
  margin-top: 6%;
}
#mepLogos img{
  width: 30%;
  height: 30%;
}
#container2 h2,#projectsCards{
  font-size: 80%;
}
.projetCard{
  width: 90%;
}

}
</style>
