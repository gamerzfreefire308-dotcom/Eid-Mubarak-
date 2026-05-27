<audio id="music" loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3">
</audio>

<script>
function start(){
  document.getElementById("screen").style.display="none";
  document.getElementById("box").style.display="block";

  let music = document.getElementById("music");

  music.play().catch(()=>{
    console.log("Audio blocked, retrying...");
    document.body.addEventListener("click", ()=>music.play(), {once:true});
  });

  typing();
  stars();
  hearts();
}
</script>
