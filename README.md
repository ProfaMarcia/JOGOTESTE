Player - CRIAR

window_set_size(1280,720);//Funcao que almenta a janela do jogo
 flor =0 //Foi criado o objeto flor


ETAPA -----------------

if keyboard_check(vk_up) //Se eu apertar a tecla de cima! (Função serve para verificar se atecla esta sendo usada).
{ 
	
	y-=1 //Quando aperta o batão cima, diminui 1 da variável y.
}

if keyboard_check(vk_down) //Se eu apertar a tecla de baixo 
{ 
	y+=1 //Quando aperta o batão baixo, aumenta 1 da variável y.

}

if keyboard_check(vk_left) //Se eu apertar a tecla de esquerda
{ 

	x-=1 //Quando aperta o batão esquerda, diminui 1 da variável x.
	image_xscale=-1 // Deixa a imagem invertida
}

if keyboard_check(vk_right) //Se eu apertar a tecla de direita
{ 

	x+=1 //Quando aperta o batão direita, diminui 1 da variável x.
	image_xscale=1 // Deixa a imagem invertida
}


if flor=3 
{
room_goto_next() //Para passar de fase (Proxima Room).
}

if keyboard_check(vk_anykey) //vk_anykey - significa apertar qualquer tecla
{ /* Se tiver apertando qualquer tecla
	o sprite de sera ele correndo */
	
	sprite_index=SplayerCorre
} 
else /* Senao tiver apertando nenhuma tecla
	o sprite de sera ele parado */
{
	
	sprite_index=Splayer
}
	

--------------COLISAO ---------------


FLOR

flor+=1

/*Toda vez que encostar em uma flor, ele vai
aumetar 1 na variável FLOR dele, e destrir a flor que 
ele encostou. Temos que encostar em 3 flores para passar
para a próxima fase.
*/
instance_destroy(other)

--------------------------------------------------------------
SERRA

room_restart() //Função que reinicia no ambiente atual
----------------------------------------------------------------
SERRA Q MOVE

room_restart() //Função que reinicia no ambiente atual
--------------------------------------------------------------------

SERRA Q MOVE CRIAR

hsp=random_range(-2,2) //Variavel de velocidade Horizontal

vsp=random_range(-2,2) //Variavel de velocidade Vertical

/*
Random_range, faz ele se movimentar aleatoriamente
*/

__________________________________________________________________

ETAPA


x+=hsp //O x vai ser somado pala velocidade horizontal

y+=vsp //O x vai ser somado pala velocidade vertical

if x<0 {
hsp=-hsp
image_xscale = -1
} //O hsp vai ser invertido (para nao sair da tela)

if x>room_width{
hsp=-hsp
image_xscale = 1
}

if y<0 {vsp=-vsp} //O vsp vai ser invertido (para nao sair da tela)
if y>room_height{vsp=-vsp}
