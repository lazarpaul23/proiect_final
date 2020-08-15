<template>
    <Layout>
        <header class="header">
            <h1>Rock Paper Scissors Game</h1>
        </header>
        <div class="container">
            <div class="score-container">
                <span class="user">YOU</span>
                <span id="score">{{this.UserPoints}} - {{this.ComPoints}}</span>
                <span class="com">COM</span>
            </div>
            <div class="buttons">
                <button id="paper" class="bn" @click="game('paper')"><i class="far fa-hand-paper"></i></button>
                <button id="rock" class="bn" @click="game('rock')"><i class="far fa-hand-rock"></i></button>
                <button id="scissors" class="bn" @click="game('scissors')"><i class="far fa-hand-scissors"></i></button>
            </div>
            <div id="challenge">
                <div id="you">
                    <div id="YourObject"></div>
                    <div class="who">You</div>
                </div>
                <div id="result"><p id="who">{{this.message}}</p></div>
                <div id="com">
                    <div id="ComObject"></div>
                    <div class="who">Computer</div>
                </div>
            </div>
        </div>
    </Layout>
</template>

<script>
export default {
    metaInfo: {
        title: 'Tic Tac Toe'
    },
    data() {
        let choice = ["paper", "rock", "scissors"];
        return {
            choices: choice,
            ComChoice: choice[Math.floor(Math.random() * 3)],
            UserPoints: 0,
            ComPoints: 0,
            drawer: false,
            winner: false,
            loser: false,
            message: ''
        }
    },
    methods: {
        score(){
            var score_div = document.getElementById("score").innerHTML = UserPoints + " - " + ComPoints;
        },
        convert(word){
            console.log(word)
            if(word === "paper") return '<i class="far fa-hand-paper"></i>';
            if(word === "rock") return '<i class="far fa-hand-rock"></i>';
            return '<i class="far fa-hand-scissors"></i>'
        },
        game(UserChoice){
            this.drawer = false;
            this.winner = false;
            this.loser = false;
            var box = document.getElementById("challenge");
            box.style.display = "inline-flex";
            var userDiv = document.getElementById("YourObject");
            userDiv.innerHTML = this.convert(UserChoice);
            var comDiv = document.getElementById("ComObject");
            comDiv.innerHTML = this.convert(this.ComChoice);
            if(UserChoice === "paper" && this.ComChoice === "rock" || UserChoice === "rock" && this.ComChoice === "scissors" || UserChoice === "scissors" && this.ComChoice === "paper"){
                this.win(UserChoice);
            }
            else if(UserChoice === this.ComChoice){
                this.draw(UserChoice);
            }
            else{
                this.lose(UserChoice);
                console.log('tot pierd?')
            }
            setTimeout(this.continuGame(), 1200);

        },
	    continuGame(){
            let i = Math.floor(Math.random() * 3);
            this.ComChoice = this.choices[i];
        },
        win(bn){
            this.UserPoints++;
            this.winner = true;
            this.message = "You win!"
        }, 
        draw(bn){
            this.drawer = true;
            this.message = "It's a Draw."
        },
        lose(bn){
            this.ComPoints++;
            this.loser = true;
            this.message = "You lose..."
        }
    }
}
</script>

<style scoped>
header{
	width: 100%;
	height: 15%;
	padding-top: 25px;
	background-color: #ecf0f1;
	box-sizing: border-box;
}
header h1{
	text-align: center;
	margin: 0;
}
.container{
	position: relative;
    height: 600px;
	width: 100%;
	box-sizing: border-box;
	padding: 30px;
	background-color: #2C3E50;
}
.score-container{
	position: relative;
	margin: 0 auto;
	width: 250px;
	height: 80px;
	color: white;
}
#score{
	position: absolute;
	text-align: center;
	font-size: 40px;
  width: 100%;
}
.user{
	position: absolute;
	left: 0;
	top: 50%;
	transform: translate(-50%, -50%);
	background-color: #e14a67;
	width: 40px;
	height: 15px;
	font-size: 10px;
	padding: 2px 10px;
	box-sizing: border-box;
}
.com{
	position: absolute;
	right: 0;
	top: 50%;
	transform: translate(50%, -50%);
	background-color: #e14a67;
	width: 40px;
	height: 15px;
	font-size: 10px;
	padding: 2px 10px;
	box-sizing: border-box;
}
.buttons{
	width: 280px;
	position: absolute;
	top: 20%; 
	left: 50%;
	transform: translateX(-50%);
}
.bn{
	width: 80px;
	height: 80px;
  margin :5px;
  border: 3px solid #34495e;
  border-radius: 50%;
  color: #34495e;
  font-size: 40px;
  background-color: white;
  cursor: pointer;
  outline: none;
  transition: .3s;
}
.bn:hover{
  background-color: #34495e;
  border-color: white;
  color: white;
}
#challenge{
	position: absolute;
	top: 43%;
	left: 50%;
	transform: translateX(-50%);
	width: 540px;
	height: 40%;
	display: none;
}
#you{
	position: relative;
	width: 37.5%;
	font-size: 50px;
}
#com{
	position: relative;
	width: 37.5%;
	font-size: 50px;
}
#YourObject{
	position: absolute;
	top: 45%;
	left: 50%;
	transform: translate(-50%, -50%);
	width: 110px;
	height: 110px;
	font-size: 50px;
	padding-top: 20px;
	border: 3px solid #34495e;
  border-radius: 50%;
  color: #34495e;
  background-color: white;
  box-sizing: border-box;
  text-align: center;
}
#ComObject{
	position: absolute;
	top: 45%;
	left: 50%;
	transform: translate(-50%, -50%);
	width: 110px;
	height: 110px;
	font-size: 50px;
	padding-top: 20px;
	border: 3px solid #34495e;
  border-radius: 50%;
  color: #34495e;
  background-color: white;
  box-sizing: border-box;
  text-align: center;
}
#result{
	position: relative;
	width: 25%;
}
#result p{
	position: absolute;
	top: 45%;
	left: 50%;
	transform: translate(-50%, -50%);
	color: white;
	font-size: 30px;
	width: 100%;
	margin: 0;
	text-align: center;
}
.who{
	position: absolute;
	bottom: 5%;
	left: 50%;
	transform: translateX(-50%);
	color: white;
	font-size: 30px;
}
.green{
	width: 70px;
	height: 70px;
  margin: 5px;
  border: 3px solid green;
  box-shadow: 0 0 10px green;
  border-radius: 50%;
  color: #34495e;
  font-size: 35px;
  background-color: white;
  cursor: pointer;
  outline: none;
  transition: .3s;
}
.red{
	width: 70px;
	height: 70px;
  margin: 5px;
  border: 3px solid red;
  box-shadow: 0 0 10px red;
  border-radius: 50%;
  color: #34495e;
  font-size: 35px;
  background-color: white;
  cursor: pointer;
  outline: none;
  transition: .3s;
}
.gray{
  width: 70px;
  height: 70px;
  margin: 5px;
  border: 3px solid #292928;
  box-shadow: 0 0 10px #292928;
  border-radius: 50%;
  color: #34495e;
  font-size: 35px;
  background-color: white;
  cursor: pointer;
  outline: none;
  transition: .3s;
}
</style>