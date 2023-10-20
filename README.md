# Introdução ao SNMP

- Desenvolvi este conteúdo para organizar todas as informações sobre meu estudo referente ao protocolo SNMP.

- Minha intenção também é compartilhar todos os ensinamentos com aqueles que estão em busca de melhorar também seu conhecimento sobre SNMP e redes de computadores.

- Lembrando que este material é a base de todo o meu progresso nos estudos atuais. Fique à vontade para contribuir ou utilizá-lo da maneira que desejar.

- Conteúdo em connstrução!


# O que é o SNMP?

-O Protocolo SNMP(Simple Network Management Protocol), utilizado na porta padrão 161, é um protocolo de rede que permite a monitoria e gestão de dispositivos de rede, coletando informações e controlando configurações em sistemas, como roteadores, switches e servidores.

- Com o SNMP, podemos receber diversas estatísticas de um dispositivo. Por exemplo: Uptime, Carga da CPU, Largura de banda, Consumo de memória, Número de conexões ativas, Status de portas e interfaces, Tráfego de pacotes, níveis de ruído e intensidade de sinal em dispositivos de rede sem fio, Status de impressoras em uma rede, Espaço em disco disponível, entre outros.

# Versões do SNMP

SNMPv1

- O SNMPv1 foi a primeira versão do protocolo e é conhecido por sua simplicidade. No entanto, ele tem algumas limitações de segurança, como o uso de comunidades (strings de texto) para autenticação, que são vulneráveis a ataques de força bruta.

Exemplo de uma operação SNMPv1 para obter o uptime de um dispositivo:

```
Comunidade de leitura (Read Community): public
OID (Object Identifier) para Uptime: 1.3.6.1.2.1.1.3.0
```

### SNMPv2c

- O SNMPv2c(Community-Based Simple Network Management Protocol) trouxe melhorias em relação ao SNMPv1, mantendo uma abordagem simples. Ele ainda usa comunidades para autenticação, mas adiciona suporte a operações de ==GET BULK e GET NEXT==. Ambas as operações GET NEXT e GET BULK são usadas para interagir com agentes SNMP para coletar informações de gerenciamento de rede, mas a diferença principal está na quantidade de informações que podem ser obtidas em uma única solicitação. O GET NEXT obtém um objeto de cada vez, enquanto o GET BULK obtém um conjunto de objetos.

Exemplo de operação SNMPv2c para obter informações sobre a interface de rede de um roteador:

```
Comunidade de leitura (Read Community): public
OID para informações da interface: 1.3.6.1.2.1.2.2.1
```

### SNMPv3

- O SNMPv3 é a versão mais segura e flexível do protocolo. Ele introduz autenticação e criptografia robustas, tornando-o adequado para ambientes sensíveis à segurança. O SNMPv3 oferece três níveis de segurança: autenticação, privacidade e controle de acesso.

Exemplo de operação SNMPv3 com autenticação e privacidade para consultar a tabela de interfaces de um switch:

```
Nome de usuário: admin
Senha de autenticação: minha_senha_segura
Senha de privacidade: minha_senha_privada
OID para tabela de interfaces: 1.3.6.1.2.1.2.2
```

