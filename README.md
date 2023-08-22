# array.java


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simple Chat Engine</title>
<style>
  #chat-container {
    width: 300px;
    height: 400px;
    border: 1px solid #ccc;
    padding: 10px;
    overflow-y: scroll;
  }
</style>
</head>
<body>
  <div id="chat-container"></div>
  <input type="text" id="user-input" placeholder="Digite sua mensagem">
  <button id="send-btn">Enviar</button>

  <script src="chat.js"></script>
</body>
</html>






document.addEventListener("DOMContentLoaded", () => {
    const chatContainer = document.getElementById("chat-container");
    const userInput = document.getElementById("user-input");
    const sendButton = document.getElementById("send-btn");
    
    const messages = [];
  
    sendButton.addEventListener("click", () => {
      const userMessage = userInput.value.trim();
      if (userMessage !== "") {
        messages.push({ type: "user", text: userMessage });
        updateChat();
        userInput.value = "";
      }
    });
  
    const updateChat = () => {
      let chatHTML = "";
      messages.forEach(message => {
        chatHTML += `<div class="${message.type}">${message.text}</div>`;
      });
      chatContainer.innerHTML = chatHTML;
      chatContainer.scrollTop = chatContainer.scrollHeight;
    };
  });
  
