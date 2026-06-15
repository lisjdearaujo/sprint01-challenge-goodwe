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

Infraestrutura de recarga compartilhada é um modelo em que um ou mais carregadores são instalados em áreas comuns de um condomínio, como garagens coletivas, e ficam disponíveis para uso de vários condôminos que possuem veículos elétricos. Em vez de cada morador ter um carregador individual, o compartilhamento permite otimizar espaço e recursos.

No entanto, como toda inovação, essa traz consigo alguns desafios. O primeiro e mais crítico diz respeito à falta de uma infraestrutura elétrica adequada em prédios, trazendo à tona questões de segurança, custos operacionais e atualização do regimento interno. De fato, há um aumento da demanda por carregadores, mas pouco se vê planejamento técnico, gestão preventiva e adequação das normas internas. Além disso, os síndicos passam a avaliar com maior cautela o risco de responsabilização civil ou criminal caso autorizem instalações que futuramente se revelem inadequadas. Moradores, por sua vez, manifestam preocupação com a sobrecarga da infraestrutura elétrica e com os efeitos de instalações individuais sobre a segurança da edificação. E então, decisões que exigem conhecimento técnico especializado acabam recaindo sobre pessoas que, em regra, não possuem formação para avaliar riscos elétricos.

A isso se soma um problema igualmente relevante na dimensão financeira. Antes mesmo de qualquer orçamento, é preciso definir como os custos de instalação serão divididos e como será feita a cobrança pelo uso do carregador, e para uso coletivo essa definição depende de plataformas de gerenciamento capazes de monitorar o consumo individual de cada morador. Sem essa medição, o rateio se torna impreciso e fonte de conflito. Vale destacar ainda que o condomínio não pode lucrar com a prestação desse serviço, a cobrança deve se limitar ao valor estipulado pela concessionária e, quando aplicável, à taxa da empresa responsável pelo ponto de recarga, o que torna a transparência no controle de consumo não apenas uma conveniência, mas uma exigência.

Entender por que essa transparência é difícil de alcançar exige olhar para o que acontece dentro de uma sessão de recarga. Todo esse processo é mediado por um protocolo de comunicação chamado OCPP, sigla para Open Charge Point Protocol. Trata-se de um padrão aberto que regula a troca de informações entre as estações de recarga e os sistemas de gerenciamento centralizados, e que se tornou referência global justamente por garantir interoperabilidade entre diferentes marcas de carregadores e plataformas de gestão, sem depender de soluções proprietárias.

O ciclo de uma sessão segue etapas bem definidas. Ao ser ligado, o carregador se apresenta ao sistema central por meio de uma mensagem chamada BootNotification, informando suas capacidades e versão de firmware. A partir daí, o usuário precisa ser validado, seja por cartão RFID, aplicativo ou outro meio de autenticação. Com a autenticação confirmada, a sessão tem início e o sistema passa a registrar continuamente os valores de consumo de energia em intervalos regulares, até que o veículo seja desconectado e a sessão encerrada com o total consumido consolidado.

É nesse fluxo que os dados mais relevantes para a gestão emergem. Cada sessão produz informações sobre o status do carregador ao longo do tempo, o consumo exato em kWh, os horários de início e fim, as regras de acesso aplicadas e os eventos de falha, quando ocorrem. Com esses dados trafegando entre o carregador e um servidor externo via OCPP, torna-se possível o monitoramento em tempo real, o controle remoto das sessões, a aplicação de tarifas diferenciadas por horário ou perfil de usuário e a integração com gateways de pagamento para automação do faturamento. É essa capacidade de captura que transforma o carregador de um simples equipamento elétrico em um ponto de coleta de inteligência operacional e que, por sua vez, abre espaço para que modelos de cobrança mais justos e precisos se tornem viáveis.

Quando o assunto é como estruturar essa cobrança, o mercado já apresenta alguns caminhos consolidados. O modelo mais direto é a cobrança por kWh consumido, em que cada usuário paga exatamente pela energia que utilizou, sem divisão proporcional ou estimativas. Uma variação desse modelo é a assinatura mensal fixa combinada com o reembolso do consumo real, em que um valor fixo cobre a infraestrutura e o suporte, e o restante é cobrado conforme o uso efetivo de cada sessão.

Há ainda modelos em que o condomínio deixa de ser o gestor da operação. Empresas especializadas instalam o carregador, monitoram o uso por aplicativo e cobram diretamente de cada usuário, retirando do síndico a responsabilidade pela cobrança e pela gestão do consumo. Uma variação dessa abordagem é a locação do equipamento, em que o condomínio paga uma mensalidade fixa que já inclui manutenção e gestão, sem precisar adquirir o hardware. Empresas como a Tupinambá operam nesse formato, planejando e implementando a rede de recarga enquanto o usuário paga uma assinatura mensal proporcional ao tamanho da rede contratada, com acesso a software de gestão e a uma malha de mais de 1.400 carregadores distribuídos pelo Brasil.

O que todos esses modelos têm em comum é a dependência de um sistema capaz de medir com precisão o consumo individual, o mesmo problema apontado lá no início como ausente na maior parte das infraestruturas compartilhadas hoje. Sem essa camada, qualquer modelo de cobrança se torna impreciso ou injusto. É justamente aí que plataformas como o EV ChargeOps se tornam estruturais, atuando como uma base que viabiliza qualquer um desses modelos de negócio em uma infraestrutura compartilhada.


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
