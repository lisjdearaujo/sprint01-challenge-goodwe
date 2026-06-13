# EV ChargeOps — Enterprise Challenge 2026

**Parceiro:** GoodWe / FIAP Energy Innovation Lab

---

## Equipe

| Nome | RM |
|------|----|
| Eduardo Alves da Silva | RM 568601 |
| Gabrielly Drosda da Silva | RM 571793 |
| Lisandra Jacinto de Araujo | RM 574055 |
| Nathan Caio da Silva | RM 568750 |

---

## Descrição do Problema e Contexto do Desafio

A GoodWe é uma das maiores fabricantes globais de inversores e sistemas de armazenamento de energia, com presença em mais de 100 países e capacidade instalada acumulada superior a 100 GW (GoodWe, 2024). No Brasil, a empresa mantém parceria com a FIAP por meio do Energy Innovation Lab, localizado na Unidade Aclimação, onde o carregador de veículos elétricos modelo HCA G2, instalado no estacionamento L1, serve como objeto de estudo direto deste projeto.

O crescimento acelerado da frota de veículos elétricos no país evidencia um problema operacional que ainda não foi adequadamente resolvido. Infraestruturas de recarga compartilhada em condomínios residenciais, edifícios corporativos e campus universitários não dispõem de mecanismos integrados para estruturar sessões por usuário, calcular consumo individual, aplicar regras de rateio justas e oferecer uma experiência digital clara para moradores e gestores.

Cada sessão de recarga produz um conjunto de dados com potencial operacional significativo, incluindo duração, volume de energia entregue em kWh, horário de uso, frequência de acesso, picos de demanda e intervalos de ociosidade. Quando organizados e processados, esses dados deixam de ser registros isolados e passam a sustentar decisões de gestão, previsão de demanda, detecção de uso irregular e geração automática de cobranças individuais. O EV ChargeOps propõe exatamente essa transformação, utilizando inteligência artificial como motor lógico da solução.

A pergunta central que orienta o projeto é como transformar sessões de recarga de veículos elétricos em uma infraestrutura compartilhada em dados estruturados, rateio justo e inteligência acionável.

---

## Frente 1 — Contexto e Problema

> _A ser preenchido._

### Infraestruturas de recarga compartilhada

> _Descrever o que são, como funcionam e quais os principais desafios operacionais para gestores de condomínios, edifícios corporativos e campus universitários._

### Funcionamento técnico de uma sessão de recarga

> _Descrever o que acontece entre a conexão do veículo e o encerramento da sessão, quais dados são gerados e como podem ser capturados._

### Modelos de negócio para recarga compartilhada

> _Mapear os modelos existentes no Brasil e no mundo: recarga gratuita, cobrança por kWh, cobrança por tempo, assinatura mensal e rateio condominial._

### Opção C — Análise de dados públicos

> _Apresentar os dados levantados sobre crescimento da frota de VE no Brasil, distribuição de pontos de recarga e perfis de uso, com análise própria da equipe._

---

## Frente 2 — Base Regulatória e Técnica

> _A ser preenchido._

### Resolução Normativa ANEEL nº 1.000/2021

> _Documentar os pontos relevantes para a operação do EV ChargeOps: exploração comercial da recarga, comunicação prévia à distribuidora e exigência de protocolos abertos._

### Carregador GoodWe HCA G2

> _Descrever as interfaces disponíveis (RS-485, LAN, Wi-Fi, Bluetooth e RFID) e o que cada uma permite fazer na plataforma._

### API GoodWe — SEMS Portal

> _Documentar os dados expostos pela API: status, potência, energia entregue e eventos de sessão._

### Opção de aprofundamento escolhida

> _A ser preenchido._

---

## Frente 3 — Arquitetura e IA

> _A ser preenchido._

### Camadas da plataforma EV ChargeOps

> _Descrever as camadas física, de conectividade, de aplicação e de apresentação._

### Fluxo de dados: da sessão à fatura

> _Descrever o caminho completo dos dados, as transformações que ocorrem e onde a IA entra no fluxo._

### Modelo de rateio proposto

> _Definir as variáveis utilizadas, como a fatura individual é calculada e como o modelo lida com casos excepcionais._

### Opção de aprofundamento escolhida

> _A ser preenchido._


---

## Diagrama de Arquitetura

> _Inserir imagem do diagrama aqui após a criação._
>
> 

---

## Papel da IA na Solução

> _A ser preenchido com a descrição estrutural do papel da IA na plataforma: quais problemas resolve, quais técnicas são utilizadas, quais dados alimentam os modelos e qual o impacto esperado._

---

## Plano para a Sprint 02

> _A ser preenchido com o detalhamento do que será desenvolvido, em qual ordem e com quais tecnologias._

---

## Fontes Consultadas

### Frente 1

- Ambar-e. Carregamento compartilhado em condomínios: como funciona e quem paga a conta. Disponível em: https://ambare.com.br/carregamento-compartilhado-em-condominios-como-funciona-e-quem-paga-a-conta/
- Zangari. Carros elétricos em condomínio: o que mudou em 2026 e como se preparar. Disponível em: https://zangari.com.br/blog/carros-eletricos-condominio/
- Migalhas. Lei 18.403/26 de SP: recarga de veículos elétricos em condomínios. Disponível em: https://www.migalhas.com.br/coluna/migalhas-edilicias/452093/lei-18-403-26-de-sp-recarga-de-veiculos-eletricos-em-condominios
- MyCond. Desafios para carregadores de carros elétricos em condomínios. Disponível em: https://mycond.com.br/desafios-para-carregadores-de-carros-eletricos-em-condominios/
- CondoCash. Carregador de carro elétrico em condomínio: instalação, custos e rateio. Disponível em: https://condocash.com.br/carregador-de-carro-eletrico-em-condominio-instalacao-custos-e-rateio/
- Canal VE. Como funciona o protocolo OCPP na recarga de carros elétricos. Disponível em: https://canalve.com.br/como-funciona-o-protocolo-ocpp-nas-recargas-de-carros-eletricos/
- Kilowatt Crew. OCPP: o guia definitivo para quem opera, integra e desenvolve infraestrutura de recarga. Disponível em: https://www.kilowattcrew.app/noticias/ocpp-open-charge-point-protocol-o-guia-definitivo
- VoltBras. Como o OCPP 1.6 facilita o carregamento elétrico. Disponível em: https://voltbras.com/ocpp-1-6-carregamento/
- Power2Go. Cobrança por kWh ou assinatura mensal? O melhor modelo para recarga de carros elétricos. Disponível em: https://www.power2go.com.br/post/melhor-modelo-de-cobran%C3%A7a-para-recarga-de-carros-el%C3%A9tricos
- Sindiconet. Carro elétrico: recarregue seu veículo sem sair do condomínio. Disponível em: https://www.sindiconet.com.br/informese/carro-eletrico-mercado-coluna-de-olho-no-mercado
