# Jogo Ichigo

 - Link do jogo: https://www.greenfoot.org/scenarios/28848

![imagem of result](https://github.com/WellysonM/Jogo-Ichigo/blob/master/jogo.PNG?raw=true)

## Tecnologias usadas

- JAVA

### Jogo feito no greenfoot

- execute o arquivo .jar com o JAVA

### Controles do jogo

- espaço => pula 
- setas do teclado => controla o personagem

### Objetivo do jogo

- controle o Ichigo pulando e desviando dos Goku e Naruto e colhendo as moedas para assim aumentar sua pontuação
- OBS: você pode controla o Ichigo mesmo no ar enquanto o personagem pula ou esta caindo 
- o getsuga tenshou do ichigo é automatico 

### Como o Ichigo se movimenta

    private void gerenciamentoDoMovimento(){
        setImage(new GreenfootImage("personagem/ichigo"+proximoPasso+".png"));

        if(possoAtualizar()){
            proximoPasso++;
        }
        if(proximoPasso > 12){
            proximoPasso = 5;
        }

    }
    
        public void movimento(){

        if (Greenfoot.isKeyDown("left") && getX()>0 || isTouching(Bicho.class))
            move(-6);

        if (Greenfoot.isKeyDown("right") && getX()!=690 || isTouching(Bicho.class))
            move(2);

        if(jeda>0)jeda--;
        else jeda=500;
        if(jeda==1){

            setImage(new GreenfootImage("personagem/ichigo"+proximoAtaque+".png"));
            if (possoAtualizar()){
                proximoAtaque++;
            }
            if(proximoAtaque > 26){
                proximoAtaque = 23;
            }
            getWorld().addObject(new Laser(),getX()+100,getY());
        }

    }
    
    - Para o Ichigo se mover é um conjunto de imagem que ao ser trocada de um para outra rapidamente da a impressão do personagem esta
    correndo, pulando, caindo ou atancando.
    
    - O mesmo é utlizado para da impressão do fundo ta se movimentando.
