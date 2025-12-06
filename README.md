<!doctype html>
<html lang="sq">
<head>
<meta charset="utf-8" />
<title>Aplikacion me 2 Seksione</title>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
  body{
    margin:0;
    font-family: Arial, Helvetica, sans-serif;
    background:#eef2f7;
    padding:20px;
  }

  .container{
    max-width:900px;
    margin:auto;
  }

  h1{
    text-align:center;
    margin-bottom:20px;
  }

  .section{
    background:white;
    padding:20px;
    border-radius:12px;
    margin-bottom:25px;
    box-shadow:0 4px 14px rgba(0,0,0,0.08);
  }

  .section h2{
    margin-top:0;
    color:#2563eb;
  }

  .input-row{
    display:flex;
    gap:10px;
    margin-bottom:15px;
  }

  input, textarea{
    flex:1;
    padding:12px;
    border-radius:8px;
    border:1px solid #ccd4dd;
    font-size:15px;
  }

  button{
    padding:12px 18px;
    border:0;
    background:#2563eb;
    color:white;
    border-radius:8px;
    cursor:pointer;
    font-size:15px;
    font-weight:bold;
  }

  button.delete{
    background:#d62828;
  }

  .list{
    margin-top:10px;
  }

  .item{
    display:flex;
    justify-content:space-between;
    align-items:center;
    background:#f8fafc;
    border:1px solid #e2e8f0;
    padding:12px;
    border-radius:8px;
    margin-bottom:8px;
  }

  textarea{
    height:70px;
    resize:none;
  }
</style>
</head>
<body>

<div class="container">
  <h1>Aplikacion me 2 Seksione</h1>

  <!-- ======================== Seksioni 1 ======================== -->
  <div class="section">
    <h2>Detyrat</h2>

    <div class="input-row">
      <input id="taskInput" type="text" placeholder="Shkruaj detyrën...">
      <button onclick="addTask()">Shto</button>
    </div>

    <div id="tasks" class="list">
      <div class="item">
        <span>Përgatit prezantimin</span>
        <button class="delete" onclick="removeItem(this)">Fshi</button>
      </div>

      <div class="item">
        <span>Bëj ushtrimet e programimit</span>
        <button class="delete" onclick="removeItem(this)">Fshi</button>
      </div>
    </div>
  </div>

  <!-- ======================== Seksioni 2 ======================== -->
  <div class="section">
    <h2>Shënime</h2>

    <div class="input-row">
      <textarea id="noteInput" placeholder="Shkruaj një shënim..."></textarea>
      <button onclick="addNote()">Shto</button>
    </div>

    <div id="notes" class="list">
      <div class="item">
        <span>Ide: Krijo një aplikacion më të madh</span>
        <button class="delete" onclick="removeItem(this)">Fshi</button>
      </div>
    </div>
  </div>
</div>

<script>
function addTask(){
  const val = taskInput.value.trim();
  if(!val) return;
  tasks.innerHTML += `
    <div class="item">
      <span>${val}</span>
      <button class="delete" onclick="removeItem(this)">Fshi</button>
    </div>`;
  taskInput.value="";
}

function addNote(){
  const val = noteInput.value.trim();
  if(!val) return;
  notes.innerHTML += `
    <div class="item">
      <span>${val}</span>
      <button class="delete" onclick="removeItem(this)">Fshi</button>
    </div>`;
  noteInput.value="";
}

function removeItem(btn){
  btn.parentElement.remove();
}
</script>

</body>
</html>
