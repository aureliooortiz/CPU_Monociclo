Registradores de 32bits
 São usados 32 flip-flops tipo D, ligados a uma entrada de 32 bits a entrada do registrador.

Banco de Registradores
 São usados 32 registradores, cada sáida é ligada a dois Mux, com 5 bits de seleção (o endereço do registrador), que está conectada a outra saída, ou seja, o Mux apenas seleciona o registrador que quero ler. Para escrever nos registradores é usado um Demux, suas entradas são conectadas à saída deste Demux, usando também 5 bits de seleção, e a entrada deste Demux é o valor que será escrito no registrador, ou seja, um registrador é selecionado para receber a entrada.

Instruction Memory
 É usada uma ROM para armazenar as instruções em hexadecimal, são usadas 8 bits de dados para instruções e 32 bits de saída para o endereço. 
 ROM:A ROM é o local onde o código de maquina será escrito, os 8 bits de entrada que vem do PC são o endereço de uma instrução do código, em assembly seria o equivalente ao endereço de uma linha contendo uma instrução.
 A ROM só aceita leitura em indices, então todo valor de PC que entra é dividido por 4 (2 shift lógico direito), mudar o valor para pular de 1 em 1 não adiantaria (nesse caso de indice em indice), pois ao fazer um branch ou jump daria problema na hora de pular, por isso é feito pulo de 4 em 4 bytes (tamanho de uma instrução). 

PC

Data_Memory
 Afinal, o que são os bits saido da ALU que entram no data memory?
 
ALU_Control
 Utiliza os bits da ALUop, que são os 2 bits do opcode necessários para distinguir as operações na ULA. Além disso, usa 1 bit do funct7 para distinguir as intruções do tipo-R, o único bit necessário é o bit 30, e por fim usa os 3 bits do funct3 pelo mesmo motivo. Que culminam em 6 bits, que juntos nessa ordem, vão ser o seletor de operações da ULA. 
(Não corro risco de usar o func7 de uma inst que não existe?) Acredito que não pois circuito cuida disto.

Control

ImmGen
