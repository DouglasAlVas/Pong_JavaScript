# Pong_JavaScript
//Pong game in Javascript

//variáveis da bolinha
let xBolinha = 250;
let yBolinha = 200;
let diametro =  22;

//velocidade da bolinha
let velocidadexBolinha = 10;
let velocidadeyBolinha = 10;
let raio = diametro / 2; 

//Player
let xPlayer = 10;
let yPlayer =150;
let velocidadePlayer = 10;
let comprimentoPlayer = 10;
let alturaPlayer = 70;
function setup() {
  createCanvas(500, 400);
}

function draw() {
  background(0);
  mostraBolinha ();
  movimentaBolinha ();
  verificaColisaoBolinha();
  mostrarPlayer();
  movimentoPlayer();
}

function mostraBolinha()
{
  circle(xBolinha, yBolinha, diametro);
}

function movimentaBolinha()
{
  xBolinha += velocidadexBolinha;
  yBolinha += velocidadeyBolinha;
}

function verificaColisaoBolinha()
{
    if (xBolinha + raio > width || xBolinha - raio < 0 )
  {
    velocidadexBolinha *= -1;
  }
  if (yBolinha + raio > height || yBolinha - raio < 0)
  {
    velocidadeyBolinha *= -1    
  }
}

function mostrarPlayer()
{
  rect(xPlayer, yPlayer, comprimentoPlayer, alturaPlayer);
}

function movimentoPlayer() {
    if (keyIsDown(UP_ARROW)) {
        yPlayer -= 10;
    }
    if (keyIsDown(DOWN_ARROW)) {
        yPlayer += 10;
    }
}
