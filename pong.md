# Pong_JavaScript
//Pong game in Javascript

//variaveiBolinha
 let xBolinha = 200;
 let yBolinha = 200;
 let velocidadexBolinha = 10;
 let velocidadeyBolinha = 5;
 let diametro = 25;
 let raio = diametro / 2;

//variaveis Raquete
 let yRaquete = 150;
 let xRaquete = 5;
 let velocidadeyRaquete = 10;
 let comprimentoRaquete = 10;
 let alturaRaquete = 70;
 let raioRaquete = diametroRaquete / 2;

function setup() {
  createCanvas(600, 400);
}

function draw() {
  background(0);
  mostrarBolinha();
  movimentoBolinha();
  colisaoBolinha();
  mostrarRaquete();
  movimentoRaquete();
  colisaoRaquete();
  
}

function colisaoRaquete()
{
  if (xBolinha - raio < xRaquete + comprimentoRaquete && yBolinha - raio < yRaquete + alturaRaquete && yBolinha + raio > yRaquete)
  {
    velocidadexBolinha *= -1;
  }
}

function movimentoRaquete()
{
  if (keyIsDown (DOWN_ARROW))
      yRaquete += velocidadeyRaquete;
  if (keyIsDown (UP_ARROW))
      yRaquete -= velocidadeyRaquete;
}

function mostrarRaquete()
{
  rect(xRaquete, yRaquete, comprimentoRaquete, alturaRaquete);
}

function mostrarBolinha()
{
  circle(xBolinha,yBolinha,diametro);
}

function movimentoBolinha ()
{
  xBolinha += velocidadexBolinha;
  yBolinha += velocidadeyBolinha;
}

function colisaoBolinha()
{
 if (xBolinha + raio > width || xBolinha - raio < 0)
   {
     velocidadexBolinha *= -1;
   }
 if (yBolinha + raio > height || yBolinha - raio < 0)
   {
     velocidadeyBolinha *= -1;
   }
}
