- 👋 Hi, I’m @KKiry
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
KKiry/KKiry is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->const Discord = require('discord.js');
const client = new Discord.Client();

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
});

const convertEmoji = (who) => { //1
  if(who === "가위"){
    return ":v: ";
  }
  else if(who === "바위"){
    return ":fist: ";
  }
  else if(who === "보"){
    return ":raised_back_of_hand: "; //
  }
}

client.on('message', msg => {
  if(msg.content === "야"){
    msg.reply("호!");
  }

  if(msg.content === "가위" || msg.content === "바위" || msg.content === "보") {
    const human = msg.content;
    const list = ["가위", "바위", "보"];
    const random = Math.floor(Math.random() * 3);
    const bot = list[random];
    let winner = "";

    if(human === bot) {
      winner = "비김";
    }
    else {
      human === "가위" ? (winner = bot === "바위" ? "봇" : "인간") : "";
      human === "바위" ? (winner = bot === "보" ? "봇" : "인간") : "";
      human === "보" ? (winner = bot === "가위" ? "봇" : "인간") : "";
    }

    const result =
`
사람 : ${convertEmoji(human)} vs 봇 : ${convertEmoji(bot)}
${winner === "비김" ? "우리는 비겼다 인간." : winner + "의 승리다"}
`
    msg.reply(result);
  }

});

client.login('ODc4NjM5MDI1NzM5NjkwMDA2.YSEGXA.kgKQyD0gqUiHOUMFT-E4UZ96dck"); 
