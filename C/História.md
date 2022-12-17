---
title: História
permalink: /c/historia/
layout: page
---

A linguagem C é a precursora de quase todas as linguagens de programação modernas, inspirando seus paradigmas, modos de operação e sintaxe. 

Originalmente, programas de computador eram escritos em cartões furados, e eventualmente, passaram a ser escritos como uma série de instruções sequenciais a serem executadas diretamente pelo processador, conhecida como **assembly**.
Assembly é difícil de escrever, entender e aprender. É fácil cometer erros no desenvolvimento do programa e esses erros são muito mais difíceis de serem identificados. Para qualquer pessoa sem conhecimento prévio, *assembly é **ilegível**.*
Para resolver esse problema, e garantir maior agilidade e acessibilidade no desenvolvimento de programas de computador, foram desenvolvidas linguagens de programação de alto nível.
Garantiam ergonomia, fácil identificação de erros e código legível, diminuindo drasticamente a barreira de entrada para programação. 
Mas essas linguagens tinham um sério defeito: eram interpretadas.
Um programa deve rodar como uma série de instruções enviadas para o processador, no entanto, para desfrutar das vantagens fornecidas pelas linguagens de alto nível, era necessário sacrificar performance, pois um programa secundário precisaria ler o código, traduzir ele para assembly e executar na CPU. A presença dessa camada intermediária é, ainda hoje, um sério gargalo no desempenho de todo o tipo de aplicação.

C foi revolucionário nesse sentido, pois tornou possível escrever código legível de alto nível, mas com a mesma performance de um programa desenvolvido minuciosamente em assembly. 
Como? Com o compilador.
Compilação é a etapa em que um código escrito em uma linguagem é transcrito para outra linguagem, nesse caso assembly, apenas uma vez. Você tem seu programa escrito em C, executa o compilador, e este te fornece um novo arquivo, com o mesmo programa, mas escrito em assembly.

C não é pioneiro em muitas de suas características que o tornaram a linguagem de escolha nos últimos quarenta anos: tem esse privilégio pois adota muitas dessas características. 

Se você estivesse usando uma linguagem de alto nível regular, como Pascal, não teria acesso direto ao computador, pois todo o código estaria sendo executado em tempo real pelo interpretador, e não rodando diretamente. no processador 
Esse não é o caso de C.
C, como é simplesmente uma outra forma de escrever assembly, te permite regalias como manipular a memória RAM de forma direta. Graças a isso, é a linguagem de escolha de drivers, sistemas operacionais e sistemas embarcados ainda hoje. É uma linguagem extremamente poderosa, com um design além de sua época. C existe a 50 anos, e continuará sendo uma parte pivotal da infraestrutura moderna pelos próximos cinquenta anos.