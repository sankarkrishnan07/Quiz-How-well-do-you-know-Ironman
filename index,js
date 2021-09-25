var readlineSync = require('readline-sync');
const chalk = require ("chalk");

//High scorers
var highScores = [
  {
    name : "Happy",
    points : 4
  },
  {
    name : "Peter",
    points : 3
  }
];

var questions = [];

//The yes or no queation and answer bank
var yesOrNoQuestions = [
  {
    question : "Is Tony Stark the real name of Ironman?",
    answer : "Y",
  },
  {
    question : "Does Iromman own SHIELD?",
    answer : "N",
  },
  {
    question : "Is Friday Ironman's first AI assistant?",
    answer : "N",
  },
  {
    question : "Did Ironman discover a new element?",
    answer : "Y",
  },
  {
    question : "Iron man has only 2 standalone movies y/n? ",
    answer : "N",
  }
]

//The mcq queation and answer bank
var mcqQuestions = [
  {
    question : "Name of the device that powers Ironman's armor?\n1.Tesseract\n2.Arc Reactor\n3.Adamantium\n\n",
    answer : "2",
  },
  {
    question : "Ironman's real name?\n1.Howard Stark\n2.Peter\n3.Tony Stark\n\n",
    answer : "3",
  },
  {
    question : "Main colours of Ironman's Armor?\n1.Red and Gold\n2.Green and Yellow\n3.Red and black\n\n",
    answer : "3"
  },
  {
    question : "Ironman's favourite snack?\n1.Cheese Burger\n2.Cookie\n3.Pizza\n\n",
    answer : "1"
  },
  {
    question : "How many standalone movies Ironman has?\n1.2\n2.3\n3.4\n\n",
    answer : "2"
  }
]

//game logic
var score = 0;

function game(question,answer){
  var userAnswer=readlineSync.question(chalk.blue(question));

  if(userAnswer.toLowerCase()==answer.toLowerCase()){
    console.log(chalk.bold.green("Right!"));
    score++;
  }else{
    console.log(chalk.bold.red("Wrong!"));
  }
  
//display the current score
  console.log("Current Score : "+score);
  console.log("--------------\n");
}

//calling the game logic
function play(){
  console.log("Level 1\n");

  for (var i=0; i<questions.length; i++){

    if(i==2){
      if(score==2){
        console.log("YAY! You have cleared Level 1. Proceeding to Level 2\n");
      }
      else{
        console.log("\nOops! You did not clear Level 1. Better luck next time!")
        break;
      }
    }
    game(questions[i].question,questions[i].answer);
    
  }

  //display final scores
  if(score>0){
    console.log("\nYAY! You scored "+score +"\n\nCheck out the high scores!");

    //display the high scorers
    highScores.map(score => console.log(chalk.blue(score.name)," : ",score.points));

    highScoreCheck();
  }
  else{
    console.log("You scored 0.Better luck next time!")
  }
}

function highScoreCheck(){

  var firstScore=4;
  var secondScore=3;
  if((score>=firstScore) || (score>=secondScore)){
    console.log("\nWow! You have cracked a high score. Send a screenshot and I will update it.")
  }

   if (score>=4){
    console.log("You scored more than 3. So you do know Ironman well!")
  }
}

//greet,get the player name, decide game type
function welcome(){
  userName = readlineSync.question(chalk.blue("Hello there! Welcome to the quiz\n 'How well do you know IRONMAN'\nPlease provide your name.\n\n"));

  console.log("\nHello "+userName+"! \n\nGood luck for the game and let's see if you make it to the the top scorers list\n\nNote:There will be two levels and 2 questions for level 1 and 3 questions for level 2\n");

  var gameType = readlineSync.question(chalk.green("Choose your game \n 1.Y/N type questions (press 1) \n 2.Multiple choice (press 2)\n\n"));

 if(gameType=='1'){
    questions = yesOrNoQuestions.slice();
    console.log("\nHere you go! Give your answer as y or n and press enter.\n");
    play();
   }
   else if(gameType=='2'){
    questions = mcqQuestions.slice();
    console.log("\nHere you go! Give your answer as 1, 2 or 3 according to the options and press enter.\n");
    play();
   }
   else{
     console.log("You did not press 1 or 2. Please restart the game if you want to play again.");
   }
}

function thankYou(){
    console.log("\n---Thank you for playing the game "+userName+"!---");
  }


welcome();
thankYou();