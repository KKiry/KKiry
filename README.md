- š Hi, Iām @KKiry
- š Iām interested in ...
- š± Iām currently learning ...
- šļø Iām looking to collaborate on ...
- š« How to reach me ...

<!---
KKiry/KKiry is a āØ special āØ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->const Discord = require('discord.js');
const client = new Discord.Client();

client.on('ready', () => {
  console.log(`Logged in as ${client.user.tag}!`);
});

const convertEmoji = (who) => { //1
  if(who === "ź°ģ"){
    return ":v: ";
  }
  else if(who === "ė°ģ"){
    return ":fist: ";
  }
  else if(who === "ė³“"){
    return ":raised_back_of_hand: "; //
  }
}

client.on('message', msg => {
  if(msg.content === "ģ¼"){
    msg.reply("ķø!");
  }

  if(msg.content === "ź°ģ" || msg.content === "ė°ģ" || msg.content === "ė³“") {
    const human = msg.content;
    const list = ["ź°ģ", "ė°ģ", "ė³“"];
    const random = Math.floor(Math.random() * 3);
    const bot = list[random];
    let winner = "";

    if(human === bot) {
      winner = "ė¹ź¹";
    }
    else {
      human === "ź°ģ" ? (winner = bot === "ė°ģ" ? "ė“" : "ģøź°") : "";
      human === "ė°ģ" ? (winner = bot === "ė³“" ? "ė“" : "ģøź°") : "";
      human === "ė³“" ? (winner = bot === "ź°ģ" ? "ė“" : "ģøź°") : "";
    }

    const result =
`
ģ¬ė : ${convertEmoji(human)} vs ė“ : ${convertEmoji(bot)}
${winner === "ė¹ź¹" ? "ģ°ė¦¬ė ė¹ź²¼ė¤ ģøź°." : winner + "ģ ģ¹ė¦¬ė¤"}
`
    msg.reply(result);
  }

});

client.login('ODc4NjM5MDI1NzM5NjkwMDA2.YSEGXA.kgKQyD0gqUiHOUMFT-E4UZ96dck"); 
