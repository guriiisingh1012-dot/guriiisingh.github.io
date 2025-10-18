<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>For Jerry - With Love</title>
<style>
  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background: #ffe6f0;
    color: #c71585;
    margin: 0;
    padding: 0;
    overflow-x: hidden;
  }
  header {
    background: #ffb6c1;
    padding: 30px 20px;
    text-align: center;
    box-shadow: 0 3px 10px rgba(255, 105, 180, 0.3);
  }
  header h1 {
    margin: 0;
    font-size: 3rem;
    font-weight: bold;
  }
  .quote-section {
    max-width: 600px;
    margin: 40px auto;
    background: #fff0f6;
    border-radius: 15px;
    padding: 20px 30px;
    text-align: center;
    box-shadow: 0 3px 15px rgba(255, 105, 180, 0.15);
  }
  .quote {
    font-size: 1.5rem;
    font-style: italic;
    margin-bottom: 15px;
  }
  .author {
    font-weight: 600;
    color: #a02060;
  }
  .interactive-hearts {
    margin: 40px auto;
    text-align: center;
  }
  .heart-btn {
    font-size: 3rem;
    color: #ff1493;
    border: none;
    background: none;
    cursor: pointer;
    transition: transform 0.3s ease;
    margin: 0 10px;
  }
  .heart-btn:hover {
    transform: scale(1.3);
  }
  .love-note {
    max-width: 600px;
    margin: 40px auto;
    background: #ffe6f2;
    border-radius: 15px;
    padding: 25px;
    box-shadow: 0 3px 20px rgba(255, 20, 147, 0.2);
    text-align: center;
  }
  .love-note textarea {
    width: 90%;
    height: 100px;
    border-radius: 10px;
    border: 2px solid #ff69b4;
    padding: 15px;
    font-size: 1.1rem;
    resize: none;
  }
  .love-note button {
    margin-top: 15px;
    background-color: #ff69b4;
    color: white;
    border: none;
    padding: 12px 25px;
    border-radius: 10px;
    font-size: 1.1rem;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  .love-note button:hover {
    background-color: #ff1493;
  }
  .message {
    margin-top: 20px;
    color: #c71585;
    font-weight: 700;
  }
  footer {
    text-align: center;
    padding: 20px;
    background: #ffb6c1;
    margin-top: 50px;
    color: white;
    font-weight: 600;
  }
</style>
</head>
<body>

<header>
  <h1>For Jerry, With All My Love ❤️</h1>
</header>

<div class="quote-section">
  <div class="quote" id="quoteText">"You are my today and all of my tomorrows."</div>
  <div class="author" id="quoteAuthor">- Leo Christopher</div>
</div>

<div class="interactive-hearts">
  <button class="heart-btn" onclick="showLoveNote()">💌 Send Love Note</button>
  <button class="heart-btn" onclick="toggleHearts()">❤️ Show Hearts</button>
</div>

<div id="heartsContainer" style="text-align:center; margin-top:20px; display:none;">
  <span style="font-size:40px;">❤️ 🧡 💛 💚 💙 💜</span>
</div>

<div class="love-note" id="loveNoteSection" style="display:none;">
  <textarea id="loveNoteInput" placeholder="Write a love note to Jerry..."></textarea>
  <br />
  <button onclick="submitLoveNote()">Send</button>
  <div class="message" id="loveNoteMessage"></div>
</div>

<footer>
  Made with ❤️ for Jerry by Someone Who Loves You
</footer>

<script>
  const quotes = [
    {text: "You are my today and all of my tomorrows.", author: "Leo Christopher"},
    {text: "I love you not only for what you are, but for what I am when I am with you.", author: "Roy Croft"},
    {text: "You are the finest, loveliest, tenderest, and most beautiful person I have ever known.", author: "F. Scott Fitzgerald"},
    {text: "In you, I've found the love of my life and my closest, truest friend.", author: "Unknown"},
    {text: "My heart is, and always will be, yours.", author: "Jane Austen"}
  ];

  let heartVisible = false;

  function toggleHearts() {
    heartVisible = !heartVisible;
    document.getElementById('heartsContainer').style.display = heartVisible ? 'block' : 'none';
  }

  function showLoveNote() {
    const section = document.getElementById('loveNoteSection');
    section.style.display = section.style.display === 'block' ? 'none' : 'block';
    document.getElementById('loveNoteMessage').innerText = "";
  }

  function submitLoveNote() {
    const input = document.getElementById('loveNoteInput').value.trim();
    if (input.length === 0) {
      document.getElementById('loveNoteMessage').innerText = "Please write something sweet!";
      return;
    }
    document.getElementById('loveNoteMessage').innerText = "Your love note has been sent to Jerry! ❤️";
    document.getElementById('loveNoteInput').value = "";
  }

  // Rotate quotes every 7 seconds
  let quoteIndex = 0;
  setInterval(() => {
    quoteIndex = (quoteIndex + 1) % quotes.length;
    document.getElementById('quoteText').innerText = `"${quotes[quoteIndex].text}"`;
    document.getElementById('quoteAuthor').innerText = `- ${quotes[quoteIndex].author}`;
  }, 7000);
</script>

</body>
</html>
