<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Advanced Lua Obfuscator with Token Pinning</title>
<style>
  body { background:#111; color:#eee; font-family: monospace; display:flex; flex-direction:column; align-items:center; padding:20px;}
  textarea { width:90%; height:150px; margin:10px 0; background:#222; color:#eee; border:none; padding:10px; resize:none;}
  button { padding:10px 20px; margin:5px; background:#444; color:#eee; border:none; cursor:pointer;}
  button:hover { background:#555; }
  h1 { font-size:24px; text-align:center; }
  input { padding:5px; margin:5px; width:200px; }
</style>
</head>
<body>
<h1>Advanced Lua Obfuscator with Token Pinning</h1>

<textarea id="input" placeholder="Paste your Lua script here"></textarea>
<div>
  <button onclick="obfuscate()">Obfuscate</button>
</div>

<div id="tokenSection" style="display:none;">
  <p>Copy this token and pin it before copying your obfuscated script:</p>
  <input type="text" id="tokenInput" readonly>
  <button onclick="pinToken()">Pin Token</button>
</div>

<textarea id="output" placeholder="Your obfuscated script will appear here" readonly></textarea>

<hr>

<h2>Deobfuscate</h2>
<textarea id="deobInput" placeholder="Paste your obfuscated Lua script here"></textarea>
<br>
<input type="text" id="deobToken" placeholder="Enter your token">
<button onclick="deobfuscate()">Deobfuscate</button>
<textarea id="deobOutput" placeholder="Deobfuscated Lua code will appear here" readonly></textarea>

<script>
// Random function/variable name generator
function randName(len=6){
  let chars = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ';
  let s='';
  for(let i=0;i<len;i++) s+=chars[Math.floor(Math.random()*chars.length)];
  return s;
}

// Random token generator (base62)
function generateToken(len=16){
  let chars = 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789';
  let t='';
  for(let i=0;i<len;i++) t+=chars[Math.floor(Math.random()*chars.length)];
  return t;
}

// Store pinned tokens in localStorage
function saveToken(token, code){
  localStorage.setItem(token, code);
}
function getToken(token){
  return localStorage.getItem(token);
}

// Global current token before pinning
let currentToken = null;
let currentObfCode = null;

// Obfuscate function
function obfuscate(){
  let code = document.getElementById('input').value;
  if(!code) return alert("Please enter a Lua script first!");

  // Dummy functions
  let dummyFuncs = '';
  for(let i=0;i<3;i++){
    let fname = randName();
    dummyFuncs += `function ${fname}() return ${Math.floor(Math.random()*1000)} end\n`;
  }

  // Encode to base36
  let encoded = code.split('').map(c=>c.charCodeAt(0).toString(36)).join(',');
  let mainFuncName = randName();
  let token = generateToken();

  let luaObf = `
-- Token: ${token}
${dummyFuncs}
local ${mainFuncName}=function()
  local s="${encoded}"
  local t=""
  for v in s:gmatch("([^,]+)") do
    t=t..string.char(tonumber(v,36))
  end
  return t
end
loadstring(${mainFuncName}())()
`;

  currentToken = token;
  currentObfCode = luaObf;

  // Show token section
  document.getElementById('tokenSection').style.display = 'block';
  document.getElementById('tokenInput').value = token;

  alert("Token generated! Pin it before copying your obfuscated script.");
}

// Pin token (confirm)
function pinToken(){
  if(!currentToken || !currentObfCode) return alert("No token/code to pin!");
  saveToken(currentToken, currentObfCode);
  document.getElementById('output').value = currentObfCode;
  alert("Token pinned! You can now copy your obfuscated Lua script safely.");
  currentToken = null;
  currentObfCode = null;
}

// Deobfuscate function
function deobfuscate(){
  let code = document.getElementById('deobInput').value;
  let token = document.getElementById('deobToken').value;
  if(!code || !token) return alert("Please provide both obfuscated code and token!");

  let savedCode = getToken(token);
  if(!savedCode){
    return alert("Invalid token or you are not the owner. Deobfuscate denied.");
  }

  // Decode base36 numbers
  let match = code.match(/local \w+=function\(\)\s+local s="([^"]+)"/s);
  if(match && match[1]){
    let nums = match[1].split(',');
    let text = '';
    nums.forEach(n=>{ text+=String.fromCharCode(parseInt(n,36)); });
    document.getElementById('deobOutput').value = text;
  } else {
    alert("Invalid obfuscated format.");
  }
}
</script>
</body>
</html>
