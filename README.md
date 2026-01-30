<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>I Miss You Siya</title>

<style>
body{
  margin:0;
  height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  background:linear-gradient(135deg,#ff4d6d,#ff9a9e);
  overflow:hidden;
  font-family:Arial, sans-serif;
}

#mainPhoto{
  width:280px;
  border-radius:20px;
  cursor:pointer;
  box-shadow:0 0 30px rgba(255,0,100,0.8);
}

/* floating hearts */
.heart{
  position:absolute;
  color:pink;
  font-size:20px;
  animation:float 6s linear infinite;
}

@keyframes float{
  0%{transform:translateY(100vh);opacity:0}
  10%{opacity:1}
  100%{transform:translateY(-10vh);opacity:0}
}

/* popup */
#popup{
  position:fixed;
  top:0; left:0;
  width:100%;
  height:100%;
  background:rgba(0,0,0,0.6);
  display:none;
  justify-content:center;
  align-items:center;
  flex-direction:column;
  z-index:10;
}

#popup img{
  max-width:85%;
  border-radius:20px;
  box-shadow:0 0 40px pink;
}

#popup h1{
  color:white;
  margin-top:15px;
  text-shadow:0 0 10px pink;
}

#popup button{
  margin-top:15px;
  padding:10px 22px;
  font-size:16px;
  border:none;
  border-radius:25px;
  background:pink;
  cursor:pointer;
}
</style>
</head>

<body>

<img src="https://i.ibb.co/d03bvZmt/photo.jpg" id="mainPhoto">

<div id="popup">
  <img src="https://i.ibb.co/d03bvZmt/photo.jpg">
  <h1>I miss you Siya 💋</h1>
  <button onclick="closePopup()">Close</button>
</div>

<script>
document.getElementById("mainPhoto").onclick = function(){
  document.getElementById("popup").style.display="flex";
};

function closePopup(){
  document.getElementById("popup").style.display="none";
}

// hearts animation
setInterval(()=>{
  let h=document.createElement("div");
  h.className="heart";
  h.innerHTML="❤";
  h.style.left=Math.random()*100+"vw";
  h.style.fontSize=(15+Math.random()*20)+"px";
  document.body.appendChild(h);
  setTimeout(()=>h.remove(),6000);
},300);
</script>

</body>
</html>
