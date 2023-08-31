

<template>

    <div class="main-container">

         <div class="flip-card-container">
            <div class="input-container">
                <input v-model="favoriteCharacter" placeholder="Enter your favorite character" />
                <button @click="generateCharacter" class="btn-generate">Generate</button>
            </div>
            <div class="flip-card" :class="{ flipped: isFlipped }" @click="flipCard">
                <div class="card front">
                    <p>Say Hii to your fav Doraemon Character</p>
                </div>
                <div class="card back">
                    <img :src="characterImage" alt="Enter Valid Character" />
                    <p class="back-text"><span class="hii-text">Hii!</span> <br> I am <span class="character-name">{{ favoriteCharacter }}</span></p>

                </div>
            </div>
        </div>


    </div>
   
</template>

<script>
export default {
    data() {
        return {
            favoriteCharacter: "",
            characterImage: "",
            isFlipped: false,
            characterImages: {
                Doraemon: require('@/assets/Doraemon.jpg'), 
                Dekisugi: require('@/assets/Dekisugi.jpg'),
                Dorami: require('@/assets/Dorami.jpg'),
                Gian: require('@/assets/Gian.jpg'),
                Jaiko: require('@/assets/Jaiko.jpg'),
                MiniDoras: require('@/assets/MiniDoras.jpg'),
                Nobita: require('@/assets/Nobita.jpg'),
                Shizuka: require('@/assets/Shizuka.jpg'),
                Suneo: require('@/assets/Suneo.jpg'),
                Teacher: require('@/assets/Teacher.jpg'),
                
            },
        };
    },
    methods: {
        generateCharacter() {
            if (this.characterImages[this.favoriteCharacter]) {
                this.characterImage = this.characterImages[this.favoriteCharacter];
                this.errorMessage = '';
            } else {
                // Handle case when character image is not available
                // You can show an error message or something similar
                this.errorMessage = 'Enter a valid character';
            }
        },
        flipCard() {
            this.isFlipped = !this.isFlipped;
        },
    },
};
</script>

<style scoped>

.main-container{
    background-color: #070921;
    color: white;
    font-family: 'Poppins', sans-serif;
    margin: 0;
    padding: 0;
    overflow-x: hidden;
  overflow-y:hidden ;
}
 .flip-card-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
}

.input-container {
    margin-bottom: 20px;
    padding: 1rem;
}
input{
    padding: 1rem;
    margin-right: 1rem;
    border-radius: 10px;
}
.btn-generate{
    padding: 0.5rem;
    font-size: 1rem;
    font-weight: bolder;
    border-radius: 1.1rem;
    cursor: pointer;
}
.btn-generate:hover{
    background-color: plum;
    transition: all 0.5s;
    color: rgb(231, 231, 231);
  background: rgb(170, 0, 255);
  filter: drop-shadow(3px 3px 7px #d510ef);
}
.flip-card {
    width: 250px;
    height: 400px;
    perspective: 1000px;
    border-radius: 40px;
    /* background: linear-gradient(to right, #cc2b5e, #753a88);  */
    cursor: pointer;
}

.card {
    width: 100%;
    height: 100%;
    position: absolute;
    backface-visibility: hidden;
    transition: transform 0.5s;
    display: flex;
    justify-content: center;
    align-items: center;
    border: 1px solid #ccc;
   
}

.back {
    transform: rotateY(180deg);
    border-radius: 30px;
    background: linear-gradient(to right, #cc2b5e, #753a88); 
  /* filter: drop-shadow(3px 3px 7px #d510ef); */
  box-shadow: rgba(255, 48, 203, 0.8) 0px 22px 70px 4px;
  display: flex;
  flex-direction: column;
  gap: 4px;
  font-size: 2rem;


}
.hii-text{
    margin-right: 2rem;
}

.back-text{
    margin: 5px;
    padding: 11px;
}
.character-name{
    font-size: 2.5rem;
    font-weight: 500;
}
.front{
    transform: rotateY(0deg);
     border-radius: 30px;
     background: linear-gradient(to right, #cc2b5e, #753a88); 
    box-shadow: rgba(255, 48, 203, 0.4) 0px 30px 90px;
}

.front p{
    margin: 3rem;
    font-size: 2rem;
}
.flipped .front{
    transform: rotateY(180deg);
}

.flipped .back {
    transform: rotateY(0deg);
}

img {
    max-width: 100%;
    max-height: 100%;
    height: 11rem;
    width: 11rem;
    margin-top: 1rem;
    border-radius: 2rem;
} 




</style>
