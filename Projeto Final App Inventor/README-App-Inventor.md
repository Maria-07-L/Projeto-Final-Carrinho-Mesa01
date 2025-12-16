######  **- o que o app faz**

Este aplicativo é responsável por enviar comandos para o carrinho, como as ações de ir para frente, para trás e para os lados. Nosso aplicativo possui senha configurável, garantindo assim um nível de segurança para os clientes.





###### **- quais dados ele envia/recebe (MQTT, HTTP etc., se aplicável)**

Os dados são enviados via MQTT, permitindo a execução dos comandos definidos nos blocos do sistema. A comunicação com o carrinho é realizada por meio do tópico mesa02/cont, responsável pelo envio dos comandos de direção do carrinho como direita, esquerda, etc.





######  **- como testar**

Você pode testar o funcionamento baixando o nosso aplicativo e utilizando os botões disponíveis, como frente, trás, direita e esquerda.

