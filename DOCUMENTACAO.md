1. O que é o projeto



Nosso projeto consiste em um carrinho para transporte de pequenas cargas, funcionando como um ajudante no dia a dia.

Ele foi desenvolvido com o intuito de auxiliar em pequenas tarefas em locais específicos, como residências, almoxarifados e estoques. Nosso projeto visa unir praticidade e tecnologia, oferecendo um pequeno ajudante capaz de realizar transportes com eficiência e precisão.



2. O que foi feito

Foi desenvolvido um carrinho com rodas omnidirecionais. Essas rodas permitem que o carrinho não apenas ande para trás, mas também para a direita e para a esquerda. Ele possui comunicação via MQTT e AWS, com comunicação por meio de aplicativo e dashboard.

Nosso projeto final funciona com as direções padrão (frente, trás, direita e esquerda) e conta com o funcionamento do seguidor de linha, que, como o nome já diz, direciona o carrinho a partir de uma linha.

Como easter egg, utilizamos o sensor RFID: quando ele identifica algum cartão na parte superior do carrinho, onde o sensor está localizado, os LEDs do carrinho são acionados. Também implementamos um sistema de segurança por meio de um sensor de distância; caso o sensor detecte algum objeto a 170 milímetros à frente do carrinho, ele para instantaneamente.

No display localizado na parte superior do carrinho, exibimos a logo da nossa equipe. Ao girar o encoder, aparece um texto explicando o que foi feito no projeto; ao girá-lo novamente, aparecem os nomes dos integrantes do grupo em forma de créditos.



3. Como foi feito (arquitetura, comunicação, hardware, fluxos, telas)

Nosso projeto foi desenvolvido utilizando a linguagem C++ para o código do carrinho e JavaScript para o dashboard. A estrutura central de funcionamento do carrinho é composta por bibliotecas que separam as diferentes funções do sistema. No código principal (main), essas bibliotecas são chamadas para garantir o funcionamento correto do carrinho.

Dessa forma, a organização do projeto se torna mais clara e eficiente, evitando confusões e facilitando o controle de cada parte do sistema.

Utilizamos comunicação via MQTT, na qual, por meio dos tópicos definidos, conseguimos enviar as mensagens desejadas, mantendo uma comunicação estável entre o carrinho e o código. Quando conectado via MQTT, é possível enviar e receber informações sobre o funcionamento do carrinho.

Os componentes físicos incluem LEDs responsáveis pelos faróis, lanternas traseiras para ré e setas. Também utilizamos rodas omnidirecionais, sensor de distância, sensor de temperatura para os quatro motores e um encoder, que fica localizado na parte traseira juntamente com o display. O display funciona em conjunto com o encoder, exibindo informações sobre o nosso grupo.

Além disso, utilizamos um RFID, acionado por um cartão responsável pelo nosso easter egg; um joystick, que é o controle físico responsável por movimentar o carrinho; o ESP32, microcontrolador responsável por receber e processar os códigos enviados; e a placa central do carrinho, que realiza a conexão física entre todos os componentes do sistema.

Os fluxos do dashboard foram conectados aos tópicos correspondentes às funções que cada um deveria realizar, como o recebimento da temperatura e a mudança de estado dos LEDs do carrinho. Assim, as mensagens enviadas e recebidas são tratadas corretamente pelos fluxos, garantindo o funcionamento adequado do sistema.

Utilizamos uma tela que acompanha a temperatura dos quatro motores e botões que alteram e exibem o estado dos LEDs.



4. O que foi planejado (plano inicial do grupo)

Foi planejado um carrinho móvel que se movesse para frente, trás, direita e esquerda, com LEDs funcionando conforme o movimento do carrinho (por exemplo, ao virar para a direita, a seta direita acenderia).

Também foi planejado um easter egg por meio do sensor RFID: ao identificar um cartão na parte superior do carrinho, os LEDs seriam acionados. Conforme planejado, foi implementado um sistema de segurança por meio de um sensor de distância; caso o sensor detectasse algum objeto a 170 milímetros à frente do carrinho, ele pararia instantaneamente.

O dashboard foi planejado para receber, em tempo real, a temperatura dos quatro motores, servindo para monitoramento e evitando sobrecarga. No dashboard, também foi implementado um sistema de controle dos LEDs, permitindo ligar ou desligar qualquer LED do carrinho.

Além disso, foi desenvolvido um aplicativo pelo qual conseguimos controlar o carrinho nas quatro direções programadas. Também utilizamos um joystick para controlar o carrinho, conforme o planejamento inicial.



5. O que faltou fazer

Faltou a integração do código central com o código do seguidor de linha, que infelizmente não conseguimos unificar. Além disso, o joystick está funcionando, porém os botões apresentam engasgos, pois alguma parte da comunicação não está sendo enviada corretamente via MQTT.



6. O que não funcionou (com causa provável)

A integração do código central com o código do seguidor de linha não foi concluída, pois não foi possível unificar ambos corretamente. Além disso, o joystick apresentou falhas nos botões devido a problemas na comunicação via MQTT, o que ocasionou engasgos durante o uso.



7. O que precisa melhorar (melhorias técnicas e organização do projeto)

Tivemos problemas técnicos durante a implementação do código do seguidor de linha, sendo necessários ajustes para que a compilação fosse concluída corretamente.

Outro problema técnico identificado foi no controle por joystick, que apresentava travamentos e acabava impedindo o funcionamento preciso do sistema.



8. Como executar/testar (passo a passo para reproduzir)

Para que o carrinho comece a funcionar desde o início, é necessário iniciar a AWS, ativando a instância responsável pelo funcionamento do dashboard. Ao iniciar a AWS, também é estabelecida a comunicação com o IoT Core, funcionalidade da AWS que permite a comunicação via MQTT.

Após isso, caso o carrinho ainda não tenha recebido os códigos, é necessário acessar o VS Code, onde o carrinho é programado, e enviar o código para o ESP32. Uma vez enviado, o código fica salvo no microcontrolador até que seja substituído por outro.

Com o código carregado, o sistema passa a funcionar corretamente: no dashboard é possível visualizar a temperatura dos quatro motores e alterar o estado dos LEDs, ligando ou desligando conforme desejado.

Também foi desenvolvido um aplicativo; após instalá-lo, é possível controlar o carrinho por ele ou por meio do joystick. Para visualizar o easter egg, basta aproximar um cartão da parte superior do carrinho, fazendo com que todos os LEDs se acendam.

Para testar o sistema de segurança, basta posicionar um obstáculo à frente do carrinho; ao detectar um objeto a 170 milímetros de distância, o carrinho para automaticamente.

No display, é exibida a logo da nossa equipe. Ao lado do display há um encoder: ao girá-lo, aparece uma descrição sobre o objetivo do projeto; ao girá-lo novamente, aparecem os nomes dos integrantes do grupo em forma de créditos. Para inicializar o seguidor de linha, basta pressionar o encoder; para interrompê-lo, pressione novamente. O seguidor de linha também pode ser iniciado pelo aplicativo.



9. Integrantes e papéis (quem fez o quê)

Felipe

Movimentos do carrinho

Leitor de proximidade

RFID

Integração dos códigos

Envio e tratamento de informações via MQTT

Maria Saraiva

Sensor de temperatura

Node-RED (dashboard)

Envio e tratamento de informações via MQTT

Maria Lomeu

Display colorido, encoder e interface

Controle físico

Mariane

LEDs (setas, farol e lanterna)

Aplicativo Android

Envio e tratamento de informações via MQTT

Gabriella

PID

Seguidor de linha
