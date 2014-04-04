

<object width="500" height="300">
<param name="movie" value="http://www.youtube.com/v/ZblBWhllDqY?version=3&autohide=2&autoplay=0&controls=1&disablekb=0&egm=0&enablejapi=0&fs=1&loop=0&rel=0&showinfo=0&showsearch=0"></param>
<param name="allowScriptAccess" value="always"></param>
<param name="allowFullScreen" value="true"></param>
<embed src="http://www.youtube.com/v/ZblBWhllDqY?version=3&autohide=2&autoplay=0&controls=1&disablekb=0&egm=0&enablejapi=0&fs=1&loop=0&rel=0&showinfo=0&showsearch=0" type="application/x-shockwave-flash" allowfullscreen="true" allowscriptaccess="always" width="425" height="355"></embed>
</object>



<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.0 Transitional//EN">
<HTML>
<HEAD>
<meta http-equiv="Content-Type" content="text/html; charset=windows-1252">
<TITLE>Pokemon Encounter Code Generator</TITLE>
<script type="text/javascript" src="img/gradient.js"></script>
<link rel="stylesheet" href='style.css'>
<style type="text/css">
<!--

table {
 border-left-style: outset; 
 border-left-width: 3; 
 border-right-style: outset; 
 border-right-width: 3;
-moz-border-left-colors: #F1F1F1;
-moz-border-right-colors: #969696;
}

table.first { 
 border-top-style: outset; 
 border-top-width: 3;
-moz-border-top-colors: #F1F1F1;
-moz-border-bottom-colors: #969696;
}

table.second {
 border-top-style: groove;
 border-top-width: 2px;
 border-bottom-style: outset; 
 border-bottom-width: 3;
-moz-border-top-colors: #969696 #F1F1F1; 
-moz-border-bottom-colors: #969696;
}

.ridge {
-moz-border-top-colors: #F1F1F1 #969696;
-moz-border-left-colors: #F1F1F1 #969696;
-moz-border-right-colors: #969696 #F1F1F1;
-moz-border-bottom-colors: #969696 #F1F1F1;
}

.groove {
-moz-border-top-colors: #969696 #FFFFFF;
-moz-border-left-colors: #969696 #FFFFFF;
-moz-border-right-colors: #FFFFFF #969696;
-moz-border-bottom-colors: #FFFFFF #969696;  
}

.btmgroove {
-moz-border-bottom-colors: #F1F1F1 #969696;
}

td {
 font-family: Times New Roman, Times, serif; 
 font-size: 16px;
}

code {
 font-size: 14px; 
}

.power {
 font-size: 13px;
}

// -->
</style>
<script language="JavaScript" type="text/javascript">
<!--
  if (window.attachEvent){
   window.attachEvent("onkeydown", KeyListener);
  }else{
  window.onKeyDown = KeyListener;
  }

function KeyListener (e, target) {
// Intercepts ENTER keypress event and removes focus on element
if (e.keyCode == 13 || e.keyCode == 3){
 target.blur();
 } 
}
// -->
</script>
</HEAD>

<BODY bgColor="#ffffff" onLoad="Show_ID(); NewPoke()">
<SCRIPT language="JavaScript" type="text/javascript">
<!-- start
// Originally:  Pokemon Maker v2.02 
// Most Functions by kpdavatar@programmer.net
// Script has been adapted by gator_shark for use with the wild Latios encounter addresses
// The main original function that was needed is MAP/PID generation
// GS-AR Encryption is also used
// Please credit kpdavatar for the program itself ! 

// Changes made after version 1: 
// Added Pointer code-types for a RNG version
// Capped off the Contest stats to 255
// Set Current HP initial value to 1
// Rewrote the MAP/PID code labels for Gender
// Added code label for Unown shape
// Added Save TrainerIDs button
// Added locations and codes for FireRed/LeafGreen
// Rewrote the Location list to remove the value before the place name
// Changed the Prevent Fleeing code to use Shadow Tag directly
// Fixed location code problem in Firefox browers
// Eliminated possibility of nonnumerical and negative value inputs 
// Cleaned up script
// Evaluate pokemon stats on pageload (and on reset)
// Added a Jump-to Dex number feature
// Made PokeDex chosen to also sort the Pokemon species list
// Disabled Unown option when some other pokemon is selected
// Made MaxIV button zero IVs when IVs were maxed
// Changed the Prevent Fleeing code to use the move Block instead
// [version 1.4.0] Added RNG version Pointer codes for FireRed/LeafGreen
// Sped up creation of National Dex pokemon list
// Corrected Deoxys stats for v1.1 of FireRed/LeafGreen

// Added CSS styles for border colors in Firefox; Cross-browser gradient for titlebar 
// Made Max stats button zero Contest Stats when all are 255
// Using regular expressions in value tests, eliminates NaN
// Added Wurmple evolution choices
// Added MAP/PID input box for defining Spinda's spots

function Thanks(){
var tlog=" ";
tlog="Thanks to:\r\n";
tlog+="Nintendo for making Gamboy Advance.\r\n";
tlog+=" No GBA, no game!\r\n";
tlog+="Game Freak for making Pokemon Ruby/Sapphire.\r\n";
tlog+=" No game, no reason to make program!\r\n";
tlog+="Nintendo for making GameCube adapter for playing Gameboy Advance Games.\r\n";
tlog+=" Needed for screen captures of images!\r\n";
tlog+="Datel for making ActionReplay v3 for Gameboy Advance.\r\n";
tlog+=" Needed for putting Pokemon in game!\r\n";
tlog+=" Needed for save game dump, even if it was 64k.\r\n";
tlog+="  Saves needed for find 80 bytes of a Pokemon.\r\n";
tlog+="Raihan Kibria.\r\n";
tlog+=" Maker of the Hex editor I used to look at save games from ActionReplay.\r\n";
tlog+=" Needed to find 80 bytes to make a Pokemon.\r\n";
tlog+="http://www.Codejunkies.com\r\n";
tlog+=" For codes on Pokemon.\r\n";
tlog+="Parasyte\r\n";
tlog+=" For infomation on ActionReplay v3 codes\r\n";
tlog+="http://pokefor.greenchu.de/meowth346/ for all the Images and Information on Pokemon.\r\n";
tlog+=" Soo much infomation on moves, Pokemon Abilities, Hidden Power...\r\n";
tlog+="xyzman for the ABCD structure order and Special Ribbons.\r\n";
tlog+=" For the two bits of information I did not find by myself on Pokemon.\r\n";
tlog+="BurleyEd For Info. on Fire/Leaf alternate Deoxy/Mew/...\r\n";
document.PokemonForm.LogC.value=tlog;
}

function MaxCurrentHP(){
var f=document.PokemonForm;
f.CurrentHP.value=f.HPDex.value;
}

function MaxContest(){
var f=document.PokemonForm;
if(f.Cool.value==255 && f.Beauty.value==255 && 
   f.Cute.value==255 && f.Smart.value==255 &&
   f.Tough.value==255)
 {   
  f.Cool.value=0;
  f.Beauty.value=0;
  f.Cute.value=0;
  f.Smart.value=0;
  f.Tough.value=0;
 }else{
  f.Cool.value=255;
  f.Beauty.value=255;
  f.Cute.value=255;
  f.Smart.value=255;
  f.Tough.value=255;
 }
}

function TestNumerical(){
// limits Contest values and eliminates nonnumerical data
var f=document.PokemonForm;
var numexp=/[^0-9]/;
if(numexp.test(f.TID.value)){f.TID.value=0;}
if(numexp.test(f.STID.value)){f.STID.value=0;}
if(f.CurrentHP.value<0 || numexp.test(f.CurrentHP.value)){f.CurrentHP.value=1;}
if(f.Cool.value>255){f.Cool.value=255;}
if(f.Cool.value<0 || numexp.test(f.Cool.value)){f.Cool.value=0;}
if(f.Beauty.value>255){f.Beauty.value=255;}
if(f.Beauty.value<0 || numexp.test(f.Beauty.value)){f.Beauty.value=0;}
if(f.Cute.value>255){f.Cute.value=255;}
if(f.Cute.value<0 || numexp.test(f.Cute.value)){f.Cute.value=0;}
if(f.Smart.value>255){f.Smart.value=255;}
if(f.Smart.value<0 || numexp.test(f.Smart.value)){f.Smart.value=0;}
if(f.Tough.value>255){f.Tough.value=255;}
if(f.Tough.value<0 || numexp.test(f.Tough.value)){f.Tough.value=0;}
f.CurrentHP.value=1*f.CurrentHP.value;
f.Cool.value=1*f.Cool.value;
f.Beauty.value=1*f.Beauty.value;
f.Cute.value=1*f.Cute.value;
f.Smart.value=1*f.Smart.value;
f.Tough.value=1*f.Tough.value;
}

function MaxDV(){
var f=document.PokemonForm;
var dv=0;
if(f.HPDV.selectedIndex==31 && f.AtkDV.selectedIndex==31 && 
   f.DefDV.selectedIndex==31 && f.SpeDV.selectedIndex==31 &&
   f.SpADV.selectedIndex==31 && f.SpDDV.selectedIndex==31)
 {
  f.HPDV.options[0].selected=true;
  f.AtkDV.options[0].selected=true;
  f.DefDV.options[0].selected=true;
  f.SpeDV.options[0].selected=true;
  f.SpADV.options[0].selected=true;
  f.SpDDV.options[0].selected=true;
 }else{   
  f.HPDV.options[31].selected=true;
  f.AtkDV.options[31].selected=true;
  f.DefDV.options[31].selected=true;
  f.SpeDV.options[31].selected=true;
  f.SpADV.options[31].selected=true;
  f.SpDDV.options[31].selected=true;
 }
dv=HPower();
}

function RandomDV(){
var f=document.PokemonForm;
var dv=0;
dv=Math.round(Math.random() * 31);
f.HPDV.options[dv].selected=true;
dv=Math.round(Math.random() * 31);
f.AtkDV.options[dv].selected=true;
dv=Math.round(Math.random() * 31);
f.DefDV.options[dv].selected=true;
dv=Math.round(Math.random() * 31);
f.SpeDV.options[dv].selected=true;
dv=Math.round(Math.random() * 31);
f.SpADV.options[dv].selected=true;
dv=Math.round(Math.random() * 31);
f.SpDDV.options[dv].selected=true;
dv=HPower();
}

function XQ(what){
var f=document.PokemonForm;
var numexp=/[^0-9]/;
var o=" ";
var s=0;
var i=0;
var n=0;
if(what=="X"){i=f.XLvl.value;}
if(i<0){i=1;}
if(i>100){i=100;}
if(numexp.test(i)){i=1;}
f.XLvl.value=i*1;  // multiplying by 1 to avoid nonnumerical data
s=f.Species.options[f.Species.selectedIndex].value;
o=PokeDex(s);
n=FI(o,"~",21);
n=HPower()
}

function HPower(){
f=document.PokemonForm;
var o=" ";
var pd=" ";
var a0=0;
var a1=0;
var a2=0;
var a3=0;
var a4=0;
var a5=0;
var p=0;
var pg=0;
var q=0;
var hpower=" ";
pg=f.Species.options[f.Species.selectedIndex].value;
pd=PokeDex(pg);
o=FI(pd,"~",21);
p=parseInt(o,10);
a0=(Math.floor((((2*FI(pd,"~",4))-(-1*f.HPDV.selectedIndex)-Math.ceil(0/-4))*f.XLvl.value)/100)-(-10)-(-1*f.XLvl.value));
a1=Math.floor((Math.floor((((2*FI(pd,"~",5))-(-1*f.AtkDV.selectedIndex)-Math.ceil(0/-4))*f.XLvl.value)/100)-(-5))*PerMod("Atk"));
a2=Math.floor((Math.floor((((2*FI(pd,"~",6))-(-1*f.DefDV.selectedIndex)-Math.ceil(0/-4))*f.XLvl.value)/100)-(-5))*PerMod("Def"));
a3=Math.floor((Math.floor((((2*FI(pd,"~",7))-(-1*f.SpeDV.selectedIndex)-Math.ceil(0/-4))*f.XLvl.value)/100)-(-5))*PerMod("Spe"));
a4=Math.floor((Math.floor((((2*FI(pd,"~",8))-(-1*f.SpADV.selectedIndex)-Math.ceil(0/-4))*f.XLvl.value)/100)-(-5))*PerMod("SpA"));
a5=Math.floor((Math.floor((((2*FI(pd,"~",9))-(-1*f.SpDDV.selectedIndex)-Math.ceil(0/-4))*f.XLvl.value)/100)-(-5))*PerMod("SpD"));
f.HPDex.value=a0;
f.AtkDex.value=a1;
f.DefDex.value=a2;
f.SpeDex.value=a3;
f.SpADex.value=a4;
f.SpDDex.value=a5;
p=0;
q=(1*f.HPDV.selectedIndex)%4;
if(q==2||q==3){p+=1;}
q=(1*f.AtkDV.selectedIndex)%4;
if(q==2||q==3){p+=2;}
q=(1*f.DefDV.selectedIndex)%4;
if(q==2||q==3){p+=4;}
q=(1*f.SpeDV.selectedIndex)%4;
if(q==2||q==3){p+=8;}
q=(1*f.SpADV.selectedIndex)%4;
if(q==2||q==3){p+=16;}
q=(1*f.SpDDV.selectedIndex)%4;
if(q==2||q==3){p+=32;}
p=Math.floor((p*40)/63)+30;
f.HidePower.value=p;
p=0;
q=(1*f.HPDV.selectedIndex)%2;
if(q==1){p+=1;}
q=(1*f.AtkDV.selectedIndex)%2;
if(q==1){p+=2;}
q=(1*f.DefDV.selectedIndex)%2;
if(q==1){p+=4;}
q=(1*f.SpeDV.selectedIndex)%2;
if(q==1){p+=8;}
q=(1*f.SpADV.selectedIndex)%2;
if(q==1){p+=16;}
q=(1*f.SpDDV.selectedIndex)%2;
if(q==1){p+=32;}
p=Math.floor((p*15)/63);
hpower=HPowerType(p);
f.PowerType.value=FI(hpower,"~",1);
return p;
}

function PerMod(w){
var f=document.PokemonForm;
var o= 1.0;
var n=0;
var atkb=""
var defb=""
var speb=""
var spab=""
var spdb=""
n=f.Nature.selectedIndex;
o=1.0;
if(w=="Atk"){
if(n==1){o=1.1;atkb="+";}
if(n==2){o=1.1;atkb="+";}
if(n==3){o=1.1;atkb="+";}
if(n==4){o=1.1;atkb="+";}
if(n==5){o=0.9;atkb="-";}
if(n==10){o=0.9;atkb="-";}
if(n==15){o=0.9;atkb="-";}
if(n==20){o=0.9;atkb="-";}
f.AtkBoost.value=atkb;
}
if(w=="Def"){
if(n==1){o=0.9;defb="-";}
if(n==5){o=1.1;defb="+";}
if(n==7){o=1.1;defb="+";}
if(n==8){o=1.1;defb="+";}
if(n==9){o=1.1;defb="+";}
if(n==11){o=0.9;defb="-";}
if(n==16){o=0.9;defb="-";}
if(n==21){o=0.9;defb="-";}
f.DefBoost.value=defb;
}
if(w=="Spe"){
if(n==2){o=0.9;speb="-";}
if(n==7){o=0.9;speb="-";}
if(n==10){o=1.1;speb="+";}
if(n==11){o=1.1;speb="+";}
if(n==13){o=1.1;speb="+";}
if(n==14){o=1.1;speb="+";}
if(n==17){o=0.9;speb="-";}
if(n==22){o=0.9;speb="-";}
f.SpeBoost.value=speb;
}
if(w=="SpA"){
if(n==3){o=0.9;spab="-";}
if(n==8){o=0.9;spab="-";}
if(n==13){o=0.9;spab="-";}
if(n==15){o=1.1;spab="+";}
if(n==16){o=1.1;spab="+";}
if(n==17){o=1.1;spab="+";}
if(n==19){o=1.1;spab="+";}
if(n==23){o=0.9;spab="-";}
f.SpABoost.value=spab;
}
if(w=="SpD"){
if(n==4){o=0.9;spdb="-";}
if(n==9){o=0.9;spdb="-";}
if(n==14){o=0.9;spdb="-";}
if(n==19){o=0.9;spdb="-";}
if(n==20){o=1.1;spdb="+";}
if(n==21){o=1.1;spdb="+";}
if(n==22){o=1.1;spdb="+";}
if(n==23){o=1.1;spdb="+";}
f.SpDBoost.value=spdb;
}
return o;
}

function MT(n,W,T2){
var x=0;
var c=" ";
var o=" ";
o="Unknown";
x=n;
if(x<0){o="P=================/None";}
if(x>16){o="P=================/None";}
if(x==0){o="P=--=+-0+====-+=++/Fighting";}
if(x==1){o="P+===-+=-==+-=====/Flying";}
if(x==2){o="P==---=-0==+======/Poison";}
if(x==3){o="P=0+=+-=++=-+=====/Ground";}
if(x==4){o="P-+=-=+=-+====+===/Rock";}
if(x==5){o="P---===---=+=+==+=/Bug";}
if(x==6){o="P======+-====+==-0/Ghost";}
if(x==7){o="P====+==---=-=+===/Steel";}
if(x==8){o="S====-+=+--+==+-==/Fire";}
if(x==9){o="S===++===+--===-==/Water";}
if(x==10){o="S=--++-=--+-===-==/Grass";}
if(x==11){o="S=+=0=====+--==-==/Electric";}
if(x==12){o="S+=+====-====-==0=/Psychic";}
if(x==13){o="S=+=+===---+==-+==/Ice";}
if(x==14){o="S=======-======+==/Dragon";}
if(x==15){o="S-=====+-====+==-=/Dark";}
if(x==16){o="P====-=0-=========/Normal";}
if(x==16){o="P====-=0-=========/fairy";}
x=W;
if(x<0){x=1;}
if(x>3){x=1;}
if(x==0){o=o.substring(0,1);}
if(x==1){o=o.substring(19,o.length);}
if(x==2){o=o.substring(1,18);}
if(x==3){
x=T2;
if(x<0){x=16;}
if(x>16){x=16;}
c=o.substring((1+x),1);
if(c=="+"){o=2.0;}
if(c=="-"){o=-2.0;}
if(c=="="){o=1.0;}
if(c=="0"){o=0.0;}
}
return o;
}

function Gtest(){
var f=document.PokemonForm;
var pg=0;
var pd=" ";
var p=" ";
var gt=0;
gt=256;
pg=f.Species.options[f.Species.selectedIndex].value;
pd=PokeDex(pg);
p=FI(pd,"~",20);
if(p=="-1"){gt=128;}
if(p=="0"){gt=128;}
if(p=="12"){gt=30;}
if(p=="25"){gt=63;}
if(p=="50"){gt=126;}
if(p=="75"){gt=190;}
if(p=="100"){gt=128;}
return gt;
}

function FI(S,C,N){
var i=0;
var j=0;
var f=0;
var t=" ";
var o=" ";
j=0;
f=0;
o="";
for(i=0;i<(S.length);i++){
 t=S.substring(i,i+1);
 if(f==0){
  if(t==C){
   j+=1;
   if(j==N){
    f=1;
   }
  }
 }else{
  if(t==C){
   j=i;
   i=(S.length)+1;
  }else{
   o+=t;
  }
 }
}
return o;
}

function PokeDex(n){
var f=document.PokemonForm;
// info from http://pokefor.tk/
// 1   2   3    4  5  6  7  8   9   10 11 12 13 14  15  16  17   18
// ~Na#~Hn#~Name~HP~AT~DF~SP~SpA~SpD~HP~AT~DF~SP~SpA~SpD~Bex~Rare~
//     19      20     21      22        23
// Type~Ability~Gender~Max EXP~Egg Group~Held Item~
var O=" ";
O="~1~203~  ~45~49~49~45~65~65~0~0~0~0~1~0~64~45~10/2~39~12~3~9/11~0/0~";
if(n==1){O="~1~203~leaflet~45~49~49~45~65~65~0~0~0~0~1~0~64~45~10/2~39~12~3~9/11~0/0~";}
if(n==2){O="~2~204~grazepen~60~62~63~60~80~80~0~0~0~0~1~1~141~45~10/2~39~12~3~9/11~0/0~";}
if(n==3){O="~3~205~grassolot~80~82~83~80~100~100~0~0~0~0~2~1~208~45~10/2~39~12~3~9/11~0/0~";}
if(n==4){O="~4~206~Charmander~39~52~43~65~60~50~0~0~0~1~0~0~65~45~8~3~12~3~9/2~0/0~";}
if(n==5){O="~5~207~Charmeleon~58~64~58~80~80~65~0~0~0~1~1~0~142~45~8~3~12~3~9/2~0/0~";}
if(n==6){O="~6~208~Charizard~78~84~78~100~109~85~0~0~0~0~3~0~209~45~8/1~3~12~3~9/2~0/0~";}
if(n==7){O="~7~209~Squirtle~44~48~65~43~50~64~0~0~1~0~0~0~66~45~9~68~12~3~9/12~0/0~";}
if(n==8){O="~8~210~Wartortle~59~63~80~58~65~80~0~0~1~0~0~1~143~45~9~68~12~3~9/12~0/0~";}
if(n==9){O="~9~211~Blastoise~79~83~100~78~85~105~0~0~0~0~0~3~210~45~9~68~12~3~9/12~0/0~";}
if(n==10){O="~10~212~Caterpie~45~30~35~45~20~20~1~0~0~0~0~0~53~255~5~56~50~0~0~0/0~";}
if(n==11){O="~11~213~Metapod~50~20~55~30~25~25~0~0~2~0~0~0~72~120~5~54~50~0~0~0/0~";}
if(n==12){O="~12~214~Butterfree~60~45~50~70~80~80~0~0~0~0~2~1~160~45~5/1~9~50~0~0~0/0BC~";}
if(n==13){O="~13~215~Weedle~40~35~30~50~20~20~0~0~0~1~0~0~52~255~5/2~56~50~0~0~0/0~";}
if(n==14){O="~14~216~Kakuna~45~25~50~35~25~25~0~0~2~0~0~0~71~120~5/2~54~50~0~0~0/0~";}
if(n==15){O="~15~217~Beedrill~65~80~40~75~45~80~0~2~0~0~0~1~159~45~5/2~64~50~0~0~0/0D3~";}
if(n==16){O="~16~218~Pidgey~40~45~40~56~35~35~0~0~0~1~0~0~55~255~16/1~28~50~3~4~0/0~";}
if(n==17){O="~17~219~Pidgeotto~63~60~55~71~50~50~0~0~0~2~0~0~113~120~16/1~28~50~3~4~0/0~";}
if(n==18){O="~18~220~Pidgeot~83~80~75~91~70~70~0~0~0~3~0~0~172~45~16/1~28~50~3~4~0/0~";}
if(n==19){O="~19~221~Rattata~30~56~35~72~25~35~0~0~0~1~0~0~57~255~16~49/19~50~0~5~0/0~";}
if(n==20){O="~20~222~Raticate~55~81~60~97~50~70~0~0~0~2~0~0~116~127~16~49/19~50~0~5~0/0~";}
if(n==21){O="~21~223~Spearow~40~60~30~70~31~31~0~0~0~1~0~0~58~255~16/1~28~50~0~4~0/0~";}
if(n==22){O="~22~224~Fearow~65~90~65~100~61~61~0~0~0~2~0~0~162~90~16/1~28~50~0~4~0/0D2~";}
if(n==23){O="~23~225~Ekans~35~60~44~55~40~54~0~1~0~0~0~0~62~255~2~27/54~50~0~5/2~0/0~";}
if(n==24){O="~24~226~Arbok~60~85~69~80~65~79~0~2~0~0~0~0~147~90~2~27/54~50~0~5/2~0/0~";}
if(n==25){O="~25~156~Pikachu~35~55~30~90~50~40~0~0~0~2~0~0~82~190~11~59~50~0~5/3~08B/0CA~";}
if(n==26){O="~26~157~Raichu~60~90~55~100~90~80~0~0~0~3~0~0~122~75~11~59~50~0~5/3~0/08B~";}
if(n==27){O="~27~112~Sandshrew~50~75~85~40~20~30~0~0~1~0~0~0~93~255~3~51~50~0~5~0/0B7~";}
if(n==28){O="~28~113~Sandslash~75~100~110~65~45~55~0~0~2~0~0~0~163~90~3~51~50~0~5~0/0B7~";}
if(n==29){O="~29~227~Nidoran Female~55~47~52~41~40~40~1~0~0~0~0~0~59~235~2~43~100~3~9/5~0/0~";}
if(n==30){O="~30~228~Nidorina~70~62~67~56~55~55~2~0~0~0~0~0~117~120~2~43~100~3~10~0/0~";}
if(n==31){O="~31~229~Nidoqueen~90~82~87~76~75~85~3~0~0~0~0~0~194~45~2/3~43~100~3~10~0/0~";}
if(n==32){O="~32~230~Nidoran Male~46~57~40~50~40~40~0~1~0~0~0~0~60~235~2~43~0~3~9/5~0/0~";}
if(n==33){O="~33~231~Nidorino~61~72~57~65~55~55~0~2~0~0~0~0~118~120~2~43~0~3~9/5~0/0~";}
if(n==34){O="~34~232~Nidoking~81~92~77~85~85~75~0~3~0~0~0~0~195~45~2/3~43~0~3~9/5~0/0~";}
if(n==35){O="~35~233~Clefairy~70~45~48~35~60~65~2~0~0~0~0~0~68~150~16~10~75~4~3~08A/05E~";}
if(n==36){O="~36~234~Clefable~95~70~73~60~85~90~3~0~0~0~0~0~129~25~16~10~75~4~3~08A/05E~";}
if(n==37){O="~37~153~Vulpix~38~41~40~65~50~65~0~0~0~1~0~0~63~190~8~17~75~0~5~088/088~";}
if(n==38){O="~38~154~Ninetales~73~76~75~100~81~100~0~0~0~1~0~1~178~75~8~17~75~0~5~088/088~";}
if(n==39){O="~39~138~Jigglypuff~115~45~20~20~45~25~2~0~0~0~0~0~76~170~16~10~75~4~3~0/0~";}
if(n==40){O="~40~139~Wigglytuff~140~70~45~45~75~50~3~0~0~0~0~0~109~50~16~10~75~4~3~0/0~";}
if(n==41){O="~41~63~Zubat~40~45~35~55~30~40~0~0~0~1~0~0~54~255~2/1~25~50~0~4~0/0~";}
if(n==42){O="~42~64~Golbat~75~80~70~90~65~75~0~0~0~2~0~0~171~90~2/1~25~50~0~4~0/0~";}
if(n==43){O="~43~88~Oddish~45~50~55~30~75~65~0~0~0~0~1~0~78~255~10/2~5~50~3~11~0/0~";}
if(n==44){O="~44~89~Gloom~60~65~70~40~85~75~0~0~0~0~2~0~132~120~10/2~5~50~3~11~0/0~";}
if(n==45){O="~45~90~Vileplume~75~80~85~50~100~90~0~0~0~0~3~0~184~45~10/2~5~50~3~11~0/0~";}
if(n==46){O="~46~235~Paras~35~70~55~25~45~55~0~1~0~0~0~0~70~190~5/10~15~50~0~0/11~067/068~";}
if(n==47){O="~47~236~Parasect~60~95~80~30~60~80~0~2~1~0~0~0~128~75~5/10~15~50~0~0/11~067/068~";}
if(n==48){O="~48~237~Venonat~60~55~50~45~40~55~0~0~0~0~0~1~75~190~5/2~9~50~0~0~0/0~";}
if(n==49){O="~49~238~Venomoth~70~65~60~90~90~75~0~0~0~1~1~0~138~75~5/2~56~50~0~0~0/0~";}
if(n==50){O="~50~239~Diglett~10~55~25~95~35~45~0~0~0~1~0~0~81~255~3~51/1~50~0~5~0/0~";}
if(n==51){O="~51~240~Dugtrio~35~80~50~120~50~70~0~0~0~2~0~0~153~50~3~51/1~50~0~5~0/0~";}
if(n==52){O="~52~241~Meowth~40~45~35~90~40~40~0~0~0~1~0~0~69~255~16~41~50~0~5~0/0~";}
if(n==53){O="~53~242~Persian~65~70~60~115~65~65~0~0~0~2~0~0~148~90~16~31~50~0~5~0/0~";}
if(n==54){O="~54~158~Psyduck~50~52~48~55~65~50~0~0~0~0~1~0~80~190~9~11/7~50~0~12/5~0/0~";}
if(n==55){O="~55~159~Golduck~80~82~78~85~95~80~0~0~0~0~2~0~174~75~9~11/7~50~0~12/5~0/0~";}
if(n==56){O="~56~243~Mankey~40~80~35~70~35~45~0~1~0~0~0~0~74~190~0~71~50~0~5~0/0~";}
if(n==57){O="~57~244~Primeape~65~105~60~95~60~70~0~2~0~0~0~0~149~75~0~71~50~0~5~0/0~";}
if(n==58){O="~58~245~Growlithe~55~70~45~60~70~50~0~1~0~0~0~0~91~190~8~27/17~25~5~5~088/088~";}
if(n==59){O="~59~246~Arcanine~90~110~80~95~100~80~0~2~0~0~0~0~213~75~8~27/17~25~5~5~088/088~";}
if(n==60){O="~60~247~Poliwag~40~50~40~90~40~40~0~0~0~1~0~0~77~255~9~73/11~50~3~12~0/0~";}
if(n==61){O="~61~248~Poliwhirl~65~65~65~90~50~50~0~0~0~2~0~0~131~120~9~73/11~50~3~12~0/0BB~";}
if(n==62){O="~62~249~Poliwrath~90~85~95~70~70~90~0~0~3~0~0~0~185~45~9/0~73/11~50~3~12~0/0BB~";}
if(n==63){O="~63~39~Abra~25~20~15~90~105~55~0~0~0~0~1~0~73~200~12~66/25~25~3~6~0/0D6~";}
if(n==64){O="~64~40~Kadabra~40~35~30~105~120~70~0~0~0~0~2~0~145~100~12~66/25~25~3~6~0/0D6~";}
if(n==65){O="~65~41~Alakazam~55~50~45~120~135~85~0~0~0~0~3~0~186~50~12~66/25~25~3~6~0/0D6~";}
if(n==66){O="~66~73~Machop~70~80~50~35~35~35~0~1~0~0~0~0~88~180~0~19~25~3~6~0/0~";}
if(n==67){O="~67~74~Machoke~80~100~70~45~50~60~0~2~0~0~0~0~146~90~0~19~25~3~6~0/0~";}
if(n==68){O="~68~75~Machamp~90~130~80~55~65~85~0~3~0~0~0~0~193~45~0~19~25~3~6~0/0~";}
if(n==69){O="~69~250~Bellsprout~50~75~35~40~70~30~0~1~0~0~0~0~84~255~10/2~5~50~3~11~0/0~";}
if(n==70){O="~70~251~Weepinbell~65~90~50~55~85~45~0~2~0~0~0~0~151~120~10/2~5~50~3~11~0/0~";}
if(n==71){O="~71~252~Victreebel~80~105~65~70~100~60~0~3~0~0~0~0~191~45~10/2~5~50~3~11~0/0~";}
if(n==72){O="~72~66~Tentacool~40~40~35~70~50~100~0~0~0~0~0~1~105~190~9/2~6/32~50~5~14~0/0~";}
if(n==73){O="~73~67~Tentacruel~80~70~65~100~80~120~0~0~0~0~0~2~205~60~9/2~6/32~50~5~14~0/0~";}
if(n==74){O="~74~57~Geodude~40~80~100~20~30~30~0~0~1~0~0~0~86~255~4/3~47/62~50~3~8~0/0C3~";}
if(n==75){O="~75~58~Graveler~55~95~115~35~45~45~0~0~2~0~0~0~134~120~4/3~47/62~50~3~8~0/0C3~";}
if(n==76){O="~76~59~Golem~80~110~130~45~55~65~0~0~3~0~0~0~177~45~4/3~47/62~50~3~8~0/0C3~";}
if(n==77){O="~77~253~Ponyta~50~85~55~90~65~65~0~0~0~1~0~0~152~190~8~49/17~50~0~5~0/0~";}
if(n==78){O="~78~254~Rapidash~65~100~70~105~80~80~0~0~0~2~0~0~192~60~8~49/17~50~0~5~0/0~";}
if(n==79){O="~79~255~Slowpoke~90~65~65~15~40~40~1~0~0~0~0~0~99~190~9/12~38/40~50~0~9/12~0/0BB~";}
if(n==80){O="~80~256~Slowbro~95~75~110~30~100~80~0~0~2~0~0~0~164~75~9/12~38/40~50~0~9/12~0/0BB~";}
if(n==81){O="~81~82~Magnemite~25~35~70~45~95~55~0~0~0~0~1~0~89~190~11/7~34/62~-1~0~8~0/0C7~";}
if(n==82){O="~82~83~Magneton~50~60~95~70~120~70~0~0~0~0~2~0~161~60~11/7~34/62~-1~0~8~0/0C7~";}
if(n==83){O="~83~257~Farfetch'd~52~65~55~60~58~62~0~1~0~0~0~0~94~45~16/1~28/25~50~0~4/5~0/0E1~";}
if(n==84){O="~84~92~Doduo~35~85~45~75~35~35~0~1~0~0~0~0~96~190~16/1~49/14~50~0~4~0/0D2~";}
if(n==85){O="~85~93~Dodrio~60~110~70~100~60~60~0~2~0~0~0~0~158~45~16/1~49/14~50~0~4~0/0D2~";}
if(n==86){O="~86~258~Seel~65~45~55~45~45~70~0~0~0~0~0~1~100~190~9~67~50~0~12/5~0/0~";}
if(n==87){O="~87~259~Dewgong~90~70~80~70~70~95~0~0~0~0~0~2~176~75~9/13~67~50~0~12/5~0/0~";}
if(n==88){O="~88~106~Grimer~80~80~50~25~40~50~1~0~0~0~0~0~90~190~2~60/61~50~0~7~0/06E~";}
if(n==89){O="~89~107~Muk~105~105~75~50~65~100~1~1~0~0~0~0~157~75~2~60/61~50~0~7~0/06E~";}
if(n==90){O="~90~260~Shellder~30~65~100~40~45~25~0~0~1~0~0~0~97~190~9~55~50~5~14~06A/06B~";}
if(n==91){O="~91~261~Cloyster~50~95~180~70~85~45~0~0~2~0~0~0~203~60~9/13~55~50~5~14~06A/06B~";}
if(n==92){O="~92~262~Gastly~30~35~30~80~100~35~0~0~0~0~1~0~95~190~6/2~29~50~3~7~0/0~";}
if(n==93){O="~93~263~Haunter~45~50~45~95~115~55~0~0~0~0~2~0~126~90~6/2~29~50~3~7~0/0~";}
if(n==94){O="~94~264~Gengar~60~65~60~110~130~75~0~0~0~0~3~0~190~45~6/2~29~50~3~7~0/0~";}
if(n==95){O="~95~265~Onix~35~45~160~70~30~45~0~0~1~0~0~0~108~45~4/3~47/62~50~0~8~0/0~";}
if(n==96){O="~96~266~Drowzee~60~48~45~42~43~90~0~0~0~0~0~1~102~190~12~26~50~0~6~0/0~";}
if(n==97){O="~97~267~Hypno~85~73~70~67~73~115~0~0~0~0~0~2~165~75~12~26~50~0~6~0/0~";}
if(n==98){O="~98~268~Krabby~30~105~90~50~25~25~0~1~0~0~0~0~115~225~9~22/55~50~0~14~0/0~";}
if(n==99){O="~99~269~Kingler~55~130~115~75~50~50~0~2~0~0~0~0~206~60~9~22/55~50~0~14~0/0~";}
if(n==100){O="~100~84~Voltorb~40~30~50~100~55~55~0~0~0~1~0~0~103~190~11~57/59~-1~0~8~0/0~";}
if(n==101){O="~101~85~Electrode~60~50~70~140~80~80~0~0~0~2~0~0~150~60~11~57/59~-1~0~8~0/0~";}
if(n==102){O="~102~270~Exeggcute~60~40~80~40~60~45~0~0~1~0~0~0~98~90~10/12~5~50~5~11~0/0~";}
if(n==103){O="~103~271~Exeggutor~95~95~85~55~125~65~0~0~0~0~2~0~212~45~10/12~5~50~5~11~0/0~";}
if(n==104){O="~104~272~Cubone~50~50~95~35~40~50~0~0~1~0~0~0~87~190~3~47/30~50~0~9~0/0E0~";}
if(n==105){O="~105~273~Marowak~60~80~110~45~50~80~0~0~2~0~0~0~124~75~3~47/30~50~0~9~0/0E0~";}
if(n==106){O="~106~274~Hitmonlee~50~120~53~87~35~110~0~2~0~0~0~0~139~45~0~31~0~0~6~0/0~";}
if(n==107){O="~107~275~Hitmonchan~50~105~79~76~35~110~0~0~0~0~0~2~140~45~0~28~0~0~6~0/0~";}
if(n==108){O="~108~276~Lickitung~90~55~75~30~60~75~2~0~0~0~0~0~127~45~16~40/38~50~0~9~0/0~";}
if(n==109){O="~109~108~Koffing~40~65~95~35~60~45~0~0~1~0~0~0~114~190~2~29~50~0~7~0/0C2~";}
if(n==110){O="~110~109~Weezing~65~90~120~60~85~70~0~0~2~0~0~0~173~60~2~29~50~0~7~0/0C2~";}
if(n==111){O="~111~169~Rhyhorn~80~85~95~25~30~30~0~0~1~0~0~0~135~120~3/4~30/47~50~5~9/5~0/0~";}
if(n==112){O="~112~170~Rhydon~105~130~120~40~45~45~0~2~0~0~0~0~204~60~3/4~30/47~50~5~9/5~0/0~";}
if(n==113){O="~113~277~Chansey~250~5~5~50~35~105~2~0~0~0~0~0~255~30~16~37/52~100~4~3~0/0C5~";}
if(n==114){O="~114~278~Tangela~65~55~115~60~100~40~0~0~1~0~0~0~166~45~10~5~50~0~11~0/0~";}
if(n==115){O="~115~279~Kangaskhan~105~95~80~90~40~80~2~0~0~0~0~0~175~45~16~14~100~0~9~0/0~";}
if(n==116){O="~116~184~Horsea~30~40~70~60~70~25~0~0~0~0~1~0~83~225~9~65~50~0~12/2~0/0C9~";}
if(n==117){O="~117~185~Seadra~55~65~95~85~95~45~0~0~1~0~1~0~155~75~9~43~50~0~12/2~0/0C9~";}
if(n==118){O="~118~50~Goldeen~45~67~60~63~35~50~0~1~0~0~0~0~111~225~9~65/74~50~0~13~0/0~";}
if(n==119){O="~119~51~Seaking~80~92~65~68~65~80~0~2~0~0~0~0~170~60~9~65/74~50~0~13~0/0~";}
if(n==120){O="~120~143~Staryu~30~45~55~85~70~55~0~0~0~1~0~0~106~225~9~23/37~-1~5~14~06C/06D~";}
if(n==121){O="~121~144~Starmie~60~75~85~115~100~85~0~0~0~2~0~0~207~70~9/12~23/37~-1~5~14~06C/06D~";}
if(n==122){O="~122~280~Mr. Mime~40~45~65~90~100~120~0~0~0~0~0~2~136~45~12~57~50~0~6~0/08A~";}
if(n==123){O="~123~281~Scyther~70~110~80~105~55~80~0~1~0~0~0~0~187~45~5/1~64~50~0~0~0/0~";}
if(n==124){O="~124~282~Jynx~65~50~35~95~115~95~0~0~0~0~2~0~137~45~13/12~38~100~0~6~089/089~";}
if(n==125){O="~125~283~Electabuzz~65~83~57~105~95~85~0~0~0~2~0~0~156~45~11~59~25~0~6~0/0~";}
if(n==126){O="~126~284~Magmar~65~95~57~93~100~85~0~0~0~0~2~0~167~45~8~16~25~0~6~088/088~";}
if(n==127){O="~127~167~Pinsir~65~125~100~85~55~70~0~2~0~0~0~0~200~45~5~22~50~5~0~0/0~";}
if(n==128){O="~128~285~Tauros~75~100~95~110~40~70~0~1~0~1~0~0~211~45~16~27~0~5~5~0/0~";}
if(n==129){O="~129~52~Magikarp~20~10~55~80~15~20~0~0~0~1~0~0~20~255~9~65~50~5~13/2~0/0~";}
if(n==130){O="~130~53~Gyarados~95~125~79~81~60~100~0~2~0~0~0~0~214~45~9/1~27~50~5~13/2~0/0~";}
if(n==131){O="~131~286~Lapras~130~85~80~60~85~95~2~0~0~0~0~0~219~45~9/13~73/55~50~5~9/12~0/0~";}
if(n==132){O="~132~287~Ditto~48~48~48~48~48~48~1~0~0~0~0~0~61~35~16~31~-1~0~1~0/0DF~";}
if(n==133){O="~133~288~Eevee~55~55~50~55~45~65~0~0~0~0~0~1~92~45~16~49~12~0~5~0/0~";}
if(n==134){O="~134~289~Vaporeon~130~65~60~65~110~95~2~0~0~0~0~0~196~45~9~73~12~0~5~0/0~";}
if(n==135){O="~135~290~Jolteon~65~65~60~130~110~95~0~0~0~2~0~0~197~45~11~72~12~0~5~0/0~";}
if(n==136){O="~136~291~Flareon~65~130~60~65~95~110~0~2~0~0~0~0~198~45~8~17~12~0~5~0/0~";}
if(n==137){O="~137~292~Porygon~65~60~70~40~85~75~0~0~0~0~1~0~130~45~16~69~-1~0~8~0/0~";}
if(n==138){O="~138~293~Omanyte~35~40~100~35~90~55~0~0~1~0~0~0~120~45~4/9~65/55~12~0~12/14~0/0~";}
if(n==139){O="~139~294~Omastar~70~60~125~55~115~70~0~0~2~0~0~0~199~45~4/9~65/55~12~0~12/14~0/0~";}
if(n==140){O="~140~295~Kabuto~30~80~90~55~55~45~0~0~1~0~0~0~119~45~4/9~65/2~12~0~12/14~0/0~";}
if(n==141){O="~141~296~Kabutops~60~115~105~80~65~70~0~2~0~0~0~0~201~45~4/9~65/2~12~0~12/14~0/0~";}
if(n==142){O="~142~297~Aerodactyl~80~105~65~130~60~75~0~0~0~2~0~0~202~45~4/1~47/44~12~5~4~0/0~";}
if(n==143){O="~143~298~Snorlax~160~110~65~30~65~110~2~0~0~0~0~0~154~25~16~24/67~12~5~9~0C8/0C8~";}
if(n==144){O="~144~299~Articuno~90~85~100~85~95~125~0~0~0~0~0~3~215~3~13/1~44~-1~5~10~0/0~";}
if(n==145){O="~145~300~Zapdos~90~90~85~100~125~90~0~0~0~0~3~0~216~3~11/1~44~-1~5~10~0/0~";}
if(n==146){O="~146~301~Moltres~90~100~90~90~125~85~0~0~0~0~3~0~217~3~8/1~44~-1~5~10~0/0~";}
if(n==147){O="~147~302~Dratini~41~64~45~50~50~50~0~1~0~0~0~0~67~45~14~54~50~5~12/2~0/0C9~";}
if(n==148){O="~148~303~Dragonair~61~84~65~70~70~70~0~2~0~0~0~0~144~45~14~54~50~5~12/2~0/0C9~";}
if(n==149){O="~149~304~Dragonite~91~134~95~80~100~100~0~3~0~0~0~0~218~45~14/1~25~50~5~12/2~0/0C9~";}
if(n==150){O="~150~305~Mewtwo~106~110~90~130~154~90~0~0~0~0~3~0~220~3~12~44~-1~5~10~0/0~";}
if(n==151){O="~151~306~Mew~100~100~100~100~100~100~3~0~0~0~0~0~64~45~12~66~-1~3~10~08D/08D~";}
if(n==152){O="~152~307~Chikorita~45~49~65~45~49~65~0~0~0~0~0~1~64~45~10~39~12~3~9/11~0/0~";}
if(n==153){O="~153~308~Bayleef~60~62~80~60~63~80~0~0~1~0~0~1~141~45~10~39~12~3~9/11~0/0~";}
if(n==154){O="~154~309~Meganium~80~82~100~80~83~100~0~0~1~0~0~2~208~45~10~39~12~3~9/11~0/0~";}
if(n==155){O="~155~310~Cyndaquil~39~52~43~65~60~50~0~0~0~1~0~0~65~45~8~3~12~3~5~0/0~";}
if(n==156){O="~156~311~Quilava~58~64~58~80~80~65~0~0~0~1~1~0~142~45~8~3~12~3~5~0/0~";}
if(n==157){O="~157~312~Typhlosion~78~84~78~100~109~85~0~0~0~0~3~0~209~45~8~3~12~3~5~0/0~";}
if(n==158){O="~158~313~Totodile~50~65~64~43~44~48~0~1~0~0~0~0~66~45~9~68~12~3~9/12~0/0~";}
if(n==159){O="~159~314~Croconaw~65~80~80~58~59~63~0~1~1~0~0~0~143~45~9~68~12~3~9/12~0/0~";}
if(n==160){O="~160~315~Feraligatr~85~105~100~78~79~83~0~2~1~0~0~0~210~45~9~68~12~3~9/12~0/0~";}
if(n==161){O="~161~316~Sentret~35~46~34~20~35~45~0~1~0~0~0~0~57~255~16~49/28~50~0~5~0/08B~";}
if(n==162){O="~162~317~Furret~85~76~64~90~45~55~0~0~0~2~0~0~116~90~16~49/28~50~0~5~08B/08E~";}
if(n==163){O="~163~318~Hoothoot~60~30~30~50~36~56~1~0~0~0~0~0~58~255~16/1~26/28~50~0~4~0/0~";}
if(n==164){O="~164~319~Noctowl~100~50~50~70~76~96~2~0~0~0~0~0~162~90~16/1~26/28~50~0~4~0/0~";}
if(n==165){O="~165~320~Ledyba~40~20~30~55~40~80~0~0~0~0~0~1~54~255~5/1~64/14~50~4~0~0/0~";}
if(n==166){O="~166~321~Ledian~55~35~50~85~55~110~0~0~0~0~0~2~134~90~5/1~64/14~50~4~0~0/0~";}
if(n==167){O="~167~322~Spinarak~40~60~40~30~40~40~0~1~0~0~0~0~54~255~5/2~64/26~50~4~0~0/0~";}
if(n==168){O="~168~323~Ariados~70~90~70~40~60~60~0~2~0~0~0~0~134~90~5/2~64/26~50~4~0~0/0~";}
if(n==169){O="~169~65~Crobat~85~90~80~130~70~80~0~0~0~3~0~0~204~90~2/1~25~50~0~4~0/0~";}
if(n==170){O="~170~181~Chinchou~75~38~38~67~56~56~1~0~0~0~0~0~90~190~9/11~72/23~50~5~13~0/032~";}
if(n==171){O="~171~182~Lanturn~125~58~58~67~76~76~2~0~0~0~0~0~156~75~9/11~72/23~50~5~13~0/032~";}
if(n==172){O="~172~155~Pichu~20~40~15~60~35~35~0~0~0~1~0~0~42~190~11~59~50~0~10~0/08B~";}
if(n==173){O="~173~324~Cleffa~50~25~28~15~45~55~0~0~0~0~0~1~37~150~16~10~75~4~10~08A 05E~";}
if(n==174){O="~174~137~Igglybuff~90~30~15~15~40~20~1~0~0~0~0~0~39~170~16~10~75~4~10~0/0~";}
if(n==175){O="~175~325~Togepi~35~20~65~20~40~65~0~0~0~0~0~1~74~190~16~21/52~12~4~10~0/0~";}
if(n==176){O="~176~326~Togetic~55~40~85~40~80~105~0~0~0~0~0~2~114~75~16/1~21/52~12~4~4/3~0/0~";}
if(n==177){O="~177~162~Natu~40~50~45~70~70~45~0~0~0~0~1~0~73~190~12/1~66/14~50~0~4~0/0~";}
if(n==178){O="~178~163~Xatu~65~75~70~95~95~70~0~0~0~1~1~0~171~75~12/1~66/14~50~0~4~0/0~";}
if(n==179){O="~179~327~Mareep~55~40~40~35~65~45~0~0~0~0~1~0~59~235~11~59~50~3~9/5~0/0~";}
if(n==180){O="~180~328~Flaaffy~70~55~55~45~80~60~0~0~0~0~2~0~117~120~11~59~50~3~9/5~0/0~";}
if(n==181){O="~181~329~Ampharos~90~75~75~55~115~90~0~0~0~0~3~0~194~45~11~59~50~3~9/5~0/0~";}
if(n==182){O="~182~91~Bellossom~75~80~85~50~90~100~0~0~0~0~0~3~184~45~10~5~50~3~11~0/0~";}
if(n==183){O="~183~55~Marill~70~20~50~40~20~50~2~0~0~0~0~0~58~190~9~67/20~50~4~12/3~0/0~";}
if(n==184){O="~184~56~Azumarill~100~50~80~50~50~80~3~0~0~0~0~0~153~75~9~67/20~50~4~12/3~0/0~";}
if(n==185){O="~185~330~Sudowoodo~70~100~115~30~30~65~0~0~2~0~0~0~135~65~4~62/47~50~0~8~0/0~";}
if(n==186){O="~186~331~Politoed~90~75~75~70~90~100~0~0~0~0~0~3~185~45~9~73/11~50~3~12~0/0BB~";}
if(n==187){O="~187~332~Hoppip~35~35~40~50~35~55~0~0~0~0~0~1~74~255~10/1~5~50~3~3/11~0/0~";}
if(n==188){O="~188~333~Skiploom~55~45~50~80~45~65~0~0~0~2~0~0~136~120~10/1~5~50~3~3/11~0/0~";}
if(n==189){O="~189~334~Jumpluff~75~55~70~110~55~85~0~0~0~3~0~0~176~45~10/1~5~50~3~3/11~0/0~";}
if(n==190){O="~190~335~Aipom~55~70~55~85~40~55~0~0~0~1~0~0~94~45~16~49/41~50~4~5~0/0~";}
if(n==191){O="~191~336~Sunkern~30~30~30~30~30~30~0~0~0~0~1~0~52~235~10~5~50~3~11~0/0~";}
if(n==192){O="~192~337~Sunflora~75~75~55~30~105~85~0~0~0~0~2~0~146~120~10~5~50~3~11~0/0~";}
if(n==193){O="~193~338~Yanma~65~65~45~95~75~45~0~0~0~2~0~0~147~75~5/1~58/9~50~0~0~0/0~";}
if(n==194){O="~194~339~Wooper~55~45~45~15~25~25~1~0~0~0~0~0~52~255~9/3~11/73~50~0~12/5~0/0~";}
if(n==195){O="~195~340~Quagsire~95~85~85~35~65~65~2~0~0~0~0~0~137~90~9/3~11/73~50~0~12/5~0/0~";}
if(n==196){O="~196~341~Espeon~65~65~60~110~130~95~0~0~0~0~2~0~197~45~12~66~12~0~5~0/0~";}
if(n==197){O="~197~342~Umbreon~95~65~110~65~60~130~0~0~0~0~0~2~197~45~15~66~12~0~5~0/0~";}
if(n==198){O="~198~343~Murkrow~60~85~42~91~85~42~0~0~0~1~0~0~107~30~15/1~26~50~3~4~0/0~";}
if(n==199){O="~199~344~Slowking~95~75~80~30~100~110~0~0~0~0~0~3~164~70~9/12~38/40~50~0~9/12~0/0BB~";}
if(n==200){O="~200~345~Misdreavus~60~60~60~85~85~85~0~0~0~0~1~1~147~45~6~29~50~4~7~0/0D5~";}
if(n==201){O="~201~346~Unown~48~72~48~48~72~48~0~1~0~0~1~0~61~225~12~29~-1~0~10~0/0~";}
if(n==202){O="~202~161~Wobbuffet~190~33~58~33~33~58~2~0~0~0~0~0~177~45~12~53~50~0~7~0/0~";}
if(n==203){O="~203~164~Girafarig~70~80~65~85~90~65~0~0~0~0~2~0~149~60~16/12~25/14~50~0~5~0/08C~";}
if(n==204){O="~204~347~Pineco~50~65~90~15~35~35~0~0~1~0~0~0~60~190~5~62~50~0~0~0/0~";}
if(n==205){O="~205~348~Forretress~75~90~140~40~60~60~0~0~2~0~0~0~118~75~5/7~62~50~0~0~0/0~";}
if(n==206){O="~206~349~Dunsparce~100~70~70~45~65~65~1~0~0~0~0~0~75~190~16~52/49~50~0~5~0/0~";}
if(n==207){O="~207~350~Gligar~65~75~105~85~35~65~0~0~1~0~0~0~108~60~3/1~22/51~50~3~0~0/0~";}
if(n==208){O="~208~351~Steelix~75~85~200~30~55~65~0~0~2~0~0~0~196~25~7/3~47/62~50~0~8~0/0C7~";}
if(n==209){O="~209~352~Snubbull~60~80~50~30~40~40~0~1~0~0~0~0~63~190~16~27/49~75~4~5/3~0/0~";}
if(n==210){O="~210~353~Granbull~90~120~75~45~60~60~0~2~0~0~0~0~178~75~16~27~75~4~5/3~0/0~";}
if(n==211){O="~211~354~Qwilfish~65~95~75~85~55~55~0~1~0~0~0~0~100~45~9/2~43/65~50~0~13~0/0~";}
if(n==212){O="~212~355~Scizor~70~130~100~65~55~80~0~2~0~0~0~0~200~25~5/7~64~50~0~0~0/0~";}
if(n==213){O="~213~356~Shuckle~20~10~230~5~10~230~0~0~1~0~0~1~80~190~5/4~62~50~3~0~08B/08B~";}
if(n==214){O="~214~168~Heracross~80~125~75~85~40~95~0~2~0~0~0~0~200~45~5/0~64/19~50~5~0~0/0~";}
if(n==215){O="~215~357~Sneasel~55~95~55~115~35~75~0~0~0~1~0~0~132~60~15/13~25/28~50~3~5~0/0B7~";}
if(n==216){O="~216~358~Teddiursa~60~80~50~40~50~50~0~1~0~0~0~0~124~120~16~41~50~0~5~0/0~";}
if(n==217){O="~217~359~Ursaring~90~130~75~55~75~75~0~2~0~0~0~0~189~60~16~19~50~0~5~0/0~";}
if(n==218){O="~218~103~Slugma~40~40~40~20~70~40~0~0~0~0~1~0~78~190~8~33/16~50~0~7~0/0~";}
if(n==219){O="~219~104~Magcargo~50~50~120~30~80~80~0~0~2~0~0~0~154~75~8/4~33/16~50~0~7~0/0~";}
if(n==220){O="~220~360~Swinub~50~50~40~50~30~30~0~1~0~0~0~0~78~225~13/3~38~50~5~5~0/0~";}
if(n==221){O="~221~361~Piloswine~100~100~80~50~60~60~1~1~0~0~0~0~160~75~13/3~38~50~5~5~0/0~";}
if(n==222){O="~222~180~Corsola~55~55~85~35~65~85~0~0~1~0~0~1~113~60~9/4~21/37~75~4~12/14~0/030~";}
if(n==223){O="~223~362~Remoraid~35~65~35~65~65~35~0~0~0~0~1~0~78~190~9~21~50~0~12/13~0/0~";}
if(n==224){O="~224~363~Octillery~75~105~75~45~105~75~0~1~0~0~1~0~164~75~9~63~50~0~12/13~0/0~";}
if(n==225){O="~225~364~Delibird~45~55~45~75~65~45~0~0~0~1~0~0~183~45~13/1~71/21~50~4~12/5~0/0~";}
if(n==226){O="~226~365~Mantine~65~40~70~70~80~140~0~0~0~0~0~2~168~25~9/1~65/73~50~5~12~0/0~";}
if(n==227){O="~227~115~Skarmory~65~80~140~70~40~70~0~0~2~0~0~0~168~25~7/1~28/62~50~5~4~0/0~";}
if(n==228){O="~228~366~Houndour~45~60~30~65~80~50~0~0~0~0~1~0~114~120~15/8~14/17~50~5~5~0/0~";}
if(n==229){O="~229~367~Houndoom~75~90~50~95~110~80~0~0~0~0~2~0~204~45~15/8~14/17~50~5~5~0/0~";}
if(n==230){O="~230~186~Kingdra~75~95~95~85~95~95~0~1~0~0~1~1~207~45~9/14~65~50~0~12/2~0/0C9~";}
if(n==231){O="~231~165~Phanpy~90~60~60~40~40~40~1~0~0~0~0~0~124~120~3~41~50~0~5~0/0~";}
if(n==232){O="~232~166~Donphan~90~120~120~50~60~60~0~1~1~0~0~0~189~60~3~62~50~0~5~0/0~";}
if(n==233){O="~233~368~Porygon2~85~80~90~60~105~95~0~0~0~0~2~0~180~45~16~69~-1~0~8~0/0~";}
if(n==234){O="~234~369~Stantler~73~95~62~85~85~65~0~1~0~0~0~0~165~45~16~27~50~5~5~0/0~";}
if(n==235){O="~235~370~Smeargle~55~20~35~75~20~45~0~0~0~1~0~0~106~45~16~40~50~4~5~0/0~";}
if(n==236){O="~236~371~Tyrogue~35~35~35~35~35~35~0~1~0~0~0~0~91~75~0~19~0~0~10~0/0~";}
if(n==237){O="~237~372~Hitmontop~50~95~95~70~35~110~0~0~0~0~0~2~138~45~0~27~0~0~6~0/0~";}
if(n==238){O="~238~373~Smoochum~45~30~15~65~85~65~0~0~0~0~1~0~87~45~13/12~38~100~0~10~089/089~";}
if(n==239){O="~239~374~Elekid~45~63~37~95~65~55~0~0~0~1~0~0~106~45~11~59~25~0~10~0/0~";}
if(n==240){O="~240~375~Magby~45~75~37~83~70~55~0~0~0~1~0~0~117~45~8~16~25~0~10~088/088~";}
if(n==241){O="~241~376~Miltank~95~80~105~100~40~70~0~0~2~0~0~0~200~45~16~67~100~5~5~01D/01D~";}
if(n==242){O="~242~377~Blissey~255~10~10~55~75~135~2~0~0~0~0~0~255~30~16~37/52~100~4~3~0/0C5~";}
if(n==243){O="~243~378~Raikou~90~85~75~115~115~100~0~0~0~2~1~0~216~3~11~44~-1~5~10~0/0~";}
if(n==244){O="~244~379~Entei~115~115~85~100~90~75~1~2~0~0~0~0~217~3~8~44~-1~5~10~0/0~";}
if(n==245){O="~245~380~Suicune~100~75~115~85~90~115~0~0~1~0~0~2~215~3~9~44~-1~5~10~0/0~";}
if(n==246){O="~246~381~Larvitar~50~64~50~41~45~50~0~1~0~0~0~0~67~45~4/3~19~50~5~9~0/0~";}
if(n==247){O="~247~382~Pupitar~70~84~70~51~65~70~0~2~0~0~0~0~144~45~4/3~54~50~5~9~0/0~";}
if(n==248){O="~248~383~Tyranitar~100~134~110~61~95~100~0~3~0~0~0~0~218~45~4/15~50~50~5~9~0/0~";}
if(n==249){O="~249~384~Lugia~106~90~130~110~90~154~0~0~0~0~0~3~220~3~12/1~44~-1~5~10~0/0~";}
if(n==250){O="~250~385~Ho-oh~106~130~90~90~110~154~0~0~0~0~0~3~220~3~8/1~44~-1~5~10~02D/02D~";}
if(n==251){O="~251~386~Celebi~100~100~100~100~100~100~3~0~0~0~0~0~64~45~12/10~37~-1~3~10~08D/08D~";}
if(n==277){O="~252~1~Treecko~40~45~35~70~65~55~0~0~0~1~0~0~65~45~10~39~12~3~9/2~0/0~";}
if(n==278){O="~253~2~Grovyle~50~65~45~95~85~65~0~0~0~2~0~0~141~45~10~39~12~3~9/2~0/0~";}
if(n==279){O="~254~3~Sceptile~70~85~65~120~105~85~0~0~0~3~0~0~208~45~10~39~12~3~9/2~0/0~";}
if(n==280){O="~255~4~Torchic~45~60~40~45~70~50~0~0~0~0~1~0~65~45~8~3~12~3~5~0/0~";}
if(n==281){O="~256~5~Combusken~60~85~60~55~85~60~0~1~0~0~1~0~142~45~8/0~3~12~3~5~0/0~";}
if(n==282){O="~257~6~Blaziken~80~120~70~80~110~70~0~3~0~0~0~0~209~45~8/0~3~12~3~5~0/0~";}
if(n==283){O="~258~7~Mudkip~50~70~50~40~50~50~0~1~0~0~0~0~65~45~9~68~12~3~9/12~0/0~";}
if(n==284){O="~259~8~Marshtomp~70~85~70~50~60~70~0~2~0~0~0~0~143~45~9/3~68~12~3~9/12~0/0~";}
if(n==285){O="~260~9~Swampert~100~110~90~60~85~90~0~3~0~0~0~0~210~45~9/3~68~12~3~9/12~0/0~";}
if(n==286){O="~261~10~Poochyena~35~55~35~35~30~30~0~1~0~0~0~0~55~255~15~49~50~0~5~0/087~";}
if(n==287){O="~262~11~Mightyena~70~90~70~70~60~60~0~2~0~0~0~0~128~127~15~27~50~0~5~0/087~";}
if(n==288){O="~263~12~Zigzagoon~38~30~41~60~30~41~0~0~0~1~0~0~60~255~16~41~50~0~5~0/08B~";}
if(n==289){O="~264~13~Linoone~78~70~61~100~50~61~0~0~0~2~0~0~128~90~16~41~50~0~5~08B/08E~";}
if(n==290){O="~265~14~Wurmple~45~45~35~20~20~30~1~0~0~0~0~0~54~255~5~56~50~0~0~0/0~";}
if(n==291){O="~266~15~Silcoon~50~35~55~15~25~25~0~0~2~0~0~0~71~120~5~54~50~0~0~0/0~";}
if(n==292){O="~267~16~Beautifly~60~70~50~65~90~50~0~0~0~0~3~0~161~45~5/1~64~50~0~0~0/0BC~";}
if(n==293){O="~268~17~Cascoon~50~35~55~15~25~25~0~0~2~0~0~0~72~120~5~54~50~0~0~0/0~";}
if(n==294){O="~269~18~Dustox~60~50~70~65~50~90~0~0~0~0~0~3~160~45~5/2~56~50~0~0~0/0BC~";}
if(n==295){O="~270~19~Lotad~40~30~30~30~40~50~0~0~0~0~0~1~74~255~9/10~65/46~50~3~12/11~0/0~";}
if(n==296){O="~271~20~Lombre~60~50~50~50~60~70~0~0~0~0~0~2~141~120~9/10~65/46~50~3~12/11~0/0~";}
if(n==297){O="~272~21~Ludicolo~80~70~70~70~90~100~0~0~0~0~0~3~181~45~9/10~65/46~50~3~12/11~0/0~";}
if(n==298){O="~273~22~Seedot~40~40~50~30~30~30~0~0~1~0~0~0~74~255~10~5/14~50~3~5/11~0/0~";}
if(n==299){O="~274~23~Nuzleaf~70~70~40~60~60~40~0~2~0~0~0~0~141~45~10/15~5/14~50~3~5/11~0/0~";}
if(n==300){O="~275~24~Shiftry~90~100~60~80~90~60~0~3~0~0~0~0~181~45~10/15~5/14~50~3~5/11~0/0~";}
if(n==301){O="~290~42~Nincada~31~45~90~40~30~30~0~0~1~0~0~0~65~255~5/3~9~50~1~0~0/0~";}
if(n==302){O="~291~43~Ninjask~61~90~45~160~50~50~0~0~0~2~0~0~155~120~5/1~58~50~1~0~0/0~";}
if(n==303){O="~292~44~Shedinja~1~90~45~40~30~30~2~0~0~0~0~0~95~45~5/6~76~-1~1~8~0/0~";}
if(n==304){O="~276~25~Taillow~40~55~30~85~30~30~0~0~0~1~0~0~59~200~16/1~19~50~3~4~0/0~";}
if(n==305){O="~277~26~Swellow~60~85~60~125~50~50~0~0~0~2~0~0~162~45~16/1~19~50~3~4~0/0~";}
if(n==306){O="~285~34~Shroomish~60~40~60~35~40~60~1~0~0~0~0~0~65~255~10~15~50~2~3/11~0/0~";}
if(n==307){O="~286~35~Breloom~60~130~80~70~60~60~0~2~0~0~0~0~165~90~10/0~15~50~2~3/11~0/0~";}
if(n==308){O="~327~114~Spinda~60~60~60~60~60~60~0~0~0~0~1~0~85~255~16~40~50~4~5/6~0/086~";}
if(n==309){O="~278~27~Wingull~40~30~30~85~55~30~0~0~0~1~0~0~64~190~9/1~28~50~0~12/4~0/0~";}
if(n==310){O="~279~28~Pelipper~60~50~100~65~85~70~0~0~2~0~0~0~164~45~9/1~28~50~0~12/4~0/0~";}
if(n==311){O="~283~32~Surskit~40~30~32~65~50~52~0~0~0~1~0~0~63~200~5/9~65~50~0~12/0~0/0~";}
if(n==312){O="~284~33~Masquerain~70~60~62~60~80~82~0~0~0~0~1~1~128~75~5/1~27~50~0~12/0~0/0BC~";}
if(n==313){O="~320~99~Wailmer~130~70~35~60~70~35~1~0~0~0~0~0~137~125~9~74/38~50~2~5/13~0/0~";}
if(n==314){O="~321~100~Wailord~170~90~45~60~90~45~2~0~0~0~0~0~206~60~9~74/38~50~2~5/13~0/0~";}
if(n==315){O="~300~61~Skitty~50~45~45~50~35~35~0~0~0~1~0~0~65~255~16~10~75~4~5/3~0/08A~";}
if(n==316){O="~301~62~Delcatty~70~65~65~70~55~55~1~0~0~1~0~0~138~60~16~10~75~4~5/3~0/08A~";}
if(n==317){O="~352~145~Kecleon~60~90~70~40~60~120~0~0~0~0~0~1~132~200~16~8~50~3~5~0/08C~";}
if(n==318){O="~343~131~Baltoy~40~40~55~55~40~70~0~0~0~0~0~1~58~255~3/12~29~-1~0~8~0/0~";}
if(n==319){O="~344~132~Claydol~60~70~105~75~70~120~0~0~0~0~0~2~189~90~3/12~29~-1~0~8~0/0~";}
if(n==320){O="~299~60~Nosepass~30~45~135~30~45~90~0~0~1~0~0~0~108~255~4~62/34~50~0~8~0/0~";}
if(n==321){O="~324~105~Torkoal~70~85~140~20~85~70~0~0~2~0~0~0~161~90~8~75~50~0~5~0/0~";}
if(n==322){O="~302~68~Sableye~50~75~75~50~65~65~0~1~1~0~0~0~98~45~15/6~28~50~3~6~0/0~";}
if(n==323){O="~339~127~Barboach~50~48~43~60~46~41~1~0~0~0~0~0~92~190~9/3~38~50~0~13~0/0~";}
if(n==324){O="~340~128~Whiscash~110~78~73~60~76~71~2~0~0~0~0~0~158~75~9/3~38~50~0~13~0/0~";}
if(n==325){O="~370~183~Luvdisc~43~30~55~97~40~65~0~0~0~1~0~0~110~225~9~65~75~4~13~06F/0~";}
if(n==326){O="~341~129~Corphish~43~80~65~35~50~35~0~1~0~0~0~0~111~205~9~22/55~50~2~12/14~0/0~";}
if(n==327){O="~342~130~Crawdaunt~63~120~85~55~90~55~0~2~0~0~0~0~161~155~9/15~22/55~50~2~12/14~0/0~";}
if(n==328){O="~349~140~Feebas~20~15~20~80~10~55~0~0~0~1~0~0~61~255~9~65~50~1~12/2~0/0~";}
if(n==329){O="~350~141~Milotic~95~60~79~81~100~125~0~0~0~0~0~2~213~60~9~35~50~1~12/2~0/0~";}
if(n==330){O="~318~97~Carvanha~45~90~20~65~65~20~0~1~0~0~0~0~88~225~9/15~48~50~5~13~0/0~";}
if(n==331){O="~319~98~Sharpedo~70~120~40~95~95~40~0~2~0~0~0~0~175~60~9/15~48~50~5~13~0/0~";}
if(n==332){O="~328~116~Trapinch~45~100~45~10~45~45~0~1~0~0~0~0~73~255~3~22/1~50~3~0~0/0CB~";}
if(n==333){O="~329~117~Vibrava~50~70~50~70~50~50~0~1~0~1~0~0~126~120~3/14~29~50~3~0~0/0~";}
if(n==334){O="~330~118~Flygon~80~100~80~100~80~80~0~1~0~2~0~0~197~45~3/14~29~50~3~0~0/0~";}
if(n==335){O="~296~48~Makuhita~72~60~30~25~20~30~1~0~0~0~0~0~87~180~0~67/19~25~2~6~0/0~";}
if(n==336){O="~297~49~Hariyama~144~120~60~50~40~60~2~0~0~0~0~0~184~200~0~67/19~25~2~6~0/0BB~";}
if(n==337){O="~309~78~Electrike~40~45~40~65~65~40~0~0~0~1~0~0~104~120~11~59/30~50~5~5~0/0~";}
if(n==338){O="~310~79~Manectric~70~75~60~105~105~60~0~0~0~2~0~0~168~45~11~59/30~50~5~5~0/0~";}
if(n==339){O="~322~101~Numel~60~60~40~35~65~45~0~0~0~0~1~0~88~255~8/3~38~50~0~5~088/088~";}
if(n==340){O="~323~102~Camerupt~70~100~70~40~105~75~0~1~0~0~1~0~175~150~8/3~33~50~0~5~088/088~";}
if(n==341){O="~363~173~Spheal~70~40~50~25~55~50~1~0~0~0~0~0~75~255~13/9~67~50~3~12/5~0/0~";}
if(n==342){O="~364~174~Sealeo~90~60~70~45~75~70~2~0~0~0~0~0~128~120~13/9~67~50~3~12/5~0/0~";}
if(n==343){O="~365~175~Walrein~110~80~90~65~95~90~3~0~0~0~0~0~192~45~13/9~67~50~3~12/5~0/0~";}
if(n==344){O="~331~119~Cacnea~50~85~40~35~85~40~0~0~0~0~1~0~97~190~10~51~50~3~11/6~0/0D3~";}
if(n==345){O="~332~120~Cacturne~70~115~60~55~115~60~0~1~0~0~1~0~177~60~10/15~51~50~3~11/6~0/0D3~";}
if(n==346){O="~361~171~Snorunt~50~50~50~50~50~50~1~0~0~0~0~0~74~190~13~25~50~0~3/8~0/0~";}
if(n==347){O="~362~172~Glalie~80~80~80~80~80~80~2~0~0~0~0~0~187~75~13~25~50~0~3/8~0/0D4~";}
if(n==348){O="~337~125~Lunatone~70~55~65~70~95~85~0~0~0~0~2~0~150~45~4/12~29~-1~4~8~0/05E~";}
if(n==349){O="~338~126~Solrock~70~95~85~70~55~65~0~2~0~0~0~0~150~45~4/12~29~-1~4~8~0/05D~";}
if(n==350){O="~298~54~Azurill~50~20~40~20~20~40~1~0~0~0~0~0~33~150~16~67/20~75~4~10~0/0~";}
if(n==351){O="~325~110~Spoink~60~25~35~60~70~80~0~0~0~0~0~1~89~255~12~67/40~50~4~5~0/0~";}
if(n==352){O="~326~111~Grumpig~80~45~65~80~90~110~0~0~0~0~0~2~164~60~12~67/40~50~4~5~0/0~";}
if(n==353){O="~311~80~Plusle~60~50~40~95~85~75~0~0~0~1~0~0~120~200~11~42~50~0~3~0/0~";}
if(n==354){O="~312~81~Minun~60~40~50~95~75~85~0~0~0~1~0~0~120~200~11~36~50~0~3~0/0~";}
if(n==355){O="~303~69~Mawile~50~85~85~50~55~55~0~1~1~0~0~0~98~45~7~22/27~50~4~5/3~0/0~";}
if(n==356){O="~307~76~Meditite~30~40~55~60~40~55~0~0~0~1~0~0~91~180~0/12~45~50~0~6~0/0~";}
if(n==357){O="~308~77~Medicham~60~60~75~80~60~75~0~0~0~2~0~0~153~90~0/12~45~50~0~6~0/0~";}
if(n==358){O="~333~121~Swablu~45~40~60~50~40~75~0~0~0~0~0~1~74~255~16/1~37~50~1~4/2~0/0~";}
if(n==359){O="~334~122~Altaria~75~70~90~80~70~105~0~0~0~0~0~2~188~45~14/1~37~50~1~4/2~0/0~";}
if(n==360){O="~360~160~Wynaut~95~23~48~23~23~48~1~0~0~0~0~0~44~125~12~53~50~0~10~0/0~";}
if(n==361){O="~355~148~Duskull~20~40~90~25~30~90~0~0~1~0~0~1~97~190~6~29~50~4~7~0/0D5~";}
if(n==362){O="~356~149~Dusclops~40~70~130~25~60~130~0~0~1~0~0~2~179~90~6~44~50~4~7~0/0D5~";}
if(n==363){O="~315~94~Roselia~50~60~45~65~100~80~0~0~0~0~1~0~152~150~10/2~37/43~50~3~3/11~0/0D3~";}
if(n==364){O="~287~36~Slakoth~60~60~60~30~35~35~1~0~0~0~0~0~83~255~16~70~50~5~5~0/0~";}
if(n==365){O="~288~37~Vigoroth~80~80~80~90~55~55~0~0~0~2~0~0~126~120~16~71~50~5~5~0/0~";}
if(n==366){O="~289~38~Slaking~150~160~100~100~95~65~3~0~0~0~0~0~210~45~16~70~50~5~5~0/0~";}
if(n==367){O="~316~95~Gulpin~70~43~53~40~43~53~1~0~0~0~0~0~75~225~2~32/61~50~2~7~0/06B~";}
if(n==368){O="~317~96~Swalot~100~73~83~55~73~83~2~0~0~0~0~0~168~75~2~32/61~50~2~7~0/06B~";}
if(n==369){O="~357~150~Tropius~99~68~83~51~72~87~2~0~0~0~0~0~169~200~10/1~5~50~5~9/11~0/0~";}
if(n==370){O="~293~45~Whismur~64~51~23~28~51~23~1~0~0~0~0~0~68~190~16~57~50~3~9/5~0/086~";}
if(n==371){O="~294~46~Loudred~84~71~43~48~71~43~2~0~0~0~0~0~126~120~16~57~50~3~9/5~0/086~";}
if(n==372){O="~295~47~Exploud~104~91~63~68~91~63~3~0~0~0~0~0~184~45~16~57~50~3~9/5~0/086~";}
if(n==373){O="~366~176~Clamperl~35~64~85~32~74~55~0~0~1~0~0~0~142~255~9~55~50~1~12~0/031~";}
if(n==374){O="~367~177~Huntail~55~104~105~52~94~75~0~1~1~0~0~0~178~60~9~65~50~1~12~0/0~";}
if(n==375){O="~368~178~Gorebyss~55~84~105~52~114~75~0~0~0~0~2~0~178~60~9~65~50~1~12~0/0~";}
if(n==376){O="~359~152~Absol~65~130~60~75~75~60~0~2~0~0~0~0~174~30~15~44~50~3~5~0/0~";}
if(n==377){O="~353~146~Shuppet~44~75~35~45~63~33~0~1~0~0~0~0~97~225~6~26~50~4~7~0/0D5~";}
if(n==378){O="~354~147~Banette~64~115~65~65~83~63~0~2~0~0~0~0~179~45~6~26~50~4~7~0/0D5~";}
if(n==379){O="~336~124~Seviper~73~100~60~65~100~60~0~1~0~0~1~0~165~90~2~54~50~2~5/2~0/0~";}
if(n==380){O="~335~123~Zangoose~73~115~60~90~60~60~0~2~0~0~0~0~165~90~16~24~50~1~5~0/0~";}
if(n==381){O="~369~179~Relicanth~100~90~130~55~45~65~1~0~1~0~0~0~198~25~9/4~65/47~12~5~12/13~0/033~";}
if(n==382){O="~304~70~Aron~50~70~100~30~40~40~0~0~1~0~0~0~96~180~7/4~62/47~50~5~9~0/0CC~";}
if(n==383){O="~305~71~Lairon~60~90~140~40~50~50~0~0~2~0~0~0~152~90~7/4~62/47~50~5~9~0/0CC~";}
if(n==384){O="~306~72~Aggron~70~110~180~50~60~60~0~0~3~0~0~0~205~45~7/4~62/47~50~5~9~0/0CC~";}
if(n==385){O="~351~142~Castform~70~70~70~70~70~70~1~0~0~0~0~0~145~45~16~18~50~0~3/7~0D1/0D1~";}
if(n==386){O="~313~86~Volbeat~65~73~55~85~47~75~0~0~0~1~0~0~146~150~5~23/64~0~1~0/6~0/0~";}
if(n==387){O="~314~87~Illumise~65~47~55~85~73~75~0~0~0~1~0~0~146~150~5~38~100~2~0/6~0/0~";}
if(n==388){O="~345~133~Lileep~66~41~77~23~61~87~0~0~0~0~0~1~121~45~4/10~63~12~1~14~0/0~";}
if(n==389){O="~346~134~Cradily~86~81~97~43~81~107~0~0~0~0~0~2~201~45~4/10~63~12~1~14~0/0~";}
if(n==390){O="~347~135~Anorith~45~95~50~75~40~50~0~1~0~0~0~0~119~45~4/5~2~12~1~14~0/0~";}
if(n==391){O="~348~136~Armaldo~75~125~100~45~70~80~0~2~0~0~0~0~200~45~4/5~2~12~1~14~0/0~";}
if(n==392){O="~280~29~Ralts~28~25~25~40~45~35~0~0~0~0~1~0~70~235~12~66/69~50~5~7~0/0~";}
if(n==393){O="~281~30~Kirlia~38~35~35~50~65~55~0~0~0~0~2~0~140~120~12~66/69~50~5~7~0/0~";}
if(n==394){O="~282~31~Gardevoir~68~65~65~80~125~115~0~0~0~0~3~0~208~45~12~66/69~50~5~7~0/0~";}
if(n==395){O="~371~187~Bagon~45~75~60~50~40~30~0~1~0~0~0~0~89~45~14~47~50~5~2~0/0C9~";}
if(n==396){O="~372~188~Shelgon~65~95~100~50~60~50~0~0~2~0~0~0~144~45~14~47~50~5~2~0/0C9~";}
if(n==397){O="~373~189~Salamence~95~135~80~100~110~80~0~3~0~0~0~0~218~45~14/1~27~50~5~2~0/0C9~";}
if(n==398){O="~374~190~Beldum~40~55~80~30~35~60~0~0~1~0~0~0~103~3~7/12~6~-1~5~8~0/0C7~";}
if(n==399){O="~375~191~Metang~60~75~100~50~55~80~0~0~2~0~0~0~153~3~7/12~6~-1~5~8~0/0C7~";}
if(n==400){O="~376~192~Metagross~80~135~130~70~95~90~0~0~3~0~0~0~210~3~7/12~6~-1~5~8~0/0C7~";}
if(n==401){O="~377~193~Regirock~80~100~200~50~50~100~0~0~3~0~0~0~217~3~4~6~-1~5~10~0/0~";}
if(n==402){O="~378~194~Regice~80~50~100~50~100~200~0~0~0~0~0~3~216~3~13~6~-1~5~10~0/0~";}
if(n==403){O="~379~195~Registeel~80~75~150~50~75~150~0~0~2~0~0~1~215~3~7~6~-1~5~10~0/0~";}
if(n==404){O="~382~198~Kyogre~100~100~90~90~150~140~0~0~0~0~3~0~218~5~9~12~-1~5~10~0/0~";}
if(n==405){O="~383~199~Groudon~100~150~140~90~100~90~0~3~0~0~0~0~218~5~3~13~-1~5~10~0/0~";}
if(n==406){O="~384~200~Rayquaza~105~150~90~95~150~90~0~2~0~0~1~0~220~3~14/1~0~-1~5~10~0/0~";}
if(n==407){O="~380~196~Latias~80~80~90~110~110~130~0~0~0~0~0~3~211~3~14/12~29~100~5~10~0/0~";}
if(n==408){O="~381~197~Latios~80~90~80~110~130~110~0~0~0~0~3~0~211~3~14/12~29~0~5~10~0/0~";}
if(n==409){O="~385~201~Jirachi~100~100~100~100~100~100~3~0~0~0~0~0~215~3~7/12~52~-1~5~10~06D/06D~";}
if(n==410){
  O="~386~202~Deoxys~50~150~50~150~150~50~0~1~0~1~1~0~215~3~12~44~-1~5~10~0/0~";
  if(f.Game.selectedIndex==0){O="~386~202~Deoxys~50~95~90~180~95~90~0~1~0~1~1~0~215~3~12~44~-1~5~10~0/0~";}
  if(f.Game.selectedIndex==1 || f.Game.selectedIndex==3){O="~386~202~Deoxys~50~180~20~150~180~20~0~1~0~1~1~0~215~3~12~44~-1~5~10~0/0~";}
  if(f.Game.selectedIndex==2 || f.Game.selectedIndex==4){O="~386~202~Deoxys~50~70~160~90~70~160~0~1~0~1~1~0~215~3~12~44~-1~5~10~0/0~";}
}
if(n==411){O="~358~151~Chimecho~65~50~70~65~95~80~0~0~0~0~1~1~147~45~12~29~50~4~7~0/0~";}
return O;
}


function HPowerType(n){
var f=document.PokemonForm;
// Hidden Power Type
var O=" ";
O="~ ~";
if(n==0){O="~Fighting~";}
if(n==1){O="~Flying~";}
if(n==2){O="~Poison~";}
if(n==3){O="~Ground~";}
if(n==4){O="~Rock~";}
if(n==5){O="~Bug~";}
if(n==6){O="~Ghost~";}
if(n==7){O="~Steel~";}
if(n==8){O="~Fire~";}
if(n==9){O="~Water~";}
if(n==10){O="~Grass~";}
if(n==11){O="~Electric~";}
if(n==12){O="~Psychic~";}
if(n==13){O="~Ice~";}
if(n==14){O="~Dragon~";}
if(n==15){O="~Dark~";}
if(n==16){O="~Normal~";}
if(n==17){O="~ ~";}
return O;
}


function new_loc(x){
// Load New Location List
var f=document.PokemonForm;
var groups=f.Game.options.length;
var group=new Array(groups);
for (i=0; i<groups; i++)
group[i]=new Array();

group[0][0]=new Option("Route 101","1000");
group[0][1]=new Option("Route 102","1100");
group[0][2]=new Option("Route 103","1200");
group[0][3]=new Option("Route 104","1300");
group[0][4]=new Option("Route 105","1400");
group[0][5]=new Option("Route 106","1500");
group[0][6]=new Option("Route 107","1600");
group[0][7]=new Option("Route 108","1700");
group[0][8]=new Option("Route 109","1800");
group[0][9]=new Option("Route 110","1900");
group[0][10]=new Option("Route 111 (Desert)","1A00");
group[0][11]=new Option("Route 112","1B00");
group[0][12]=new Option("Route 113","1C00");
group[0][13]=new Option("Route 114","1D00");
group[0][14]=new Option("Route 115","1E00");
group[0][15]=new Option("Route 116","1F00");
group[0][16]=new Option("Route 117","2000");
group[0][17]=new Option("Route 118","2100");
group[0][18]=new Option("Route 119","2200");
group[0][19]=new Option("Route 120","2300");
group[0][20]=new Option("Route 121","2400");
group[0][21]=new Option("Route 122","2500");
group[0][22]=new Option("Route 123","2600");
group[0][23]=new Option("Route 124","2700");
group[0][24]=new Option("Route 125","2800");
group[0][25]=new Option("Route 126","2900");
group[0][26]=new Option("Route 127","2A00");
group[0][27]=new Option("Route 128","2B00");
group[0][28]=new Option("Route 129","2C00");
group[0][29]=new Option("Route 130","2D00");
group[0][30]=new Option("Route 131","2E00");
group[0][31]=new Option("Route 132","2F00");
group[0][32]=new Option("Route 133","3000");
group[0][33]=new Option("Route 134","3100");
group[0][34]=new Option("Meteor Falls 1","0018");
group[0][35]=new Option("Meteor Falls 2","0118");
group[0][36]=new Option("Meteor Falls 3","0218");
group[0][37]=new Option("Meteor Falls 4","0318");
group[0][38]=new Option("Meteor Falls 5 (Steven)","6B18");
group[0][39]=new Option("Rusturf Tunnel","0418");
group[0][40]=new Option("Granite Cave 1","0718");
group[0][41]=new Option("Granite Cave 2","0818");
group[0][42]=new Option("Granite Cave 3","0918");
group[0][43]=new Option("Granite Cave 4 (Steven)","0A18");
group[0][44]=new Option("Petalburg Woods","0B18");
group[0][45]=new Option("Jagged Pass","0D18");
group[0][46]=new Option("Fiery Path","0E18");
group[0][47]=new Option("Mt.Pyre 1","0F18");
group[0][48]=new Option("Mt.Pyre 2","1018");
group[0][49]=new Option("Mt.Pyre 3","1118");
group[0][50]=new Option("Mt.Pyre 4","1218");
group[0][51]=new Option("Mt.Pyre 5","1318");
group[0][52]=new Option("Mt.Pyre 6 Top (Inside)","1418");
group[0][53]=new Option("Mt.Pyre 7 (Outside)","1518");
group[0][54]=new Option("Mt.Pyre 8 Top (Outside)","1518");
group[0][55]=new Option("Seafloor Cavern 2","1C18");
group[0][56]=new Option("Seafloor Cavern 3","1D18");
group[0][57]=new Option("Seafloor Cavern 4","1E18");
group[0][58]=new Option("Seafloor Cavern 5","1F18");
group[0][59]=new Option("Seafloor Cavern 6","2018");
group[0][60]=new Option("Seafloor Cavern 7","2118");
group[0][61]=new Option("Seafloor Cavern 8","2218");
group[0][62]=new Option("Seafloor Cavern 9","2318");
group[0][63]=new Option("Cave of Origin 1","2518");
group[0][64]=new Option("Cave of Origin 2","2618");
group[0][65]=new Option("Cave of Origin [3]","2718");
group[0][66]=new Option("Cave of Origin [4]","2818");
group[0][67]=new Option("Cave of Origin [5]","2918");
group[0][68]=new Option("Victory Road 1","2B18");
group[0][69]=new Option("Victory Road 2","2C18");
group[0][70]=new Option("Victory Road 3","2D18");
group[0][71]=new Option("Shoal Cave 1","2E18");
group[0][72]=new Option("Shoal Cave 2","2F18");
group[0][73]=new Option("Shoal Cave 3","3018");
group[0][74]=new Option("Shoal Cave 4","3118");
group[0][75]=new Option("Shoal Cave (Ice)","5318");
group[0][76]=new Option("New Mauville 1","3418");
group[0][77]=new Option("New Mauville 2","3518");
group[0][78]=new Option("Sky Pillar 3","4F18");
group[0][79]=new Option("Sky Pillar 5","5118");
group[0][80]=new Option("Sky Pillar 7","5418");
group[0][81]=new Option("Mirage Tower 1","5E18");
group[0][82]=new Option("Mirage Tower 2","5F18");
group[0][83]=new Option("Mirage Tower 3","6018");
group[0][84]=new Option("Mirage Tower 4","6118");
group[0][85]=new Option("Desert Underpass","6218");
group[0][86]=new Option("Artisan Cave 1","6318");
group[0][87]=new Option("Artisan Cave 2","6418");
group[0][88]=new Option("Safari Zone A","031A");
group[0][89]=new Option("Safari Zone B (left)","021A");
group[0][90]=new Option("Safari Zone C (top-right)","011A");
group[0][91]=new Option("Safari Zone D (top-left)","001A");
group[0][92]=new Option("Safari Zone E (far-right)","0D1A");
group[0][93]=new Option("Safari Zone F","0C1A");

group[1][0]=new Option("Route 1","1303");
group[1][1]=new Option("Route 2","1403");
group[1][2]=new Option("Route 3","1503");
group[1][3]=new Option("Route 4","1603");
group[1][4]=new Option("Route 5","1703");
group[1][5]=new Option("Route 6","1803");
group[1][6]=new Option("Route 7","1903");
group[1][7]=new Option("Route 8","1A03");
group[1][8]=new Option("Route 9","1B03");
group[1][9]=new Option("Route 10","1C03");
group[1][10]=new Option("Route 11","1D03");
group[1][11]=new Option("Route 12","1E03");
group[1][12]=new Option("Route 13","1F03");
group[1][13]=new Option("Route 14","2003");
group[1][14]=new Option("Route 15","2103");
group[1][15]=new Option("Route 16","2203");
group[1][16]=new Option("Route 17","2303");
group[1][17]=new Option("Route 18","2403");
group[1][18]=new Option("Route 19","2503");
group[1][19]=new Option("Route 20","2603");
group[1][20]=new Option("Route 21","2703");
group[1][21]=new Option("Neo Route 21","2803");
group[1][22]=new Option("Route 22","2903");
group[1][23]=new Option("Route 23","2A03");
group[1][24]=new Option("Route 24","2B03");
group[1][25]=new Option("Route 25","2C03");
group[1][26]=new Option("Viridian Forest","0001");
group[1][27]=new Option("Mt.Moon 1","0101");
group[1][28]=new Option("Mt.Moon 2","0201");
group[1][29]=new Option("Mt.Moon 3","0301");
group[1][30]=new Option("Digletts Cave (Route 2)","2401");
group[1][31]=new Option("Digletts Cave","2501");
group[1][32]=new Option("Digletts Cave (Route 11)","2601");
group[1][33]=new Option("Victory Road 1","2701");
group[1][34]=new Option("Victory Road 2","2801");
group[1][35]=new Option("Victory Road 3","2901");
group[1][36]=new Option("Pokemon Mansion 1","3B01");
group[1][37]=new Option("Pokemon Mansion 2","3C01");
group[1][38]=new Option("Pokemon Mansion 3","3D01");
group[1][39]=new Option("Pokemon Mansion 4","3E01");
group[1][40]=new Option("Safari Zone A (center)","3F01");
group[1][41]=new Option("Safari Zone B (right)","4001");
group[1][42]=new Option("Safari Zone C (top)","4101");
group[1][43]=new Option("Safari Zone D (left)","4201");
group[1][44]=new Option("Cerulean Cave 1","4801");
group[1][45]=new Option("Cerulean Cave 2","4901");
group[1][46]=new Option("Cerulean Cave 3","4A01");
group[1][47]=new Option("Rock Tunnel 1","5101");
group[1][48]=new Option("Rock Tunnel 2","5201");
group[1][49]=new Option("Seafoam Islands 1","5301");
group[1][50]=new Option("Seafoam Islands 2","5401");
group[1][51]=new Option("Seafoam Islands 3","5501");
group[1][52]=new Option("Seafoam Islands 4","5601");
group[1][53]=new Option("Seafoam Islands 5","5701");
group[1][54]=new Option("Pokemon Tower 2","5901");
group[1][55]=new Option("Pokemon Tower 3","5A01");
group[1][56]=new Option("Pokemon Tower 4","5B01");
group[1][57]=new Option("Pokemon Tower 5","5C01");
group[1][58]=new Option("Pokemon Tower 6","5D01");
group[1][59]=new Option("Pokemon Tower 7 (Top)","5E01");
group[1][60]=new Option("Power Plant","5F01");
group[1][61]=new Option("Mt.Ember (Outside)","6101");
group[1][62]=new Option("Kindle Road","2D03");
group[1][63]=new Option("Treasure Beach ","2E03");
group[1][64]=new Option("Cape Brink","2F03");
group[1][65]=new Option("Bond Bridge","3003");
group[1][66]=new Option("Three Isle Port","3103");
group[1][67]=new Option("Resort Gorgeous","3603");
group[1][68]=new Option("Water Labrynth","3703");
group[1][69]=new Option("Five Isle Meadow ","3803");
group[1][70]=new Option("Memorial Pillar ","3903");
group[1][71]=new Option("Outcast Island ","3A03");
group[1][72]=new Option("Green Path ","3B03");
group[1][73]=new Option("Water Path","3C03");
group[1][74]=new Option("Ruin Valley","3D03");
group[1][75]=new Option("Trainer Tower ","3E03");
group[1][76]=new Option("Canyon Entrance ","3F03");
group[1][77]=new Option("Sevault Canyon ","4003");
group[1][78]=new Option("Tanoby Ruins","4103");
group[1][79]=new Option("Monean Chamber","1B02");
group[1][80]=new Option("Liptoo Chamber","1C02");
group[1][81]=new Option("Weepth Chamber","1D02");
group[1][82]=new Option("Dilford Chamber","1E02");
group[1][83]=new Option("Scufib Chamber","1F02");
group[1][84]=new Option("Rixy Chamber","2002");
group[1][85]=new Option("Viapois Chamber","2102");
group[1][86]=new Option("Berry Forest","6D01");
group[1][87]=new Option("Icefall Cave 1","6E01");
group[1][88]=new Option("Icefall Cave 2","6F01");
group[1][89]=new Option("Icefall Cave 3","7001");
group[1][90]=new Option("Icefall Cave 4","7101");
group[1][91]=new Option("Pattern Bush","7901");
group[1][92]=new Option("Altering Cave","7A01");

for (m=f.Loc.options.length-1;m>0;m--)
f.Loc.options[m]=null;
for (i=0;i<group[x].length;i++){
f.Loc.options[i]=new Option(group[x][i].text,group[x][i].value);
}
f.Loc.options[0].selected=true;
}


function getCookieVal (offset) {
//      - - - - - - - - Get Decoded Value of Cookie - - - - - - - -      
        var endstr = document.cookie.indexOf (";", offset);
               if (endstr == -1)
               endstr = document.cookie.length;
        return unescape(document.cookie.substring(offset, endstr));
        }
    

function GetCookie (name) {
//      - - - - - - - - Get Value of Cookie - - - - - - - - 
        var arg = name + "=";
        var alen = arg.length;
        var clen = document.cookie.length;
        var i = 0;
        while (i < clen) {
        var j = i + alen;
                if (document.cookie.substring(i, j) == arg)
                return getCookieVal (j);
        i = document.cookie.indexOf(" ", i) + 1;
                if (i == 0) break; 
        }

return null;
}


function SetCookie (name, value) {
//      - - - - - - - - Set Value of Cookie - - - - - - - -      
        var argv = SetCookie.arguments;
        var argc = SetCookie.arguments.length;
        var expires = (argc > 2) ? argv[2] : null;
        var path = (argc > 3) ? argv[3] : null;
        var domain = (argc > 4) ? argv[4] : null;
        var secure = (argc > 5) ? argv[5] : false;
        document.cookie = name + "=" + escape (value) +
        ((expires == null) ? "" : ("; expires=" + expires.toGMTString())) +
        ((path == null) ? "" : ("; path=" + path)) +
        ((domain == null) ? "" : ("; domain=" + domain)) +
        ((secure == true) ? "; secure" : "");
}


function Copy(c){
// This Function is Unused in Current Program
// 
var f = document.PokemonForm;
var C=f.Code;
if(c=="C"){C=f.Code;}
if(c=="L"){C=f.LogC;}
if(c=="D"){C=f.DNA;}
if(navigator.appName=="Microsoft Internet Explorer"){
 if(parseInt(navigator.appVersion) > 3){
 C.focus();
 C.select();
 var crange=C.createTextRange();
  copyRange=crange.execCommand("Copy");
 f.LogC.value=navigator.appName + " Copy Code Complete";
} else {
 f.LogC.value=navigator.appName + " Need Version4+";
}
} else {
 f.LogC.value=navigator.appName + " Can't Copy Code";
}
}

function Paste(c){
// This Function is Unused in Current Program
//
var f = document.PokemonForm;
var C=f.Code;
if(c=="C"){C=f.Code;}
if(c=="L"){C=f.LogC;}
if(c=="D"){C=f.DNA;}
if(navigator.appName=="Microsoft Internet Explorer"){
 if(parseInt(navigator.appVersion) > 3){
  C.value="";
  C.focus();
  document.execCommand('Paste');
 f.LogC.value=navigator.appName + " Paste Code Complete";
} else {
 f.LogC.value=navigator.appName + " Need Version4+";
}
} else {
 f.LogC.value=navigator.appName + " Can't Paste";
}
}

function MakeHexC(JI) {
// Version 3.00 07/26/2002 08:00 PM CST
// Convert 1 JunkChar to HexChar "0" - "F"
//
var HO=" ";
HO="*";
if(JI=="?") { HO="0"; }
if(JI=="0") { HO="0"; }
if(JI=="1") { HO="1"; }
if(JI=="2") { HO="2"; }
if(JI=="3") { HO="3"; }
if(JI=="4") { HO="4"; }
if(JI=="5") { HO="5"; }
if(JI=="6") { HO="6"; }
if(JI=="7") { HO="7"; }
if(JI=="8") { HO="8"; }
if(JI=="9") { HO="9"; }
if(JI=="a") { HO="A"; }
if(JI=="b") { HO="B"; }
if(JI=="c") { HO="C"; }
if(JI=="d") { HO="D"; }
if(JI=="e") { HO="E"; }
if(JI=="f") { HO="F"; }
if(JI=="A") { HO="A"; }
if(JI=="B") { HO="B"; }
if(JI=="C") { HO="C"; }
if(JI=="D") { HO="D"; }
if(JI=="E") { HO="E"; }
if(JI=="F") { HO="F"; }
return HO;
}

function MakeHexW(JI) {
// Version 3.00 07/26/2002 08:00 PM CST
// Take Junk Code and Make it Hex
// init vars
// vars for input & output
var mx = "0123456789abcdef";
var HO = "ERROR           ";
//  var for parsing HexInput
var CHF="F";
var CHE="E";
var CHD="D";
var CHC="C";
var CHB="B";
var CHA="A";
var CH9="9";
var CH8="8";
var CH7="7";
var CH6="6";
var CH5="5";
var CH4="4";
var CH3="3";
var CH2="2";
var CH1="1";
var CH0="0";
var chkspace = " ";
// Parse JunkIn and make valid hex
mx = JI;
CHF=MakeHexC(mx.substring(0,1));
CHE=MakeHexC(mx.substring(1,2));
CHD=MakeHexC(mx.substring(2,3));
CHC=MakeHexC(mx.substring(3,4));
CHB=MakeHexC(mx.substring(4,5));
CHA=MakeHexC(mx.substring(5,6));
CH9=MakeHexC(mx.substring(6,7));
CH8=MakeHexC(mx.substring(7,8));
chkspace=mx.substring(8,9);
if(chkspace==" "||chkspace==":") {
 CH7=MakeHexC(mx.substring(9,10));
 CH6=MakeHexC(mx.substring(10,11));
 CH5=MakeHexC(mx.substring(11,12));
 CH4=MakeHexC(mx.substring(12,13));
 CH3=MakeHexC(mx.substring(13,14));
 CH2=MakeHexC(mx.substring(14,15));
 CH1=MakeHexC(mx.substring(15,16));
 CH0=MakeHexC(mx.substring(16,17));
}else{
 CH7=MakeHexC(mx.substring(8,9));
 CH6=MakeHexC(mx.substring(9,10));
 CH5=MakeHexC(mx.substring(10,11));
 CH4=MakeHexC(mx.substring(11,12));
 CH3=MakeHexC(mx.substring(12,13));
 CH2=MakeHexC(mx.substring(13,14));
 CH1=MakeHexC(mx.substring(14,15));
 CH0=MakeHexC(mx.substring(15,16));
}
HO=CHF+CHE+CHD+CHC+CHB+CHA+CH9+CH8;
HO+=CH7+CH6+CH5+CH4+CH3+CH2+CH1+CH0;
return HO;
}

function DecToHex(DecNum, Group, Sign, Dollar) {
// All Function by kpdavatar@programmer.net
// Version 8.02s 09/25/2003 04:00 PM CST
// DecNum = Decimal Number In
// Group = Number of digit to show
// Sign = 0 no sign / Sign = 1 show sign / Sign = 2 invert bits
// Dollar = 0 no $ / Dollar = 1 show $
// 0xFF javascript hex value
// 4294967296 dec = 0x100000000 hex too big
// 268435456 dec = 0x10000000 hex
// 16777216 dec = 0x1000000 hex
// 1048576 dec = 0x100000 hex
// 65536 dec = 0x10000 hex
// 4096 dec = 0x1000 hex
// 256 dec = 0x100 hex
// 16 dec = 0x10 hex
// 1 dec = 0x01 hex
 var HexChars = "0123456789ABCDEF";
 var HexOut = "00000000";
 var tc = " ";
 var H7 = 0;
 var H6 = 0;
 var H5 = 0;
 var H4 = 0;
 var H3 = 0;
 var H2 = 0;
 var H1 = 0;
 var H0 = 0;
 var a = 0;
 var b = 0;
 var g = 1;
 var s = 0;
 var st = 0;
 var d = 0;
 s = 0;
 st = 0;
 if (Sign == 1) { s = 1; }
 if (Sign == 2) { s = 2; }
 d = 0;
 if (Dollar == 1) { d = 1; }
 g = 1;
 g = Group;
 if (g < 1 || g > 8) {
  g = 1;
 }
 a = DecNum;
 if (a < 0) {
  st = 1;
  if (s == 1) {
   a = a * -1;
  }
  if (s == 2) {
   a = a * -1;
   a -= 1;
  }
 }
 if (a > 0xFFFFFFFF) {
 a = 0;
 }
 b = a % 0x10000000;
 H7 = (a - b) / 0x10000000;
 a = b;
 b = a % 0x1000000;
 H6 = (a - b) / 0x1000000;
 a = b;
 b = a % 0x100000;
 H5 = (a - b) / 0x100000;
 a = b;
 b = a % 0x10000;
 H4 = (a - b) / 0x10000;
 a = b;
 b = a % 0x1000;
 H3 = (a - b) / 0x1000;
 a = b;
 b = a % 0x100;
 H2 = (a - b) / 0x100;
 a = b;
 b = a % 0x10;
 H1 = (a - b) / 0x10;
 H0 = b;
 HexOut = "";
 if (s == 1 ) {
  if (st == 1) {
   HexOut += "-";
  } else {
   HexOut += "+";
  }
 }
 if (d == 1) { HexOut += "$"; }  
 if (g > 7) {
  tc = HexChars.charAt(H7);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 if (g > 6) {
  tc = HexChars.charAt(H6);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 if (g > 5) {
  tc = HexChars.charAt(H5);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 if (g > 4) {
  tc = HexChars.charAt(H4);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 if (g > 3) {
  tc = HexChars.charAt(H3);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 if (g > 2) {
  tc = HexChars.charAt(H2);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 if (g > 1) {
  tc = HexChars.charAt(H1);
  if (s == 2 && st == 1) { tc = InvHex(tc);}
  HexOut += tc;
 }
 tc = HexChars.charAt(H0);
 if (s == 2 && st == 1) { tc = InvHex(tc);}
 HexOut += tc;
// output HexOut
 return HexOut;
}

function InvHex(Hex) {
// All Function by kpdavatar@programmer.net
// Version 8.02s 09/25/2003 04:00 PM CST
 var IHex = "0";
 if (Hex == "0") { IHex = "F"; }
 if (Hex == "1") { IHex = "E"; }
 if (Hex == "2") { IHex = "D"; }
 if (Hex == "3") { IHex = "C"; }
 if (Hex == "4") { IHex = "B"; }
 if (Hex == "5") { IHex = "A"; }
 if (Hex == "6") { IHex = "9"; }
 if (Hex == "7") { IHex = "8"; }
 if (Hex == "8") { IHex = "7"; }
 if (Hex == "9") { IHex = "6"; }
 if (Hex == "A") { IHex = "5"; }
 if (Hex == "B") { IHex = "4"; }
 if (Hex == "C") { IHex = "3"; }
 if (Hex == "D") { IHex = "2"; }
 if (Hex == "E") { IHex = "1"; }
 if (Hex == "F") { IHex = "0"; }
 if (Hex == "a") { IHex = "5"; }
 if (Hex == "b") { IHex = "4"; }
 if (Hex == "c") { IHex = "3"; }
 if (Hex == "d") { IHex = "2"; }
 if (Hex == "e") { IHex = "1"; }
 if (Hex == "f") { IHex = "0"; }
  return IHex;
}

function GAD(Code,what) {
// Version 9.00 07/30/2003 09:22 PM CST
// Gamboy Advance Decrypt
var x=" ";
var y=" ";
var ta=" ";
var tv=" ";
var z=" ";
var mx=" ";
// Get Code
x=Code;
mx=x+"00000000000000000";
mx=mx.substr(0,17);
// make sure input is hex
 mx = MakeHexW(mx);
ta = mx.substr(0,8);
tv = mx.substr(8,16);
y = GADecrypt(ta,tv,what);
// put Hex code out
x= y.substring(0,8);
z= y.substring(8,16);
y=x+z;
// y+=" "+what;
return y;
}

function GADecrypt(ar,vl,what) {
// Version 9.00 07/30/2003 09:22 PM CST
// Use Parsite Info.
 var rs = "0xC6EF3720";
 var ra = "0x9E3779B9";
 var v1s0 = "0x09F4FBBD";
 var v1s1 = "0x9681884A";
 var v1s2 = "0x352027E9";
 var v1s3 = "0xF3DEE5A7";
 var v3s0 = "0x7AA9648F";
 var v3s1 = "0x7FAE6994";
 var v3s2 = "0xC0EFAAD5";
 var v3s3 = "0x42712C57";
 var loop = 0;
 var tval = 0;
 var tadd = 0;
 var shif = 0;
 var s0 = 0;
 var s1 = 0;
 var s2 = 0;
 var s3 = 0;
var r = 0;
var rsa = 0;
var t = 0;
var t2 = 0;
 var hout = "0123456789ancdef";

r = 1 * rs;
rsa = 1 * ra;
 if (what == "1") {
  s0 = 1 * v1s0;
  s1 = 1 * v1s1;
  s2 = 1 * v1s2;
  s3 = 1 * v1s3;
 } else {
  s0 = 1 * v3s0;
  s1 = 1 * v3s1;
  s2 = 1 * v3s2;
  s3 = 1 * v3s3;
 }
 tval = 1 * ("0x" + vl);
 tadd = 1 * ("0x" + ar);
l = 32;
while (l > 0) {
 t = (tadd << 4) & (1 * "0xFFFFFFFF");
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t += s2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = tadd + r;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = (tadd >> 5) & (1 * "0x07FFFFFF");
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t2 += s3;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 tval -= t;
 if (tval < 0) { tval += (1 * "0x100000000"); }
 if (tval > (1 * "0xFFFFFFFF")) { tval -= (1 * "0x100000000"); }
 t = (tval << 4) & (1 * "0xFFFFFFFF");
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t += s0;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = tval + r;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = (tval >> 5) & (1 * "0x07FFFFFF");
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t2 += s1;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 tadd -= t;
 if (tadd < 0) { tadd += (1 * "0x100000000"); }
 if (tadd > (1 * "0xFFFFFFFF")) { tadd -= (1 * "0x100000000"); }
 r -= rsa;
 if (r < 0) { r += (1 * "0x100000000"); }
 if (r > (1 * "0xFFFFFFFF")) { r -= (1 * "0x100000000"); }
 l --;
}
hout = DecToHex(tadd,8,2) + DecToHex(tval,8,2);
return hout;
}

function GAE(Code,what) {
// Version 9.00 07/30/2003 09:22 PM CST
// Gamboy Advance Decrypt
var x=" ";
var y=" ";
var ta=" ";
var tv=" ";
var z=" ";
var mx=" ";
// Get Code
x=Code;
mx=x+"00000000000000000";
mx=mx.substr(0,17);
// make sure input is hex
 mx = MakeHexW(mx);
 ta = mx.substr(0,8);
 if(what=="1") { ta= "2"+ ta.substr(1,8); }
 if(what=="3") { ta= "04"+ mx.substr(1,1)+  mx.substr(3,5); }
// if(what=="3") { ta="04"+mx.substr(1,2)+ mx.substr(3,8); )
 tv = mx.substr(8,16);
 y = GAEncrypt(ta,tv,what);
// put Hex code out
x=y.substring(0,8);
z=y.substring(8,16);
y=x+" "+z;
// y+=" "+what;
return y;
}

function GAEncrypt(ar,vl,what) {
// Version 9.00 07/30/2003 09:22 PM CST
// Use Parsite Info.
 var rs = "0x00000000";
 var ra = "0x9E3779B9";
 var v1s0 = "0x09F4FBBD";
 var v1s1 = "0x9681884A";
 var v1s2 = "0x352027E9";
 var v1s3 = "0xF3DEE5A7";
 var v3s0 = "0x7AA9648F";
 var v3s1 = "0x7FAE6994";
 var v3s2 = "0xC0EFAAD5";
 var v3s3 = "0x42712C57";
 var loop = 0;
 var tval = 0;
 var tadd = 0;
 var shif = 0;
 var s0 = 0;
 var s1 = 0;
 var s2 = 0;
 var s3 = 0;
var r = 0;
var rsa = 0;
var t = 0;
var t2 = 0;
var hout = "0123456789abcdef";

r = 1 * rs;
rsa = 1 * ra;
 if (what == "1") {
  s0 = 1 * v1s0;
  s1 = 1 * v1s1;
  s2 = 1 * v1s2;
  s3 = 1 * v1s3;
 } else {
  s0 = 1 * v3s0;
  s1 = 1 * v3s1;
  s2 = 1 * v3s2;
  s3 = 1 * v3s3;
 }
 tval = 1 * ("0x" + vl);
 tadd = 1 * ("0x" + ar);
l = 32;
while (l > 0) {
 r += rsa;
 if (r < 0) { r += (1 * "0x100000000"); }
 if (r > (1 * "0xFFFFFFFF")) { r -= (1 * "0x100000000"); }
 t = (tval << 4) & (1 * "0xFFFFFFFF");
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t += s0;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = tval + r;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = (tval >> 5) & (1 * "0x07FFFFFF");
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t2 += s1;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 tadd += t;
 if (tadd < 0) { tadd += (1 * "0x100000000"); }
 if (tadd > (1 * "0xFFFFFFFF")) { tadd -= (1 * "0x100000000"); }
 t = (tadd << 4) & (1 * "0xFFFFFFFF");
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t += s2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = tadd + r;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 t2 = (tadd >> 5) & (1 * "0x07FFFFFF");
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t2 += s3;
 if (t2 < 0) { t2 += (1 * "0x100000000"); }
 if (t2 > (1 * "0xFFFFFFFF")) { t2 -= (1 * "0x100000000"); }
 t ^= t2;
 if (t < 0) { t += (1 * "0x100000000"); }
 if (t > (1 * "0xFFFFFFFF")) { t -= (1 * "0x100000000"); }
 tval += t;
 if (tval < 0) { tval += (1 * "0x100000000"); }
 if (tval > (1 * "0xFFFFFFFF")) { tval -= (1 * "0x100000000"); }
 l --;
}
hout = DecToHex(tadd,8,2) + DecToHex(tval,8,2);
return hout;
}


function UnownID(P,W){
// Function by kpdavatar@netbroadcaster.com
// Version 0.00 02/03/2004 05:15 PM CST
var S = 0;
var U = 0;
var UC = "A";
S=Math.floor(P%4);
S+=(Math.floor(P/256)%4)*4;
S+=(Math.floor(P/65536)%4)*16;
S+=(Math.floor(P/16777216)%4)*64;
U = Math.floor(S % 28);
if(W==0){ return U; }
if(W==1){
 if(U==0){UC="A";}
 if(U==1){UC="B";}
 if(U==2){UC="C";}
 if(U==3){UC="D";}
 if(U==4){UC="E";}
 if(U==5){UC="F";}
 if(U==6){UC="G";}
 if(U==7){UC="H";}
 if(U==8){UC="I";}
 if(U==9){UC="J";}
 if(U==10){UC="K";}
 if(U==11){UC="L";}
 if(U==12){UC="M";}
 if(U==13){UC="N";}
 if(U==14){UC="O";}
 if(U==15){UC="P";}
 if(U==16){UC="Q";}
 if(U==17){UC="R";}
 if(U==18){UC="S";}
 if(U==19){UC="T";}
 if(U==20){UC="U";}
 if(U==21){UC="V";}
 if(U==22){UC="W";}
 if(U==23){UC="X";}
 if(U==24){UC="Y";}
 if(U==25){UC="Z";}
 if(U==26){UC="!";}
 if(U==27){UC="?";}
 return UC;
}
if(W==3){return S;}
}


function EnablePID(){
var f=document.PokemonForm;
var pgn=f.Species.options[f.Species.selectedIndex].value;
if(f.MPID.checked==true && pgn==308){
 f.Shiny.disabled=true;
 f.PGender.disabled=true;
 //$ f.PGender.style.backgroundColor='#DFDFDF';
 f.Nature.disabled=true;
 //$ f.Nature.style.backgroundColor='#DFDFDF';
 f.UserPID.disabled=false;
 f.UserPID.style.backgroundColor='';
 document.getElementById("radix").style.display="block";
 f.Code.rows=27;
}else{
 if(f.MPID.checked==true){f.MPID.checked=false; FillAll();}
 f.Shiny.disabled=false;
 f.PGender.disabled=false;
 //$ f.PGender.style.backgroundColor=''; 
 f.Nature.disabled=false;
 //$ f.Nature.style.backgroundColor=''; 
 f.UserPID.disabled=true; 
 f.UserPID.style.backgroundColor='#DFDFDF';
 document.getElementById("radix").style.display="none";
 if(pgn==290 || pgn==308){
  f.Code.rows=26;
 }else{
  f.Code.rows=25;
 }  
}
}

var lastBase=0; // global

function EvalPID(){
var f=document.PokemonForm;
if(f.MPID.checked==true){
 if(f.base[1].checked){
  if(lastBase==0){
    f.UserPID.value=DecToHex(f.UserPID.value,8);
  }
  if(f.UserPID.value.length > 8){f.UserPID.value=f.UserPID.value.substring(0,8);}
  f.PID.value=parseInt(f.UserPID.value,16);
  lastBase=1; // global
 }else{
  if(lastBase==1){
    f.UserPID.value=parseInt(f.UserPID.value,16); 
  } 
  f.PID.value=f.UserPID.value;
  lastBase=0; // global
 }
}
}

function Device(i){
var f=document.PokemonForm;
var state;
if(f.Code.value!=""){
  EnablePID();
  state = f.MPID.checked;
  f.MPID.checked=true;
  codeout(i);
  f.MPID.checked=state;
}
}


function FillAll(){
var f=document.PokemonForm;
var P=f.Species;
var Pvalue=P.options[P.selectedIndex].value;
var U=f.Unown;
var Utext=U.options[U.selectedIndex].text;
var G=f.PGender;
var N=f.Nature;
var D=f.RDNA;
var W=f.WurmEvo;
var As=f.RA;
var Bs=f.RB;
var Cs=f.RC;
var Ds=f.RD;
var BA0=" ";
var BA1=" ";
var BA2=" ";
var BB0=" ";
var BB1=" ";
var BB2=" ";
var BC0=" ";
var BC1=" ";
var BC2=" ";
var BD0=" ";
var BD1=" ";
var BD2=" ";
var tt=" ";
var ts=" ";
var tg=0;
var gt=0;
var tn=0;
var tw=0;
var tpid=0;
var hpid=0;
var tid=0;
var xk=0;
var r=0;
var r1=0;
var S=" ";
var addr=0;
var cs=0;
var i=0;
xk = 0;
f.WurmVal.value="";
r=1*f.STID.value;
if(r<0||r>65565){r=Math.round(Math.random()*65535);}
f.STID.value=r;
r=1*f.TID.value
if(r<0||r>65565){r=Math.round(Math.random()*65535);}
f.TID.value=r;
tid=(f.STID.value*65536)+(1*f.TID.value);
if(f.MPID.checked==false){
 if(f.Shiny.checked){
  i=0;
  gt=Gtest();
  for(i=0;i<65536;i++){  // begin loop
   r=Math.round(Math.random()*65535);
   xk=(r*65536)+(r^(Math.round(Math.random()*7)));
   if(xk<0){xk+=(1*"0x100000000");}
   tpid=xk^tid;
   if(tpid<0){tpid+=(1*"0x100000000");}
   tg=Math.floor(tpid%256);
   if(tg<0){tg+=256;}
   tn=Math.floor(tpid%25);
   if(tn<0){tn+=25;}
   
   hpid=Math.floor(tpid / 0x10000);
   tw=Math.floor(hpid%10);
   if(tw<0){tw+=10;}
   (tw<5)?tw=0:tw=1;
   
   if(tg>=gt && G.selectedIndex==1 && N.selectedIndex==tn){
    if(Pvalue==201){
     if(UnownID(tpid,1)==Utext){i=65537;}
    }else if(Pvalue==290){
     if(W.selectedIndex==tw){i=65537;}
    }else{
     i=65537; // if condtions true, end loop
    }
   }
   if(tg<gt && G.selectedIndex==0 && N.selectedIndex==tn){
    if(Pvalue==201){
     if(UnownID(tpid,1)==Utext){i=65537;}
    }else if(Pvalue==290){
     if(W.selectedIndex==tw){i=65537;}
    }else{
     i=65537; // if condtions true, end loop
    }
   }
  }  // end of loop
 }else{  // if(f.Shiny.checked==false){
  i=0;
  gt=Gtest();
  for(i=0;i<65536;i++){  // begin loop
   tpid=(Math.round(Math.random()*65536)*Math.round(Math.random()*65536))+Math.round(Math.random()*65512);
   if(tpid<0){tpid+=(1*"0x100000000");}
   tn=Math.floor(tpid%25);
   if(tpid<0){tpid+=(1*"0x100000000");}
   tpid+=f.Nature.selectedIndex;
   if(tpid<0){tpid+=(1*"0x100000000");}
   tg=Math.floor(tpid%256);
   if(tg<0){tg+=256;}
   tn=Math.floor(tpid%25);
   if(tn<0){tn+=25;}
   
   hpid=Math.floor(tpid / 0x10000);
   tw=Math.floor(hpid%10);
   if(tw<0){tw+=10;}
   (tw<5)?tw=0:tw=1;
   
   if(tg>=gt && G.selectedIndex==1 && N.selectedIndex==tn){
    if(Pvalue==201){
     if(UnownID(tpid,1)==Utext){i=65537;}
    }else if(Pvalue==290){
     if(W.selectedIndex==tw){i=65537;}
    }else{
     i=65537; // if condtions true, end loop
    }
   }
   if(tg<gt && G.selectedIndex==0 && N.selectedIndex==tn){
    if(Pvalue==201){
     if(UnownID(tpid,1)==Utext){i=65537;}
    }else if(Pvalue==290){
     if(W.selectedIndex==tw){i=65537;}
    }else{
     i=65537; // if condtions true, end loop
    }
   }
  }  // end of loop
  xk=tid^tpid;
 }
 if(i<65538){f.PID.value="try again"; f.Code.value="try again"; return;}else{f.PID.value=tpid;}
}else{  // if(f.MPID.checked==true){ 
 tpid=f.PID.value*1;
 tn=Math.floor(tpid%25);
 if(tn<0){tn+=25;}
 N.selectedIndex=tn;
 
 hpid=Math.floor(tpid / 0x10000);
 tw=Math.floor(hpid%10);
 if(tw<0){tw+=10;}
 (tw<5)?tw=0:tw=1; // 0=silcoon, 1=cascoon
 W.selectedIndex=tw;
 
 tg=Math.floor(tpid%256);
 if(tg<0){tg+=256;}
 gt=Gtest();
 if(tg>=gt){tg=1;}else{tg=0;}
 G.selectedIndex==tg;
 i=Math.floor(tpid%65536);
 r=(1*f.TID.value)^i;
 i=Math.floor(tpid/65536);
 r1=(1*f.STID.value)^i;
 xk=r^r1;
 if(xk<8){f.Shiny.checked=true;}else{f.Shiny.checked=false;}
 xk=tid^tpid;
 ts=Pvalue;
 if(ts=="201"){
  r1=UnownID(tpid,0);
  U.options[r1].selected=true;
 }
}
r1=xk;
if(r1<0){r1+=1*"0x100000000";}
if(r1>(1*"0xFFFFFFFF")){r1-=1*"0x100000000";}
xk=r1;
tg=Math.floor(tpid%256);
gt=Gtest();
if(tg>=gt){tg=1;}else{tg=0;}
G.selectedIndex=tg;
f.WurmVal.value=Math.floor(hpid);
f.PID.value=tpid;
if(f.base[1].checked){
 f.UserPID.value=DecToHex(tpid,8);
}else{
 f.UserPID.value=tpid;
}
f.XKey.value=DecToHex(xk,8);
}


function codeout(n){
var d=document;
var f=d.PokemonForm;
var addr=0;
var tt=" ";
var t=" ";
var r=0;
var L="\r\n";
var D=f.RDNA;
var tcode="";
var tlog=" ";
var gver=0;
var i=0;
var BA0=" ";
var BA1=" ";
var BA2=" ";
var BA3=" ";
var L="\r\n";
t=FillAll();
if(n==4){
 r=0;
 for (i=0; i<4; i++){
  if(f.RCode[i].checked){
   r=i;
   i=5;
  }
 }
}else{
r=n;
}

f.LogC.value="Code Out";
tlog="Code Output\r\n";
tCode="";
t="";

// Mastercode

t="Pokemon Emerald (U)"+L;
gver=f.Game.selectedIndex;
if(gver==0){t="Pokemon Emerald (U)"+L;}
if(gver==1){t="Pokemon FireRed 1.0 (U)"+L;}
if(gver==2){t="Pokemon LeafGreen 1.0 (U)"+L;}
if(gver==3){t="Pokemon FireRed 1.1 (U)"+L;}
if(gver==4){t="Pokemon LeafGreen 1.1 (U)"+L;}

if(f.Codetype.selectedIndex==1 && r==2){
 if(gver==0){t+=L+"(m)"+L+"D8BAE4D9 4864DCE5"+L+"A86CDBA5 19BA49B3"+L+L+"RNG Kill"+L+"66BC3257 9381D042"+L+"8E883EFF 92E9660D"+L;}
 else if(gver==1){t+=L+"(m)"+L+"72BC6DFB E9CA5465"+L+"A47FB2DC 1AF3CA86"+L+L+"RNG Kill"+L+"3AF85ACA C4D18CEC"+L+"8E883EFF 92E9660D"+L;}
 else if(gver==2){t+=L+"(m)"+L+"72BC6DFB E9CA5465"+L+"56671F3A 6F4F4D6B"+L+L+"RNG Kill"+L+"3AF85ACA C4D18CEC"+L+"8E883EFF 92E9660D"+L;}
 else if(gver==3){t+=L+"(m)"+L+"E6A003D6 8110DDD5"+L+"A47FB2DC 1AF3CA86"+L+L+"RNG Kill"+L+"8B25594B 8E78C0C5"+L+"8E883EFF 92E9660D"+L;}
 else if(gver==4){t+=L+"(m)"+L+"E6A003D6 8110DDD5"+L+"56671F3A 6F4F4D6B"+L+L+"RNG Kill"+L+"8B25594B 8E78C0C5"+L+"8E883EFF 92E9660D"+L;}
 else{f.Codetype.selectedIndex=0;}  //this line is for any other games not covered [not actually needed]
}else{
 f.Codetype.selectedIndex=0;}  //if not ARv3, this changes the codetype option to DMA version

if(f.Codetype.selectedIndex==0){
 if(gver==0 && r==0){t+=L+"DMA Disabler (must be on) GS-v1"+L+"BB2BBB12B327B9BD"+L;}
 if(gver==0 && r==1){t+=L+"(m)"+L+"78A0B2AE 45CB4E65"+L+"3C1BD432 E365EC14"+L+L+"DMA Disabler (must be on)"+L+"BB2BBB12 B327B9BD"+L;}
 if(gver==0 && r==2){t+=L+"(m)"+L+"D8BAE4D9 4864DCE5"+L+"A86CDBA5 19BA49B3"+L+L+"DMA Disabler (must be on)"+L+"A57E2EDE A5AFF3E4"+L+"1C7B3231 B494738C"+L;}

 if(gver==1 && r==0){t+=L+"DMA Disabler (must be on) GS-v1"+L+"20AAA133853F98EB"+L;}
 if(gver==1 && r==1){t+=L+"(m)"+L+"78A0B2AE 45CB4E65"+L+"3C1BD432 E365EC14"+L+L+"DMA Disabler (must be on)"+L+"20AAA133 853F98EB"+L;}
 if(gver==1 && r==2){t+=L+"(m)"+L+"72BC6DFB E9CA5465"+L+"A47FB2DC 1AF3CA86"+L+L+"DMA Disabler (must be on)"+L+"8D671FD9 6F6BEFF2"+L+"78DA95DF 44018CB4"+L;}

 if(gver==2 && r==0){t+=L+"DMA Disabler (must be on) GS-v1"+L+"20AAA133853F98EB"+L;}
 if(gver==2 && r==1){t+=L+"(m)"+L+"78A0B2AE 45CB4E65"+L+"4D2BB04F 34651E54"+L+L+"DMA Disabler (must be on)"+L+"20AAA133 853F98EB"+L;}
 if(gver==2 && r==2){t+=L+"(m)"+L+"72BC6DFB E9CA5465"+L+"56671F3A 6F4F4D6B"+L+L+"DMA Disabler (must be on)"+L+"8D671FD9 6F6BEFF2"+L+"78DA95DF 44018CB4"+L;}

 if(gver==3 && r==0){t+=L+"DMA Disabler (must be on) GS-v1"+L+"08CEC818DE923E83"+L;}
 if(gver==3 && r==1){t+=L+"(m)"+L+"388E455E F1D8A012"+L+"3C1BD432 E365EC14"+L+L+"DMA Disabler (must be on)"+L+"08CEC818 DE923E83"+L;}
 if(gver==3 && r==2){t+=L+"(m)"+L+"E6A003D6 8110DDD5"+L+"A47FB2DC 1AF3CA86"+L+L+"DMA Disabler (must be on)"+L+"24C35E88 037C3033"+L+"78DA95DF 44018CB4"+L;}

 if(gver==4 && r==0){t+=L+"DMA Disabler (must be on) GS-v1"+L+"08CEC818DE923E83"+L;}
 if(gver==4 && r==1){t+=L+"(m)"+L+"388E455E F1D8A012"+L+"4D2BB04F 34651E54"+L+L+"DMA Disabler (must be on)"+L+"08CEC818 DE923E83"+L;}
 if(gver==4 && r==2){t+=L+"(m)"+L+"E6A003D6 8110DDD5"+L+"56671F3A 6F4F4D6B"+L+L+"DMA Disabler (must be on)"+L+"24C35E88 037C3033"+L+"78DA95DF 44018CB4"+L;}
}
tcode+=t;

// Encounter Activator

tcode+="\r\n\r\nEncounter Activator\r\n";
BA0="020";
if(r==1){BA0="020"; }
if(r==2){BA0="002"; }

if(f.Codetype.selectedIndex==0){  //address for code item
 if(gver==0){BA1=BA0+"28BEF";}
 if(gver>=1 && gver<=4){BA1=BA0+"2860F";}
}
if(f.Codetype.selectedIndex==1){  //pointer address
 if(gver==0){BA1="40305D90";}
 if(gver>=1 && gver<=4){BA1="4030500C";}
}

if(r==0){BA2="";}else{BA2="000000";}  //VBA and Cheat Device zero fill 
if(r==2 && f.Codetype.selectedIndex==1){  //Pointer Offset (option for ARv3 only)
 if(gver==0){BA2="00419B";}
 if(gver>=1 && gver<=4){BA2="004087";}
}
BA2+="01";   //value
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

// Pokemon Species

i=f.Species.options[f.Species.selectedIndex].value;
tt=PokeDex(i);
t=FI(tt,"~",3);
tcode+="\r\nPokemon Species: "+t+"\r\n";
BA0="020";
if(r==1){BA0="120"; }
if(r==2){BA0="022"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BE4";}
 if(gver>=1 && gver<=4){BA1=BA0+"28604";}
} 
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="42305D90";}
 if(gver>=1 && gver<=4){BA1="4230500C";} 
}

if(r==0){BA2="0";}else{BA2="00000";}
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA2="20C80";}
 if(gver>=1 && gver<=4){BA2="203E0";}
}
BA2+=DecToHex(f.Species.options[f.Species.selectedIndex].value,3);
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

// MAP

BA0="";
if(f.Nature.selectedIndex==0){BA0="Hardy";}
if(f.Nature.selectedIndex==1){BA0="Lonely";}
if(f.Nature.selectedIndex==2){BA0="Brave";}
if(f.Nature.selectedIndex==3){BA0="Adamant";}
if(f.Nature.selectedIndex==4){BA0="Naughty";}
if(f.Nature.selectedIndex==5){BA0="Bold";}
if(f.Nature.selectedIndex==6){BA0="Docile";}
if(f.Nature.selectedIndex==7){BA0="Relaxed";}
if(f.Nature.selectedIndex==8){BA0="Impish";}
if(f.Nature.selectedIndex==9){BA0="Lax";}
if(f.Nature.selectedIndex==10){BA0="Timid";}
if(f.Nature.selectedIndex==11){BA0="Hasty";}
if(f.Nature.selectedIndex==12){BA0="Serious";}
if(f.Nature.selectedIndex==13){BA0="Jolly";}
if(f.Nature.selectedIndex==14){BA0="Naive";}
if(f.Nature.selectedIndex==15){BA0="Modest";}
if(f.Nature.selectedIndex==16){BA0="Mild";}
if(f.Nature.selectedIndex==17){BA0="Quiet";}
if(f.Nature.selectedIndex==18){BA0="Bashful";}
if(f.Nature.selectedIndex==19){BA0="Rash";}
if(f.Nature.selectedIndex==20){BA0="Calm";}
if(f.Nature.selectedIndex==21){BA0="Gentle";}
if(f.Nature.selectedIndex==22){BA0="Sassy";}
if(f.Nature.selectedIndex==23){BA0="Careful";}
if(f.Nature.selectedIndex==24){BA0="Quirky";}
if(f.PGender.options[f.PGender.selectedIndex].text!="None"){
BA0+="/"+f.PGender.options[f.PGender.selectedIndex].text;}
if(f.Shiny.checked){BA0+="/Shiny";}
if(f.Species.value==201){BA0+="/'"+f.Unown.options[f.Unown.selectedIndex].text+"'";}
if(f.Species.value==290){BA0+="/"+f.WurmEvo.options[f.WurmEvo.selectedIndex].text.substring(0,4);}
tcode+="\r\nMAP Data: "+BA0+"\r\n";
BA0="020";
if(r==1){BA0="220"; }
if(r==2){BA0="042"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BE0";}
 if(gver>=1 && gver<=4){BA1=BA0+"28600";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="42305D90";}
 if(gver>=1 && gver<=4){BA1="4230500C";} 
}

if(r==0){BA2="";}else{BA2="";}
BA2+=DecToHex(f.PID.value,8);
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA3="20C7"+BA2.substring(0,4); BA2="20C6"+BA2.substring(4,8);}
 if(gver>=1 && gver<=4){BA3="203D"+BA2.substring(0,4); BA2="203C"+BA2.substring(4,8);}
}

if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

if(r==2 && f.Codetype.selectedIndex==1){tt=GAEncrypt(BA1,BA3,"3");
tt=tt.substring(0,8)+" "+tt.substring(8,16);
tcode+=tt+"\r\n";}

// Level

tcode+="\r\nLevel: "+f.XLvl.value+"\r\n";
BA0="020";
if(r==1){BA0="020"; }
if(r==2){BA0="002"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BE8";}
 if(gver>=1 && gver<=4){BA1=BA0+"28608";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="40305D90";}
 if(gver>=1 && gver<=4){BA1="4030500C";} 
}

if(r==0){BA2="";}else{BA2="000000";}
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA2="004194";}
 if(gver>=1 && gver<=4){BA2="004080";} 
}
BA2+=DecToHex(f.XLvl.value,2);
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

// Current HP

tcode+="\r\nCurrent HP: "+f.CurrentHP.value+"\r\n";
BA0="020";
if(r==1){BA0="120"; }
if(r==2){BA0="022"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BE6";}
 if(gver>=1 && gver<=4){BA1=BA0+"28606";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="42305D90";}
 if(gver>=1 && gver<=4){BA1="4230500C";} 
}

if(r==0){BA2="";}else{BA2="0000";}
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA2="20C9";}
 if(gver>=1 && gver<=4){BA2="203F";}
}
BA2+=DecToHex(f.CurrentHP.value,4);
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

// IV Stats

BA0=f.HPDV.selectedIndex;
BA0+=","+f.AtkDV.selectedIndex;
BA0+=","+f.DefDV.selectedIndex;
BA0+=","+f.SpADV.selectedIndex;
BA0+=","+f.SpDDV.selectedIndex;
BA0+=","+f.SpeDV.selectedIndex;
tcode+="\r\IV Stats: "+BA0+"\r\n";
BA0="020";
if(r==1){BA0="220"; }
if(r==2){BA0="042"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BDC";}
 if(gver>=1 && gver<=4){BA1=BA0+"285FC";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="42305D90";}
 if(gver>=1 && gver<=4){BA1="4230500C";} 
}

if(r==0){BA2="";}else{BA2="";}
i=(f.SpDDV.selectedIndex)*33554432;
i+=(f.SpADV.selectedIndex)*1048576;
i+=(f.SpeDV.selectedIndex)*32768;
i+=(f.DefDV.selectedIndex)*1024;
i+=(f.AtkDV.selectedIndex)*32;
i+=(f.HPDV.selectedIndex)*1;
BA2+=DecToHex(i,8);
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA3="20C5"+BA2.substring(0,4); BA2="20C4"+BA2.substring(4,8);}
 if(gver>=1 && gver<=4){BA3="203B"+BA2.substring(0,4); BA2="203A"+BA2.substring(4,8);} 
}

if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

if(r==2 && f.Codetype.selectedIndex==1){tt=GAEncrypt(BA1,BA3,"3");
tt=tt.substring(0,8)+" "+tt.substring(8,16);
tcode+=tt+"\r\n";}

// Contest Stats

if(f.Cool.value>255){f.Cool.value=255;}
if(f.Beauty.value>255){f.Beauty.value=255;}
if(f.Cute.value>255){f.Cute.value=255;}
if(f.Smart.value>255){f.Smart.value=255;}
if(f.Tough.value>255){f.Tough.value=255;}
BA0=f.Cool.value;
BA0+=","+f.Beauty.value;
BA0+=","+f.Cute.value;
BA0+=","+f.Smart.value;
BA0+=","+f.Tough.value;
tcode+="\r\nContest Stats: "+BA0+"\r\n";
BA0="020";
if(r==1){BA0="120"; }
if(r==2){BA0="022"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BEA";}
 if(gver>=1 && gver<=4){BA1=BA0+"2860A";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="42305D90";}
 if(gver>=1 && gver<=4){BA1="4230500C";} 
}

if(r==0){BA2="";}else{BA2="0000";}
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA2="20CB";}
 if(gver>=1 && gver<=4){BA2="2041";}
}
BA2+=DecToHex(f.Beauty.value,2);
BA2+=DecToHex(f.Cool.value,2);
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BEC";}
 if(gver>=1 && gver<=4){BA1=BA0+"2860C";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="42305D90";}
 if(gver>=1 && gver<=4){BA1="4230500C";} 
}

if(r==0){BA2="";}else{BA2="0000";}
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA2="20CC";}
 if(gver>=1 && gver<=4){BA2="2042";}
}
BA2+=DecToHex(f.Smart.value,2);
BA2+=DecToHex(f.Cute.value,2);
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";
BA0="020";
if(r==1){BA0="020"; }
if(r==2){BA0="002"; }

if(f.Codetype.selectedIndex==0){
 if(gver==0){BA1=BA0+"28BEE";}
 if(gver>=1 && gver<=4){BA1=BA0+"2860E";}
}
if(f.Codetype.selectedIndex==1){ 
 if(gver==0){BA1="40305D90";}
 if(gver>=1 && gver<=4){BA1="4030500C";} 
}

if(r==0){BA2="";}else{BA2="000000";}
if(r==2 && f.Codetype.selectedIndex==1){
 if(gver==0){BA2="00419A";}
 if(gver>=1 && gver<=4){BA2="004086";}
}
BA2+=DecToHex(f.Tough.value,2);
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

// Location

BA0="";
BA0=f.Loc.options[f.Loc.selectedIndex].text;
tcode+="\r\n\r\nLocation: "+BA0+"\r\n";
BA0="020";
if(r==1){BA0="120"; }
if(r==2){BA0="022"; }

if(gver==0){BA1=BA0+"3BC86";}
if(gver>=1 && gver<=4){BA1=BA0+"3F3AE";}

if(r==0){BA2="";}else{BA2="0000";}
BA2+=f.Loc.options[f.Loc.selectedIndex].value;
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

// Block

tcode+="\r\nPrevent Fleeing\r\n";
BA0="020";
if(r==1){BA0="020"; }
if(r==2){BA0="002"; }

if(gver==0){BA1=BA0+"2412F";}
if(gver>=1 && gver<=4){BA1=BA0+"23C8F";}

if(r==0){BA2="";}else{BA2="000000";}
BA2+="04";
if(r==0){tt=BA1+":"+BA2;}
if(r==1){tt=GAEncrypt(BA1,BA2,"1");}
if(r==2){tt=GAEncrypt(BA1,BA2,"3");}
if(r!=0){tt=tt.substring(0,8)+" "+tt.substring(8,16);}
tcode+=tt+"\r\n";

f.Code.value=tcode;
f.LogC.value=tlog+"Done.";
}

function IsCode(C){
var e=0;
e=0;
if(C=="0"){e=1;}
if(C=="1"){e=1;}
if(C=="2"){e=1;}
if(C=="3"){e=1;}
if(C=="4"){e=1;}
if(C=="5"){e=1;}
if(C=="6"){e=1;}
if(C=="7"){e=1;}
if(C=="8"){e=1;}
if(C=="9"){e=1;}
if(C=="a"){e=1;}
if(C=="b"){e=1;}
if(C=="c"){e=1;}
if(C=="d"){e=1;}
if(C=="e"){e=1;}
if(C=="f"){e=1;}
if(C=="A"){e=1;}
if(C=="B"){e=1;}
if(C=="C"){e=1;}
if(C=="D"){e=1;}
if(C=="E"){e=1;}
if(C=="F"){e=1;}
if(C.charCodeAt(0)==13){e=2;}
if(C.charCodeAt(0)==10){e=2;}
if(C==" "){e=2;}
if(C==":"){e=2;}
return e;
}

function NewDex(i){
var f=document.PokemonForm;
var t=" ";
var x=0;
var pgn=0;
var pdex=" ";
pgn=f.Species.options[f.Species.selectedIndex].value;
if(pgn<1){pgn=1;}
pdex=PokeDex(pgn);
// i=f.Dex.selectedIndex;
if(i==0){x=pgn;}
if(i==1){t=FI(pdex,"~",2); x=parseInt(t,10);}
if(i==2){t=FI(pdex,"~",1); x=parseInt(t,10);}
f.PNum.value=x;
SortPoke(i);
return x;
}

function PokeByNum(){
var f=document.PokemonForm;
// Removes non-values and compensates for the gap of 26 numbers
if(f.PNum.value<0){f.PNum.value=0;}
if(f.Dex.selectedIndex==0){
 if(f.PNum.value>251 && f.PNum.value<277){f.PNum.value=0;}
 if(f.PNum.value>=277){f.PNum.value-=25;}
 if(f.PNum.value>411){f.PNum.value=0;}
}
if(f.Dex.selectedIndex==1){
 if(f.PNum.value>202){f.PNum.value=0;}  
}
if(f.Dex.selectedIndex==2){
 if(f.PNum.value>386){f.PNum.value=0;}   
}
f.Species.selectedIndex=f.PNum.value;  // Jump to the pokemon with that Dex number
NewPoke();
}

function NewPoke(){
var f=document.PokemonForm;
var t=" ";
var u=" ";
var v=" ";
var w=" ";
var x=0;
var i=0;
var pgn=0;
var pdex=" ";
pgn=f.Species.options[f.Species.selectedIndex].value;
// Randomizes pokemon selection if dex PNum value is zero
if(pgn<1){
 if(f.Dex.selectedIndex==0 || f.Dex.selectedIndex==2){pgn=Math.floor(Math.random()*386)+1; f.Species.selectedIndex=pgn;}
 if(f.Dex.selectedIndex==1){pgn=Math.floor(Math.random()*200)+1; f.Species.selectedIndex=pgn;}
 pgn=f.Species.options[f.Species.selectedIndex].value;
}  
pdex=PokeDex(pgn);
i=f.Dex.selectedIndex;
if(i==0){x=pgn;}
if(i==1){t=FI(pdex,"~",2); x=parseInt(t,10);}
if(i==2){t=FI(pdex,"~",1); x=parseInt(t,10);}
f.PNum.value=x;
t=SetGender();
i=HPower();
if(pgn==290){
 var hpid=Math.floor(f.PID.value/0x10000);
 var tw=Math.floor(hpid%10);
 if(tw<0){tw+=10;}
 f.WurmEvo.selectedIndex=(tw<5)?0:1; // 0=Silcoon, 1=Cascoon
}
SpecialPoke();
EnablePID();
}

function SpecialPoke(){
var f=document.PokemonForm;
var pgn=f.Species.options[f.Species.selectedIndex].value;
f.Unown.disabled=(pgn==201)?false:true;
f.Unown.style.background=(pgn==201)?'':'#DFDFDF';
document.getElementById("wurmple").style.display=(pgn==290)?"block":"none";
document.getElementById("spinda").style.display=(pgn==308)?"block":"none";
if(pgn==290 || pgn==308){
 f.Code.rows=26;
}else{
 f.Code.rows=25;
}  
if(f.MPID.checked){f.Code.rows=27;}
}

function SortPoke(o){
var f=document.PokemonForm;
var P1=f.Species;
var ln=" "; 
var l=0; var m=0; var w=0; var t=" "; var t2=" ";
var tn=0; var tname=" ";
//o=f.Dex.selectedIndex;
// Hoen
if(o==1){
ln="~277~278~279~280~281~282~283~284~285~286~287~288~289~290~291~292~293~294~295~296";
ln+="~297~298~299~300~304~305~309~310~392~393~394~311~312~306~307~364~365~366~63~64";
ln+="~65~301~302~303~370~371~372~335~336~118~119~129~130~350~183~184~74~75~76~320";
ln+="~315~316~41~42~169~72~73~322~355~382~383~384~66~67~68~356~357~337~338~353";
ln+="~354~81~82~100~101~386~387~43~44~45~182~84~85~363~367~368~330~331~313~314";
ln+="~339~340~218~219~321~88~89~109~110~351~352~27~28~308~227~332~333~334~344~345";
ln+="~358~359~380~379~348~349~323~324~326~327~318~319~388~389~390~391~174~39~40~328";
ln+="~329~385~120~121~317~377~378~361~362~369~411~376~37~38~172~25~26~54~55~360";
ln+="~202~177~178~203~231~232~127~214~111~112~346~347~341~342~343~373~374~375~381~222";
ln+="~170~171~325~116~117~230~395~396~397~398~399~400~401~402~403~407~408~404~405~406";
ln+="~409~410~-1~";}
// National
if(o==2){
/*  This portion is done automatically now
ln="~1~2~3~4~5~6~7~8~9~10~11~12~13~14~15~16~17~18~19~20";
ln+="~21~22~23~24~25~26~27~28~29~30~31~32~33~34~35~36~37~38~39~40";
ln+="~41~42~43~44~45~46~47~48~49~50~51~52~53~54~55~56~57~58~59~60";
ln+="~61~62~63~64~65~66~67~68~69~70~71~72~73~74~75~76~77~78~79~80";
ln+="~81~82~83~84~85~86~87~88~89~90~91~92~93~94~95~96~97~98~99~100";
ln+="~101~102~103~104~105~106~107~108~109~110~111~112~113~114~115~116~117~118~119~120";
ln+="~121~122~123~124~125~126~127~128~129~130~131~132~133~134~135~136~137~138~139~140";
ln+="~141~142~143~144~145~146~147~148~149~150~151~152~153~154~155~156~157~158~159~160";
ln+="~161~162~163~164~165~166~167~168~169~170~171~172~173~174~175~176~177~178~179~180";
ln+="~181~182~183~184~185~186~187~188~189~190~191~192~193~194~195~196~197~198~199~200";
ln+="~201~202~203~204~205~206~207~208~209~210~211~212~213~214~215~216~217~218~219~220";
ln+="~221~222~223~224~225~226~227~228~229~230~231~232~233~234~235~236~237~238~239~240";
ln+="~241~242~243~244~245~246~247~248~249~250~251";
*/
ln="~277~278~279~280~281~282~283~284~285~286~287~288~289~290~291~292~293~294~295~296";
ln+="~297~298~299~300~304~305~309~310~392~393~394~311~312~306~307~364~365~366~301~302";
ln+="~303~370~371~372~335~336~350~320~315~316~322~355~382~383~384~356~357~337~338~353";
ln+="~354~386~387~363~367~368~330~331~313~314~339~340~321~351~352~308~332~333~334~344";
ln+="~345~358~359~380~379~348~349~323~324~326~327~318~319~388~389~390~391~328~329~385";
ln+="~317~377~378~361~362~369~411~376~360~346~347~341~342~343~373~374~375~381~325~395";
ln+="~396~397~398~399~400~401~402~403~407~408~404~405~406~409~410~-1~";}

l=0;
m=0;
w=0;
f.Species.options.length=0;
while(l==0){
 if(o==0){
  if(w==252){w+=25;}
  if(w>411){w=-1;}
  t=parseInt(w,10);
 }else if(o==2){
  if(w>=0 && w<252){t=parseInt(w,10);}  // Creates Kanto and Johto pokemon portion
  if(w>=252){t=FI(ln,"~",w-251);}  // Looks up remaining pokemon
 }else{
  t=FI(ln,"~",w);
 }
 w+=1;
 if(t=="-1"){
  f.Species.options.length=m;
  f.Species.selectedIndex=1;
  t=NewPoke();
  l=1;  // ends while loop
 }else{
  tn=1*t;
  t2=PokeDex(tn);
  tname=FI(t2,"~",3);
  if(t<10){t="00"+t;}else if(t<100){t="0"+t;
  }else{t=t;}
  if(m==1){
   f.Species.options[m]= new Option(tname,t,true);
  }else{
   f.Species.options[m]= new Option(tname,t);
  }
  m+=1;
 }
}
f.Species.focus();
return t;
}


/* -------------
function SetAll(tlog){  //not needed
var d=document;
var f=d.PokemonForm;
var G=f.PGender;
var ga=0;
var x=0;
var t=" ";
var dna=" ";
var D=f.RDNA;
t=SetDNA();
dna=f.DNA.value;
ga=parseInt(1*("0x"+D[0].value),10);
f.PID.value=ga;
ga=Math.floor((1*("0x"+ga))%256);
gt=Gtest();
if(ga>=gt){ga=1;}else{ga=0;}
G.selectedIndex=ga;
x=(1*("0x"+D[1].value))%65536;
if(x<1){x=0;}
f.TID.value=parseInt(x,10);
x=(1*("0x"+D[1].value))/65536;
if(x<1){x=0;}
f.STID.value=parseInt(x,10);
f.PName.value=PToS(dna.substring(16,36),10);
t=D[4].value;
f.PFont.value=t.substring(0,4);
f.TName.value=PToS(dna.substring(40,54),7);
t=Marks((1*("0x"+dna.substring(55,56))));
t=SetNature();
t=SetXKey();
t=SetShiny();
t=SetUnown();
t=SetGender();
return tlog;
}
------------- */


function SetShiny(){
var f=document.PokemonForm;
var X=f.XKey;
var wh=0;
var wl=0;
var dw=0;
var t=" ";
var i=0;
dw=1*("0x"+X.value);
wh=Math.floor(dw/65536);
wl=Math.floor(dw%65536);
i=wl^wh;
if(i<0){i+=1*("0x100000000")};
if(i<8){
 f.Shiny.checked=true;
 t="Shiny";
}else{
 f.Shiny.checked=false;
 t="Normal";
}
return t;
}

function SetXKey(){  //not needed
var f=document.PokemonForm;
var D=f.RDNA;
var X=f.XKey;
var tid=0;
var pid=0;
var xk=0;
var t=" ";
pid=parseInt(1*("0x"+D[0].value),10);
tid=parseInt(1*("0x"+D[1].value),10);
xk=Math.floor(pid^tid);
if(xk<0){xk+=1*"0x100000000";}
t=DecToHex(xk,8);
X.value=t;
return t;
}

function SetUnown(){
var f=document.PokemonForm;
var D=f.RDNA;
var U=f.Unown;
var pid=0;
var s=0;
var t=" ";
var US=" ";
pid=parseInt(1*("0x"+D[0].value),10);
s=Math.floor(pid%4);
s+=(Math.floor(pid/256)%4)*4;
s+=(Math.floor(pid/65536)%4)*16;
s+=(Math.floor(pid/16777216)%4)*64;
t = Math.floor(s % 28);
if(t==0){US="A";}
if(t==1){US="B";}
if(t==2){US="C";}
if(t==3){US="D";}
if(t==4){US="E";}
if(t==5){US="F";}
if(t==6){US="G";}
if(t==7){US="H";}
if(t==8){US="I";}
if(t==9){US="J";}
if(t==10){US="K";}
if(t==11){US="L";}
if(t==12){US="M";}
if(t==13){US="N";}
if(t==14){US="O";}
if(t==15){US="P";}
if(t==16){US="Q";}
if(t==17){US="R";}
if(t==18){US="S";}
if(t==19){US="T";}
if(t==20){US="U";}
if(t==21){US="V";}
if(t==22){US="W";}
if(t==23){US="X";}
if(t==24){US="Y";}
if(t==25){US="Z";}
if(t==26){US="!";}
if(t==27){US="?";}
U.selectedIndex=t;
return US;
}

function SetNature(){
var f=document.PokemonForm;
var pid=0;
var D=f.RDNA;
var N=f.Nature;
var n=0;
pid=parseInt(1*("0x"+D[0].value),10);
n=Math.floor(pid%25);
N.selectedIndex=n;
return n;
}

function SetGender(){
var f=document.PokemonForm;
var G=f.PGender;
var pdex=" ";
var pgn=0;
var t=" ";
var g=0;
var x=0;
var o=0;
// g=Math.floor(f.PID.value/128)%2;
pgn=f.Species.options[f.Species.selectedIndex].value;
pdex=PokeDex(pgn);
x=FI(pdex,"~",20);
o=G.selectedIndex;
G.options.length=0;
if(x==-1){
 G.options[0] = new Option("None","0",true);
 G.options[1] = new Option("None","1");
 t="None";
}
if(x==100){
 G.options[0] = new Option("Female","0",true);
 G.options[1] = new Option("Female","1");
}
if(x==0){
 G.options[0] = new Option("Male","0",true);
 G.options[1] = new Option("Male","1");
}
if(x!=-1&&x!=100&&x!=0){
 G.options[0] = new Option("Female","0",true);
 G.options[1] = new Option("Male","1");
 if(g==0){t="Female";}
 if(g==1){t="Male";}
}
G.options.length=2;
G.selectedIndex=o;
return t;
}


function Set_ID(form){
// Write to Cookie
var f=document.PokemonForm;
var expdate = new Date ();
expdate.setTime (expdate.getTime() + (24 * 60 * 60 * 1000 * 31));
var tid = f.TID.value;
var stid = f.STID.value;
  if (tid && stid != ""){
    if (confirm("This will remember your Trainer ID and Secret ID for next time.")){
      SetCookie ("TrainerID", tid, expdate);
      SetCookie ("SecretID", stid, expdate);
    }
  }else alert("Invalid entry! Nothing to save.");
}

function Show_ID() {
// Read from Cookie
var f=document.PokemonForm;
  if(GetCookie("TrainerID") != null && GetCookie("SecretID") != null){
    f.TID.value=GetCookie('TrainerID');  
    f.STID.value=GetCookie('SecretID');
  }else{ 
    f.TID.value="0";  
    f.STID.value="0";
  }
}


// end -->
</SCRIPT>

<noscript>
<table border="2" cellpadding="6" width="400" height="120" bordercolor="#666666" style="border-style: solid; border-width: 2">
  <tr>
    <td valign="middle" bgcolor="#FFFFEC"> 
      <p align="center"><font size="+1">ERROR</font></p>
      <p>JavaScript is disabled in your browser and thus this form will 
        not work. Please enable javascript and try again.</p> 
    </td>
  </tr>
</table>
<BR>
</noscript>

<FORM name=PokemonForm bgColor="#d0d0d0">

  <div id="Layer1" style="position: absolute; width: 208; height: 76; z-index: 2; left: 125; top: 660; overflow: hidden; visibility: hidden"> 
    <table cellspacing=0 cols=2 cellpadding=3 width="200" height="20" bgcolor=#DFDFDF 
	 border=0 style="border-style: outset; border-width: 3">
      <tbody> 
      <tr> 
        <td>&nbsp;XKey: 
          <input maxlength=10 size=10 name=XKey>
        </td>
      </tr>
      </tbody> 
    </table>
  </div>
  
  <div id="Layer2" style="position:absolute; width:210px; height:20px; z-index:1; left: 120px; top: 518px; visibility: hidden"> 
    <table cellspacing=0 cols=2 cellpadding=3 width="209" height="20" bgcolor=#DFDFDF 
    border=0 style="border-style: outset; border-width: 3">
      <tbody> 
      <tr> 
        <td height="20" nowrap>MAP: 
          <input maxlength=20 name=PID size="20">
        </td>
      </tr>
      </tbody> 
    </table>
  </div>
  
  <div id="Layer3" style="position:absolute; width:143px; height:70px; z-index:3; left: 130px; top: 445px; visibility: hidden"> 
    <textarea name="LogC" rows="1" cols="20"></textarea>
  </div>
  
  <TABLE class="first" cellSpacing=0 cols=2 cellPadding=3 width=600 height="500" bgColor=#DFDFDF border=0>
    <TBODY> 
    <TR bgcolor="#4570C7">      
      <TD colSpan=4 height="19" style="padding:0; FILTER: progid:DXImageTransform.Microsoft.Gradient(startColorStr='#003399', endColorStr='#9BBCFF', gradientType='1')">
      <div class="gradient 003399 9BBCFF horizontal" style="position:relative; padding:3">
        <B><font color="#FFFFFF">Pokemon Encounter Code Generator&nbsp;&nbsp;1.5.1</font></B>
      </div>
      </TD>        
    </TR>
    <TR> 
      <TD height="8" width="1"></TD>
      <TD height="8" width="197"></TD>
      <TD height="8" colspan="2"></TD>
    </TR>
    <TR> 
      <TD rowspan="12" width="1">&nbsp;</TD>
      <TD rowspan="12" width="197"> 
        <TEXTAREA name=Code rows=25 cols=34></TEXTAREA>
      </TD>
      <td colspan="2"><b>Trainer Info: </b>(only required for shiny) </td>
    </TR>
    <TR> 
      <td class="ridge" style="border-left-style: ridge; border-left-width: 3; border-right-style: ridge; border-right-width: 3; border-top-style: ridge; border-top-width: 3" nowrap>
        Trainer ID: 
        <input maxlength=7 size=7 value=0 name=TID onchange="TestNumerical()">&nbsp;&nbsp; 
      </td>
      <td rowspan="2" style="padding-left:20px; padding-right:20px"> 
          <input type="button" value="Save IDs" onClick="Set_ID(this.form)" name="button">
      </td>
    </TR>
    <TR> 
      <td class="ridge" style="border-left-style: ridge; border-left-width: 3; border-right-style: ridge; border-right-width: 3; border-bottom-style: ridge; border-bottom-width: 3" nowrap>
        Secret ID: 
        <input maxlength=7 size=7 value=0 name=STID onchange="TestNumerical()" style="position: relative; left: 4">&nbsp;&nbsp; 
      </td>
    </TR>
    <TR> 
      <td class="btmgroove" colspan="2" style="border-bottom-style: groove; border-bottom-width: 2">&nbsp; 
      </td>
    </TR>
    <TR> 
      <TD colspan="2"><b>Pokemon Info:</b> &nbsp; </TD>
    </TR>
    <TR> 
      <TD colspan="2">PokeDex: 
        <select onChange="NewDex(this.selectedIndex); EnablePID()" name=Dex>
          <option value=G selected>Game 
          <option value=H>Hoen 
          <option value=N>National</option>
        </select>
        <input name=PNum size=3 value="001" maxlength=3 type="text" onDblClick="javascript: this.value=''; return false;" onKeyDown="KeyListener(event, this)" onBlur="PokeByNum(); EnablePID()" style="border-style: inset; border-width: 2">
        <div id="arrow" style="position: relative; left: 0px; top: 5px; height: 7px; display: inline">
          <div id="arrow_top" style="position: absolute; left: 6px; top: 0px; width: 1px; height: 1px; background-color: rgb(0, 0, 0); overflow: hidden"></div>
          <div id="arrow_head" style="position: absolute; left: 4px; top: 1px; width: 3px; height: 5px; background-color: rgb(0, 0, 0); overflow: hidden"></div>
          <div id="arrow_tail" style="position: absolute; left: 2px; top: 2px; width: 15px; height: 3px; background-color: rgb(0, 0, 0); overflow: hidden"></div>
          <div id="arrow_tip" style="position: absolute; left: 0px; top: 3px; width: 2px; height: 1px; background-color: rgb(0, 0, 0); overflow: hidden"></div>
          <div id="arrow_btm" style="position: absolute; left: 6px; top: 6px; width: 1px; height: 1px; background-color: rgb(0, 0, 0); overflow: hidden"></div>
        &nbsp;</div>
        <span style="position: relative; left: 14px; display: inline"><i>&nbsp;jump-to</i></span>
      </TD>
    </TR>
    <TR> 
      <TD colspan="2">Pokemon: 
        <select name="Species" onChange="NewPoke()" onKeyUp="NewPoke()">
          <option value="000"> 
          <option selected value="001">leaflet
          <option value="002">graztren
          <option value="003">grassolot
          <option value="004">Charmander 
          <option value="005">Charmeleon 
          <option value="006">Charizard 
          <option value="007">Squirtle 
          <option value="008">Wartortle 
          <option value="009">Blastoise 
          <option value="010">Caterpie 
          <option value="011">Metapod 
          <option value="012">Butterfree 
          <option value="013">Weedle 
          <option value="014">Kakuna 
          <option value="015">Beedrill 
          <option value="016">Pidgey 
          <option value="017">Pidgeotto 
          <option value="018">Pidgeot 
          <option value="019">Rattata 
          <option value="020">Raticate 
          <option value="021">Spearow 
          <option value="022">Fearow 
          <option value="023">Ekans 
          <option value="024">Arbok 
          <option value="025">Pikachu 
          <option value="026">Raichu 
          <option value="027">Sandshrew 
          <option value="028">Sandslash 
          <option value="029">Nidoran Female 
          <option value="030">Nidorina 
          <option value="031">Nidoqueen 
          <option value="032">Nidoran Male 
          <option value="033">Nidorino 
          <option value="034">Nidoking 
          <option value="035">Clefairy 
          <option value="036">Clefable 
          <option value="037">Vulpix 
          <option value="038">Ninetales 
          <option value="039">Jigglypuff 
          <option value="040">Wigglytuff 
          <option value="041">Zubat 
          <option value="042">Golbat 
          <option value="043">Oddish 
          <option value="044">Gloom 
          <option value="045">Vileplume 
          <option value="046">Paras 
          <option value="047">Parasect 
          <option value="048">Venonat 
          <option value="049">Venomoth 
          <option value="050">Diglett 
          <option value="051">Dugtrio 
          <option value="052">Meowth 
          <option value="053">Persian 
          <option value="054">Psyduck 
          <option value="055">Golduck 
          <option value="056">Mankey 
          <option value="057">Primeape 
          <option value="058">Growlithe 
          <option value="059">Arcanine 
          <option value="060">Poliwag 
          <option value="061">Poliwhirl 
          <option value="062">Poliwrath 
          <option value="063">Abra 
          <option value="064">Kadabra 
          <option value="065">Alakazam 
          <option value="066">Machop 
          <option value="067">Machoke 
          <option value="068">Machamp 
          <option value="069">Bellsprout 
          <option value="070">Weepinbell 
          <option value="071">Victreebel 
          <option value="072">Tentacool 
          <option value="073">Tentacruel 
          <option value="074">Geodude 
          <option value="075">Graveler 
          <option value="076">Golem 
          <option value="077">Ponyta 
          <option value="078">Rapidash 
          <option value="079">Slowpoke 
          <option value="080">Slowbro 
          <option value="081">Magnemite 
          <option value="082">Magneton 
          <option value="083">Farfetch'D 
          <option value="084">Doduo 
          <option value="085">Dodrio 
          <option value="086">Seel 
          <option value="087">Dewgong 
          <option value="088">Grimer 
          <option value="089">Muk 
          <option value="090">Shellder 
          <option value="091">Cloyster 
          <option value="092">Gastly 
          <option value="093">Haunter 
          <option value="094">Gengar 
          <option value="095">Onix 
          <option value="096">Drowzee 
          <option value="097">Hypno 
          <option value="098">Krabby 
          <option value="099">Kingler 
          <option value="100">Voltorb 
          <option value="101">Electrode 
          <option value="102">Exeggcute 
          <option value="103">Exeggutor 
          <option value="104">Cubone 
          <option value="105">Marowak 
          <option value="106">Hitmonlee 
          <option value="107">Hitmonchan 
          <option value="108">Lickitung 
          <option value="109">Koffing 
          <option value="110">Weezing 
          <option value="111">Rhyhorn 
          <option value="112">Rhydon 
          <option value="113">Chansey 
          <option value="114">Tangela 
          <option value="115">Kangaskhan 
          <option value="116">Horsea 
          <option value="117">Seadra 
          <option value="118">Goldeen 
          <option value="119">Seaking 
          <option value="120">Staryu 
          <option value="121">Starmie 
          <option value="122">Mr.Mime 
          <option value="123">Scyther 
          <option value="124">Jynx 
          <option value="125">Electabuzz 
          <option value="126">Magmar 
          <option value="127">Pinsir 
          <option value="128">Tauros 
          <option value="129">Magikarp 
          <option value="130">Gyarados 
          <option value="131">Lapras 
          <option value="132">Ditto 
          <option value="133">Eevee 
          <option value="134">Vaporeon 
          <option value="135">Jolteon 
          <option value="136">Flareon 
          <option value="137">Porygon 
          <option value="138">Omanyte 
          <option value="139">Omastar 
          <option value="140">Kabuto 
          <option value="141">Kabutops 
          <option value="142">Aerodactyl 
          <option value="143">Snorlax 
          <option value="144">Articuno 
          <option value="145">Zapdos 
          <option value="146">Moltres 
          <option value="147">Dratini 
          <option value="148">Dragonair 
          <option value="149">Dragonite 
          <option value="150">Mewtwo 
          <option value="151">Mew 
          <option value="152">Chikorita 
          <option value="153">Bayleef 
          <option value="154">Meganium 
          <option value="155">Cyndaquil 
          <option value="156">Quilava 
          <option value="157">Typhlosion 
          <option value="158">Totodile 
          <option value="159">Croconaw 
          <option value="160">Feraligatr 
          <option value="161">Sentret 
          <option value="162">Furret 
          <option value="163">Hoothoot 
          <option value="164">Noctowl 
          <option value="165">Ledyba 
          <option value="166">Ledian 
          <option value="167">Spinarak 
          <option value="168">Ariados 
          <option value="169">Crobat 
          <option value="170">Chinchou 
          <option value="171">Lanturn 
          <option value="172">Pichu 
          <option value="173">Cleffa 
          <option value="174">Igglybuff 
          <option value="175">Togepi 
          <option value="176">Togetic 
          <option value="177">Natu 
          <option value="178">Xatu 
          <option value="179">Mareep 
          <option value="180">Flaaffy 
          <option value="181">Ampharos 
          <option value="182">Bellossom 
          <option value="183">Marill 
          <option value="184">Azumarill 
          <option value="185">Sudowoodo 
          <option value="186">Politoed 
          <option value="187">Hoppip 
          <option value="188">Skiploom 
          <option value="189">Jumpluff 
          <option value="190">Aipom 
          <option value="191">Sunkern 
          <option value="192">Sunflora 
          <option value="193">Yanma 
          <option value="194">Wooper 
          <option value="195">Quagsire 
          <option value="196">Espeon 
          <option value="197">Umbreon 
          <option value="198">Murkrow 
          <option value="199">Slowking 
          <option value="200">Misdreavus 
          <option value="201">Unown 
          <option value="202">Wobbuffet 
          <option value="203">Girafarig 
          <option value="204">Pineco 
          <option value="205">Forretress 
          <option value="206">Dunsparce 
          <option value="207">Gligar 
          <option value="208">Steelix 
          <option value="209">Snubbull 
          <option value="210">Granbull 
          <option value="211">Qwilfish 
          <option value="212">Scizor 
          <option value="213">Shuckle 
          <option value="214">Heracross 
          <option value="215">Sneasel 
          <option value="216">Teddiursa 
          <option value="217">Ursaring 
          <option value="218">Slugma 
          <option value="219">Magcargo 
          <option value="220">Swinub 
          <option value="221">Piloswine 
          <option value="222">Corsola 
          <option value="223">Remoraid 
          <option value="224">Octillery 
          <option value="225">Delibird 
          <option value="226">Mantine 
          <option value="227">Skarmory 
          <option value="228">Houndour 
          <option value="229">Houndoom 
          <option value="230">Kingdra 
          <option value="231">Phanpy 
          <option value="232">Donphan 
          <option value="233">Porygon2 
          <option value="234">Stantler 
          <option value="235">Smeargle 
          <option value="236">Tyrogue 
          <option value="237">Hitmontop 
          <option value="238">Smoochum 
          <option value="239">Elekid 
          <option value="240">Magby 
          <option value="241">Miltank 
          <option value="242">Blissey 
          <option value="243">Raikou 
          <option value="244">Entei 
          <option value="245">Suicune 
          <option value="246">Larvitar 
          <option value="247">Pupitar 
          <option value="248">Tyranitar 
          <option value="249">Lugia 
          <option value="250">Ho-Oh 
          <option value="251">Celebi 
          <option value="277">Treecko 
          <option value="278">Grovyle 
          <option value="279">Sceptile 
          <option value="280">Torchic 
          <option value="281">Combusken 
          <option value="282">Blaziken 
          <option value="283">Mudkip 
          <option value="284">Marshtomp 
          <option value="285">Swampert 
          <option value="286">Poochyena 
          <option value="287">Mightyena 
          <option value="288">Zigzagoon 
          <option value="289">Linoone 
          <option value="290">Wurmple 
          <option value="291">Silcoon 
          <option value="292">Beautifly 
          <option value="293">Cascoon 
          <option value="294">Dustox 
          <option value="295">Lotad 
          <option value="296">Lombre 
          <option value="297">Ludicolo 
          <option value="298">Seedot 
          <option value="299">Nuzleaf 
          <option value="300">Shiftry 
          <option value="301">Nincada 
          <option value="302">Ninjask 
          <option value="303">Shedinja 
          <option value="304">Taillow 
          <option value="305">Swellow 
          <option value="306">Shroomish 
          <option value="307">Breloom 
          <option value="308">Spinda 
          <option value="309">Wingull 
          <option value="310">Pelipper 
          <option value="311">Surskit 
          <option value="312">Masquerain 
          <option value="313">Wailmer 
          <option value="314">Wailord 
          <option value="315">Skitty 
          <option value="316">Delcatty 
          <option value="317">Kecleon 
          <option value="318">Baltoy 
          <option value="319">Claydol 
          <option value="320">Nosepass 
          <option value="321">Torkoal 
          <option value="322">Sableye 
          <option value="323">Barboach 
          <option value="324">Whiscash 
          <option value="325">Luvdisc 
          <option value="326">Corphish 
          <option value="327">Crawdaunt 
          <option value="328">Feebas 
          <option value="329">Milotic 
          <option value="330">Carvanha 
          <option value="331">Sharpedo 
          <option value="332">Trapinch 
          <option value="333">Vibrava 
          <option value="334">Flygon 
          <option value="335">Makuhita 
          <option value="336">Hariyama 
          <option value="337">Electrike 
          <option value="338">Manectric 
          <option value="339">Numel 
          <option value="340">Camerupt 
          <option value="341">Spheal 
          <option value="342">Sealeo 
          <option value="343">Walrein 
          <option value="344">Cacnea 
          <option value="345">Cacturne 
          <option value="346">Snorunt 
          <option value="347">Glalie 
          <option value="348">Lunatone 
          <option value="349">Solrock 
          <option value="350">Azurill 
          <option value="351">Spoink 
          <option value="352">Grumpig 
          <option value="353">Plusle 
          <option value="354">Minun 
          <option value="355">Mawile 
          <option value="356">Meditite 
          <option value="357">Medicham 
          <option value="358">Swablu 
          <option value="359">Altaria 
          <option value="360">Wynaut 
          <option value="361">Duskull 
          <option value="362">Dusclops 
          <option value="363">Roselia 
          <option value="364">Slakoth 
          <option value="365">Vigoroth 
          <option value="366">Slaking 
          <option value="367">Gulpin 
          <option value="368">Swalot 
          <option value="369">Tropius 
          <option value="370">Whismur 
          <option value="371">Loudred 
          <option value="372">Exploud 
          <option value="373">Clamperl 
          <option value="374">Huntail 
          <option value="375">Gorebyss 
          <option value="376">Absol 
          <option value="377">Shuppet 
          <option value="378">Banette 
          <option value="379">Seviper 
          <option value="380">Zangoose 
          <option value="381">Relicanth 
          <option value="382">Aron 
          <option value="383">Lairon 
          <option value="384">Aggron 
          <option value="385">Castform 
          <option value="386">Volbeat 
          <option value="387">Illumise 
          <option value="388">Lileep 
          <option value="389">Cradily 
          <option value="390">Anorith 
          <option value="391">Armaldo 
          <option value="392">Ralts 
          <option value="393">Kirlia 
          <option value="394">Gardevoir 
          <option value="395">Bagon 
          <option value="396">Shelgon 
          <option value="397">Salamence 
          <option value="398">Beldum 
          <option value="399">Metang 
          <option value="400">Metagross 
          <option value="401">Regirock 
          <option value="402">Regice 
          <option value="403">Registeel 
          <option value="404">Kyogre 
          <option value="405">Groudon 
          <option value="406">Rayquaza 
          <option value="407">Latias 
          <option value="408">Latios 
          <option value="409">Jirachi 
          <option value="410">Deoxys 
          <option value="411">Chimecho 
          <option value="412">griflet
           <option value="413">griftrix
             <option value="414">griflon
            <option value="415">vaporit
   <option value="416">vaporis
  <option value="417">vaptix
</select>
        <div id="wurmple" name="wurmple" style="padding-top: 7px; display: none">Evolves Into: 
          <select size="1" name="WurmEvo">
            <option selected value="0">Silcoon</option>
            <option value="1">Cascoon</option>
          </select> 
          <input type="text" name="WurmVal" size="4" style="display: none"> 
        </div>
        <div id="spinda" name="spinda" style="padding-top: 7px; display: none">Define Spots?
          <input type=checkbox value=0 name=MPID onClick="EnablePID()"> 
          <input maxlength=20 value="0" name=UserPID size="10" onChange="EvalPID(); FillAll()" onKeyUp="KeyListener(event, this)" style="background-color: #DFDFDF" disabled>
          <br>
          <span id="radix" name="radix" style="position:relative; left:110; display:none">
            <label><input onClick="EvalPID()" type="radio" name="base" value="Dec" checked><code>Dec</code></label> 
            <label><input onClick="EvalPID()" type="radio" name="base" value="Hex"><code>Hex</code></label>
          </span>
        </div>         
      </TD>
    </TR>
    <TR> 
      <TD colspan="2">Shiny: 
        <input type=checkbox onChange=NewPoke() value=0 name=Shiny>
        Gender: 
        <select name=PGender size="1">
          <option value=Female selected>Female 
          <option value=Male>Male</option>
        </select>
      </TD>
    </TR>
    <TR> 
      <TD colspan="2">Level: 
        <input maxlength=3 onChange='XQ("X")' onKeyDown="KeyListener(event, this)" size=3 value=1 name=XLvl>
        &nbsp;Unown: 
        <select onChange=NewPoke() name=Unown style="background-color: #DFDFDF" disabled>
          <option value=a>A 
          <option value=b>B 
          <option value=c>C 
          <option value=d>D 
          <option value=e>E 
          <option value=f>F 
          <option value=g>G 
          <option value=h>H 
          <option value=i>I 
          <option value=j>J 
          <option value=k>K 
          <option value=l>L 
          <option value=m>M 
          <option value=n>N 
          <option value=o>O 
          <option value=p>P 
          <option value=q>Q 
          <option value=r>R 
          <option value=s>S 
          <option value=t>T 
          <option value=u>U 
          <option value=v>V 
          <option value=w>W 
          <option value=x>X 
          <option value=y>Y 
          <option value=z>Z 
          <option value=ep>! 
          <option value=qm selected>?</option>
        </select>&nbsp; 
      </TD>
    </TR>
    <TR> 
      <TD colspan="2">Nature: 
        <select onChange=HPower() name=Nature>
          <option value=00 selected>Hardy (=) 
          <option value=01>Lonely (+Atk/-Def) 
          <option value=02>Brave (+Atk/ -Spe) 
          <option value=03>Adamant (+Atk/-SpA) 
          <option value=04>Naughty (+Atk/-SpD) 
          <option value=05>Bold (+Def/-Atk) 
          <option value=06>Docile (=) 
          <option value=07>Relaxed (+Def/-Spe) 
          <option value=08>Impish (+Def/-SpA) 
          <option value=09>Lax (+Def/-SpD) 
          <option value=0A>Timid (+Spe/-Atk) 
          <option value=0B>Hasty (+Spe/-Def) 
          <option value=0C>Serious (=) 
          <option value=0D>Jolly (+Spe/-SpA) 
          <option value=0E>Naive (+Spe/-SpD) 
          <option value=0F>Modest (+SpA/-Atk) 
          <option value=10>Mild (+SpA/-Def) 
          <option value=11>Quiet (+SpA/-Spe) 
          <option value=12>Bashful (=) 
          <option value=13>Rash (+SpA/-SpD) 
          <option value=14>Calm (+SpD/-Atk) 
          <option value=15>Gentle (+SpD/-Def) 
          <option value=16>Sassy (+SpD/-Spe) 
          <option value=17>Careful (+SpD/-SpA) 
          <option value=18>Quirky (=)</option>
           <option value=19>Shy (+SpD/-SpA) 
            </select>
      </TD>
    </TR>
    <TR> 
      <TD colspan="2">Location:
          <select name=Loc>
          <option value=1000 selected>Route 101 
          <option value=1100>Route 102 
          <option value=1200>Route 103 
          <option value=1300>Route 104 
          <option value=1400>Route 105 
          <option value=1500>Route 106 
          <option value=1600>Route 107 
          <option value=1700>Route 108 
          <option value=1800>Route 109 
          <option value=1900>Route 110 
          <option value=1A00>Route 111 (Desert) 
          <option value=1B00>Route 112 
          <option value=1C00>Route 113 
          <option value=1D00>Route 114 
          <option value=1E00>Route 115 
          <option value=1F00>Route 116 
          <option value=2000>Route 117 
          <option value=2100>Route 118 
          <option value=2200>Route 119 
          <option value=2300>Route 120 
          <option value=2400>Route 121 
          <option value=2500>Route 122 
          <option value=2600>Route 123 
          <option value=2700>Route 124 
          <option value=2800>Route 125 
          <option value=2900>Route 126 
          <option value=2A00>Route 127 
          <option value=2B00>Route 128 
          <option value=2C00>Route 129 
          <option value=2D00>Route 130 
          <option value=2E00>Route 131 
          <option value=2F00>Route 132 
          <option value=3000>Route 133 
          <option value=3100>Route 134 
          <option value=0018>Meteor Falls 1 
          <option value=0118>Meteor Falls 2 
          <option value=0218>Meteor Falls 3 
          <option value=0318>Meteor Falls 4 
          <option value=6B18>Meteor Falls (Steven) 
          <option value=0418>Rusturf Tunnel 
          <option value=0718>Granite Cave 1 
          <option value=0818>Granite Cave 2 
          <option value=0918>Granite Cave 3 
          <option value=0A18>Granite Cave 4 (Steven) 
          <option value=0B18>Petalburg Woods 
          <option value=0D18>Jagged Pass 
          <option value=0E18>Fiery Path 
          <option value=0F18>Mt.Pyre 1 
          <option value=1018>Mt.Pyre 2 
          <option value=1118>Mt.Pyre 3 
          <option value=1218>Mt.Pyre 4 
          <option value=1318>Mt.Pyre 5 
          <option value=1418>Mt.Pyre 6 Top (Inside) 
          <option value=1518>Mt.Pyre 7 (Outside) 
          <option value=1518>Mt.Pyre 8 Top (Outside) 
          <option value=1C18>Seafloor Cavern 2 
          <option value=1D18>Seafloor Cavern 3 
          <option value=1E18>Seafloor Cavern 4 
          <option value=1F18>Seafloor Cavern 5 
          <option value=2018>Seafloor Cavern 6 
          <option value=2118>Seafloor Cavern 7 
          <option value=2218>Seafloor Cavern 8 
          <option value=2318>Seafloor Cavern 9 
          <option value=2518>Cave of Origin 1 
          <option value=2618>Cave of Origin 2 
          <option value=2718>Cave of Origin [3] 
          <option value=2818>Cave of Origin [4] 
          <option value=2918>Cave of Origin [5] 
          <option value=2B18>Victory Road 1 
          <option value=2C18>Victory Road 2 
          <option value=2D18>Victory Road 3 
          <option value=2E18>Shoal Cave 1 
          <option value=2F18>Shoal Cave 2 
          <option value=3018>Shoal Cave 3 
          <option value=3118>Shoal Cave 4 
          <option value=5318>Shoal Cave (Ice) 
          <option value=3418>New Mauville 1 
          <option value=3518>New Mauville 2 
          <option value=4F18>Sky Pillar 3 
          <option value=5118>Sky Pillar 5 
          <option value=5418>Sky Pillar 7 
          <option value=5E18>Mirage Tower 1 
          <option value=5F18>Mirage Tower 2 
          <option value=6018>Mirage Tower 3 
          <option value=6118>Mirage Tower 4 
          <option value=6218>Desert Underpass 
          <option value=6318>Artisan Cave 1 
          <option value=6418>Artisan Cave 2 
          <option value=6A18>Altering Cave 
          <option value=031A>Safari Zone A
          <option value=021A>Safari Zone B (left) 
          <option value=011A>Safari Zone C (top-right) 
          <option value=001A>Safari Zone D (top-left) 
          <option value=0D1A>Safari Zone E (far-right) 
          <option value=0C1A>Safari Zone F </option>
        </select>
      </TD>
    </TR>
    <TR> 
      <TD colspan="2" width="290">-Set the game version first! The pokemon will be found in 
        the wild at this location. It will appear as frequently as what's stated 
        in the code version.</TD>
    </TR>
    <tr> 
      <TD height="12" colspan="2"> 
        <p align="left">&nbsp; 
          <INPUT onclick=codeout(4) type=button value="Generate Codes">
          <input type="reset" name="Reset" value="Reset" onClick="new_loc(0); javascript: if(document.PokemonForm.Dex.selectedIndex!=0){NewDex(0);} document.PokemonForm.MPID.checked=false; EnablePID()" onMouseOut="HPower(); SpecialPoke()" onBlur="HPower(); SpecialPoke()">
        </p>
      </TD>
      <TD colSpan=2> 
        <p>Game: 
          <select name=Game size="1" onChange="(this.selectedIndex>0 && document.PokemonForm.Loc.options.length==93)?null:new_loc(this.options[this.selectedIndex].value); NewPoke()">
             	<option value="8">Pokemon back in time 1.8</option>
            <option value="1">Pokemon FireRed 1.0</option>
            <option value="1">Pokemon LeafGreen 1.0</option>
			<option value="1">Pokemon FireRed 1.1</option>
			<option value="1">Pokemon LeafGreen 1.1</option>			  	<option value="8">Pokemon back in time 1.2</option>
          </select>
        </p>
      </TD>
    </tr>
    <TR> 
      <TD colspan="2"> 
        <label><INPUT onClick="Device(0)" type=radio value=VBA name=RCode>
        VBA</label>&nbsp;&nbsp; 
        <label><INPUT onClick="Device(1)" type=radio value=ARv1-2 name=RCode>
        ARv1-2</label>&nbsp;&nbsp; 
        <label><INPUT onClick="Device(2)" type=radio CHECKED value=ARv name=RCode>
        ARv3</label></TD>
      <TD colSpan=2>Codes: 
        <select name=Codetype size="1">
          <option value="0" selected><b>DMA version (Sometimes)</b></option>
          <option value="1"><b>RNG version (Always)</b></option>
        </select>
      </TD>    
    </TBODY> 
  </TABLE>
  
  <TABLE class="second" cellSpacing=0 cols=4 cellPadding=3 width="600" height="100" bgColor=#DFDFDF border=0>
    <TBODY> 
    <TR> 
      <TD colspan="2"><B>Stats:</B></TD>
      <TD width="122" align="left" nowrap><span class="power">Hidden Power:<sup> </sup></span> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 
      name=HidePower style="background-color: #DFDFDF; border-style: solid; border-width: 0">
      </TD>
      <TD colspan="2">&nbsp; </TD>
    </TR>
    <TR> 
      <TD colspan="2" nowrap>Current HP: 
        <INPUT maxLength=4 size=4 value=1 name=CurrentHP onchange="TestNumerical()">
        <INPUT onclick=MaxCurrentHP() type=button value=Max>
      </TD>
      <TD width="120" align="left"><span class="power">Type:</span><sup> </sup>
        <INPUT maxLength=10 size=8 name=PowerType value="??" style="background-color: #DFDFDF; border-style: solid; border-width: 0">
      </TD>
      <TD colspan="2">&nbsp; </TD>
    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2; border-top-style: groove; border-top-width: 2" bordercolorlight="#FFFFFF" bordercolordark="#808080" nowrap> 
        <p align="center"><sub> 
          <INPUT onclick=MaxDV() type=button value="Max IV">
          <INPUT onclick=RandomDV() type=button value="Random">
          </sub></p>
      </TD>
      <TD width="120"> <font color="#0000FF"> <u><sub>Stats:</sub></u>&nbsp;&nbsp;</font> 
      </TD>
      <TD colspan="2"><B>Contest Stats:&nbsp;</B> 
        <INPUT onclick=MaxContest() type=button value=Max>
 </TD>
    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" bordercolorlight="#FFFFFF" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2" bordercolordark="#808080"> 
        <p align="left">HP: 
          <SELECT onchange=HPower() name=HPDV style="left: 55; position: relative" size="1">
            <OPTION value=00 selected>0 
            <OPTION value=01>1 
            <OPTION value=02>2 
            <OPTION value=03>3 
            <OPTION value=04>4 
            <OPTION value=05>5 
            <OPTION value=06>6 
            <OPTION value=07>7 
            <OPTION value=08>8 
            <OPTION value=09>9 
            <OPTION value=10>10 
            <OPTION value=11>11 
            <OPTION value=12>12 
            <OPTION value=13>13 
            <OPTION value=14>14 
            <OPTION value=15>15 
            <OPTION value=16>16 
            <OPTION value=17>17 
            <OPTION value=18>18 
            <OPTION value=19>19 
            <OPTION value=20>20 
            <OPTION value=21>21 
            <OPTION value=22>22 
            <OPTION value=23>23 
            <OPTION value=24>24 
            <OPTION value=25>25 
            <OPTION value=26>26 
            <OPTION value=27>27 
            <OPTION value=28>28 
            <OPTION value=29>29 
            <OPTION value=30>30 
            <OPTION value=31>31</OPTION>
          </SELECT>
        </p>
      </TD>
      <TD width="120"> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 name=HPDex style="background-color: #DFDFDF; border-style: solid; border-color: #DFDFDF">
      </TD>
      <TD class="ridge" width="138" style="padding: 0; FILTER: progid:DXImageTransform.Microsoft.Gradient(startColorStr='#F8D0B0', endColorStr='#F89860', gradientType='0'); border-left-style: ridge; border-left-width: 2; border-right-style: ridge; border-right-width: 2; border-top-style: ridge; border-top-width: 2" bgcolor="#F8B286">
        <div class="gradient F8D0B0 F89860 vertical" style="position:relative; display: block; padding: 3px 0 4px 6px">
          Cool: 
            <INPUT maxLength=3 size=3 value=0 name=Cool style="position: relative; left: 15" onchange="TestNumerical()">
        </div>
      </TD>
      <TD width="150">&nbsp; </TD>

    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2" bordercolorlight="#FFFFFF" bordercolordark="#808080"> 
        <p align="left">Attack: 
          <SELECT onchange=HPower() name=AtkDV style="position: relative; left: 34" size="1">
            <OPTION value=00 selected>0 
            <OPTION value=01>1 
            <OPTION value=02>2 
            <OPTION value=03>3 
            <OPTION value=04>4 
            <OPTION value=05>5 
            <OPTION value=06>6 
            <OPTION value=07>7 
            <OPTION value=08>8 
            <OPTION value=09>9 
            <OPTION value=10>10 
            <OPTION value=11>11 
            <OPTION value=12>12 
            <OPTION value=13>13 
            <OPTION value=14>14 
            <OPTION value=15>15 
            <OPTION value=16>16 
            <OPTION value=17>17 
            <OPTION value=18>18 
            <OPTION value=19>19 
            <OPTION value=20>20 
            <OPTION value=21>21 
            <OPTION value=22>22 
            <OPTION value=23>23 
            <OPTION value=24>24 
            <OPTION value=25>25 
            <OPTION value=26>26 
            <OPTION value=27>27 
            <OPTION value=28>28 
            <OPTION value=29>29 
            <OPTION value=30>30 
            <OPTION value=31>31</OPTION>
          </SELECT><input type="text" name="AtkBoost" maxLength=1 size="1" style="position: relative; left: 39; font-size: 13pt; width: 15; color: #0000FF; height: 22; text-align: Center; background-color: #DFDFDF; border-style: solid; border-width: 0">
        </p>
      </TD>
      <TD width="120"> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 name=AtkDex style="background-color: #DFDFDF; border-style: solid; border-color: #DFDFDF">
      </TD>
      <TD class="ridge" width="138" style="padding: 0; FILTER: progid:DXImageTransform.Microsoft.Gradient(startColorStr='#D8E8F8', endColorStr='#8098F8', gradientType='0'); border-left-style: ridge; border-left-width: 2; border-right-style: ridge; border-right-width: 2" bgcolor="#ACC0F8">
        <div class="gradient D8E8F8 8098F8 vertical" style="position:relative; display: block; padding: 3px 0 4px 6px">
          Beauty: 
            <INPUT maxLength=3 size=3 value=0 name=Beauty style="position: relative; left: 3" onchange="TestNumerical()">
        </div>
      </TD>
      <TD width="150">&nbsp; </TD>

    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2" bordercolorlight="#FFFFFF" bordercolordark="#808080"> 
        <p align="left">Defense: 
          <SELECT onchange=HPower() name=DefDV style="position: relative; left: 26" size="1">
            <OPTION value=00 selected>0 
            <OPTION value=01>1 
            <OPTION value=02>2 
            <OPTION value=03>3 
            <OPTION value=04>4 
            <OPTION value=05>5 
            <OPTION value=06>6 
            <OPTION value=07>7 
            <OPTION value=08>8 
            <OPTION value=09>9 
            <OPTION value=10>10 
            <OPTION value=11>11 
            <OPTION value=12>12 
            <OPTION value=13>13 
            <OPTION value=14>14 
            <OPTION value=15>15 
            <OPTION value=16>16 
            <OPTION value=17>17 
            <OPTION value=18>18 
            <OPTION value=19>19 
            <OPTION value=20>20 
            <OPTION value=21>21 
            <OPTION value=22>22 
            <OPTION value=23>23 
            <OPTION value=24>24 
            <OPTION value=25>25 
            <OPTION value=26>26 
            <OPTION value=27>27 
            <OPTION value=28>28 
            <OPTION value=29>29 
            <OPTION value=30>30 
            <OPTION value=31>31</OPTION>
          </SELECT><input type="text" name="DefBoost" maxLength=1 size="1" style="position: relative; left: 31; width: 15; height: 22; color: #0000FF; font-size: 13pt; text-align: Center; background-color: #DFDFDF; border-style: solid; border-width: 0">
        </p>
      </TD>
      <TD width="120"> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 name=DefDex style="background-color: #DFDFDF; border-style: solid; border-color: #DFDFDF">
      </TD>
      <TD class="ridge" width="138" style="padding: 0; FILTER: progid:DXImageTransform.Microsoft.Gradient(startColorStr='#F8D8F8', endColorStr='#F8A8D0', gradientType='0'); border-left-style: ridge; border-left-width: 2; border-right-style: ridge; border-right-width: 2" bgcolor="#F8C0E4">
        <div class="gradient F8D8F8 F8A8D0 vertical" style="position:relative; display: block; padding: 3px 0 4px 6px">
          Cute: 
            <INPUT maxLength=3 size=3 value=0 name=Cute style="position: relative; left: 16" onchange="TestNumerical()">
        </div>
      </TD>
      <TD width="150">&nbsp; </TD>
    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2" bordercolorlight="#FFFFFF" bordercolordark="#808080"> 
        <p align="left">Sp. Attack: 
          <SELECT onchange=HPower() name=SpADV style="position: relative; left: 9" size="1">
            <OPTION value=00 selected>0 
            <OPTION value=01>1 
            <OPTION value=02>2 
            <OPTION value=03>3 
            <OPTION value=04>4 
            <OPTION value=05>5 
            <OPTION value=06>6 
            <OPTION value=07>7 
            <OPTION value=08>8 
            <OPTION value=09>9 
            <OPTION value=10>10 
            <OPTION value=11>11 
            <OPTION value=12>12 
            <OPTION value=13>13 
            <OPTION value=14>14 
            <OPTION value=15>15 
            <OPTION value=16>16 
            <OPTION value=17>17 
            <OPTION value=18>18 
            <OPTION value=19>19 
            <OPTION value=20>20 
            <OPTION value=21>21 
            <OPTION value=22>22 
            <OPTION value=23>23 
            <OPTION value=24>24 
            <OPTION value=25>25 
            <OPTION value=26>26 
            <OPTION value=27>27 
            <OPTION value=28>28 
            <OPTION value=29>29 
            <OPTION value=30>30 
            <OPTION value=31>31</OPTION>
          </SELECT><input type="text" name="SpABoost" maxLength=1 size="1" style="position: relative; left: 14; width: 15; height: 22; font-size: 13pt; color: #0000FF; text-align: Center; background-color: #DFDFDF; border-style: solid; border-width: 0">
        </p>
      </TD>
      <TD width="120"> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 name=SpADex style="background-color: #DFDFDF; border-style: solid; border-color: #DFDFDF">
      </TD>
      <TD class="ridge" width="138" style="padding: 0; FILTER: progid:DXImageTransform.Microsoft.Gradient(startColorStr='#D0F8B8', endColorStr='#70E070', gradientType='0'); border-left-style: ridge; border-left-width: 2; border-right-style: ridge; border-right-width: 2" bgcolor="#A0EC94">
        <div class="gradient D0F8B8 70E070 vertical" style="position:relative; display: block; padding: 3px 0 4px 6px">
          Smart: 
            <INPUT maxLength=3 size=3 value=0 name=Smart style="position: relative; left: 9" onchange="TestNumerical()">
        </div> 
      </TD>
      <TD width="150">&nbsp; </TD>
    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2" bordercolorlight="#FFFFFF" bordercolordark="#808080"> 
        <p align="left">Sp. Defense: 
          <SELECT onchange=HPower() name=SpDDV style="position: relative; left: 1" size="1">
            <OPTION value=00 selected>0 
            <OPTION value=01>1 
            <OPTION value=02>2 
            <OPTION value=03>3 
            <OPTION value=04>4 
            <OPTION value=05>5 
            <OPTION value=06>6 
            <OPTION value=07>7 
            <OPTION value=08>8 
            <OPTION value=09>9 
            <OPTION value=10>10 
            <OPTION value=11>11 
            <OPTION value=12>12 
            <OPTION value=13>13 
            <OPTION value=14>14 
            <OPTION value=15>15 
            <OPTION value=16>16 
            <OPTION value=17>17 
            <OPTION value=18>18 
            <OPTION value=19>19 
            <OPTION value=20>20 
            <OPTION value=21>21 
            <OPTION value=22>22 
            <OPTION value=23>23 
            <OPTION value=24>24 
            <OPTION value=25>25 
            <OPTION value=26>26 
            <OPTION value=27>27 
            <OPTION value=28>28 
            <OPTION value=29>29 
            <OPTION value=30>30 
            <OPTION value=31>31</OPTION>
          </SELECT><input type="text" name="SpDBoost" maxLength=1 size="1" style="position: relative; left: 6; width: 15; height: 22; font-size: 13pt; color: #0000FF; text-align: Center; background-color: #DFDFDF; border-style: solid; border-width: 0">
        </p>
      </TD>
      <TD width="120"> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 name=SpDDex style="background-color: #DFDFDF; border-style: solid; border-color: #DFDFDF">
      </TD>
      <TD class="ridge" width="138" style="padding: 0; FILTER: progid:DXImageTransform.Microsoft.Gradient(startColorStr='#F8F8B0', endColorStr='#F0E408', gradientType='0'); border-left-style: ridge; border-left-width: 2; border-right-style: ridge; border-right-width: 2; border-bottom-style: ridge; border-bottom-width: 2" bgcolor="#F4EE64">
        <div class="gradient F8F8B0 F0E408 vertical" style="position:relative; display: block; padding: 3px 0 4px 6px">
          Tough: 
            <INPUT maxLength=3 size=3 value=0 name=Tough style="position: relative; left: 7" onchange="TestNumerical()">
        </div>      
      </TD>     
      <TD width="150">&nbsp; </TD>
    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD class="groove" width="161" style="border-left-style: groove; border-left-width: 2; border-right-style: groove; border-right-width: 2; border-bottom-style: groove; border-bottom-width: 2" bordercolorlight="#FFFFFF" bordercolordark="#808080"> 
        <p align="left">Speed: 
          <SELECT onchange=HPower() name=SpeDV style="position: relative; left: 36" size="1">
            <OPTION value=00 selected>0 
            <OPTION value=01>1 
            <OPTION value=02>2 
            <OPTION value=03>3 
            <OPTION value=04>4 
            <OPTION value=05>5 
            <OPTION value=06>6 
            <OPTION value=07>7 
            <OPTION value=08>8 
            <OPTION value=09>9 
            <OPTION value=10>10 
            <OPTION value=11>11 
            <OPTION value=12>12 
            <OPTION value=13>13 
            <OPTION value=14>14 
            <OPTION value=15>15 
            <OPTION value=16>16 
            <OPTION value=17>17 
            <OPTION value=18>18 
            <OPTION value=19>19 
            <OPTION value=20>20 
            <OPTION value=21>21 
            <OPTION value=22>22 
            <OPTION value=23>23 
            <OPTION value=24>24 
            <OPTION value=25>25 
            <OPTION value=26>26 
            <OPTION value=27>27 
            <OPTION value=28>28 
            <OPTION value=29>29 
            <OPTION value=30>30 
            <OPTION value=31>31</OPTION>
          </SELECT><input type="text" name="SpeBoost" maxLength=1 size="1" style="position: relative; left: 41; width: 15; height: 22; font-size: 13pt; color: #0000FF; text-align: Center; background-color: #DFDFDF; border-style: solid; border-width: 0">
        </p>
      </TD>
      <TD width="120"> 
        <INPUT maxLength=3 onchange=HPower() size=3 value=0 name=SpeDex style="background-color: #DFDFDF; border-style: solid; border-color: #DFDFDF">
      </TD>
      <TD colspan="2">&nbsp; </TD>
    </TR>
    <TR> 
      <TD width="1" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp;</TD>
      <TD width="161" bordercolorlight="#FFFFFF" bordercolordark="#808080">&nbsp; </TD>
      <TD width="120">&nbsp; </TD>
      <td colspan="2"> 
        <div align="right"><font color="#AED0CF"><b></b></font></div>
      </td>
    </TR>
    </TBODY> 
  </TABLE>
</FORM>


<!--FreeWebs FreeBar Code Begin-->

<br />
<table width="80%" border="0" cellspacing="0" cellpadding="0" align="center">
  <tr>
    <td bgcolor="#EEEEEE" align="center">
      <font size="2" color="#000000" face="verdana, arial">
        This website is hosted for free by <a href="http://www.webs.com/" title="Free Website" rel="nofollow"><img style="border:0px; width:71px; height:16px;vertical-align:bottom;" src="http://images.webs.com/Images/logo-tm.gif" alt="free website - Webs.com"></a>.
      </font>
        <font size=2 color="#0000FF">

      Get your own <a href="http://www.webs.com/" target="_blank" title="Free Website" rel="nofollow">Free Website</a> now!
        </font>
    </td>
  </tr>
</table>


<!--FreeWebs FreeBar Code End-->


</BODY></HTML>
<!-- --><script type="text/javascript" src="http://static.websimages.com/static/global/js/webs/usersites/escort.js"></script><script type="text/javascript">if(typeof(urchinTracker)=='function'){_uacct="UA-230305-2";_udn="none";_uff=false;urchinTracker();}</script>
