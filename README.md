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


### Opção de aprofundamento (C) — Análise de dados públicos

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

A plataforma EV ChargeOps é organizada em quatro camadas interdependentes. Cada camada tem uma responsabilidade clara e se comunica com a camada adjacente de forma estruturada. Entender essa separação é o que torna possível raciocinar sobre o fluxo de dados completo, desde o momento em que o veículo é conectado até a geração da fatura ao final do mês.

A primeira camada é a física, representada pelo carregador GoodWe HCA G2, modelo GW7K-HCA-20, instalado no estacionamento L1 da FIAP. Trata-se de um carregador CA monofásico com potência nominal de 7 kW, tensão de entrada de 220 V e corrente de 32 A. Ele opera por convecção natural, tem grau de proteção IP66, o que significa que pode ser instalado em ambientes expostos como estacionamentos cobertos ou abertos, e suporta faixa operacional de -30°C a +50°C. Toda a gestão do equipamento é feita pelo aplicativo SEMS+ da GoodWe.

O carregador suporta cinco modos de operação configuráveis: carregamento rápido, prioridade para energia solar, combinação de energia solar com bateria (FV+BAT), agendamento de horário e controle de carga dinâmico. Este último modo é particularmente relevante para a plataforma, pois permite que o sistema ajuste automaticamente a potência de carregamento conforme a disponibilidade da rede elétrica do condomínio, evitando sobrecarga sem interromper as sessões ativas.

Para a autenticação dos usuários, o equipamento aceita três métodos: cartão RFID, sendo que dois cartões já acompanham o kit de instalação, aplicativo SEMS+ via rede Wi-Fi ou LAN, e início automático, que pode ser configurado pelo gestor para dispensar qualquer autenticação. As interfaces de comunicação disponíveis no hardware são Wi-Fi, RS-485 com duas portas, LAN e RFID. O Bluetooth não é uma interface direta do carregador, mas está presente no aplicativo SEMS+ para pareamento e configuração inicial.

A segunda camada é a de conectividade, responsável por transportar os dados do carregador até o servidor da plataforma. O protocolo nativo do GW7K-HCA-20, conforme confirmado no datasheet oficial, é o Modbus TCP. Esse protocolo funciona como uma tabela de registros: cada posição da tabela armazena um valor diferente, como tensão, corrente ou energia acumulada, e o servidor consulta esses registros periodicamente pela rede local. É o protocolo usado para leitura de telemetria em baixo nível.

O OCPP, sigla para Open Charge Point Protocol, é o padrão aberto de mercado para comunicação entre carregadores e sistemas de gerenciamento centralizados. Ele define mensagens específicas para cada evento de uma sessão: o carregador se apresenta ao sistema com BootNotification ao ser ligado, o usuário é validado por Authorize, a sessão tem início registrado por StartTransaction, durante a sessão o carregador envia leituras periódicas de consumo por MeterValues, e o encerramento é registrado por StopTransaction. Essa separação de eventos é o que permite rastrear cada sessão individualmente com precisão.

A terceira camada é a de aplicação, que é o núcleo da plataforma. É aqui que os dados brutos se transformam em informação útil. Essa camada é composta por quatro componentes principais. O primeiro é o CSMS, o sistema de gerenciamento das estações de recarga, que recebe os eventos do carregador em tempo real e é o ponto central de controle das sessões. O segundo é o serviço de ingestão e processamento, que normaliza, valida e persiste os dados no banco da plataforma. O terceiro é o motor de rateio, que aplica as regras de cálculo de consumo individual e gera os dados de faturamento. O quarto é o módulo de IA, que executa os modelos de machine learning para previsão de demanda e detecção de anomalias, descrito em detalhe na seção de aprofundamento abaixo.

A quarta camada é a de apresentação, que materializa os dados processados em interfaces digitais para dois perfis diferentes. O painel do gestor oferece visão consolidada de todas as sessões do mês, gráficos de consumo por unidade e por período, alertas gerados pelo módulo de IA e exportação de relatórios e faturas. O aplicativo do usuário mostra o histórico individual de sessões e consumo, permite autenticação para iniciar sessões e exibe a fatura mensal com detalhamento de uso.

O caminho que um dado percorre desde a conexão do veículo até a geração da fatura passa por seis etapas com transformações distintas em cada uma.
Na primeira etapa, o usuário se autentica junto ao carregador por cartão RFID, pelo aplicativo SEMS+ ou por início automático, quando configurado. O carregador envia uma mensagem Authorize ao CSMS, que valida a identidade no banco de dados e responde com Accepted ou Blocked. Com a autorização confirmada, o carregador emite StartTransaction com o timestamp de início e a leitura inicial do medidor em kWh acumulado.

Na segunda etapa, durante toda a sessão, o carregador envia mensagens MeterValues a intervalos regulares, geralmente a cada 60 segundos. Cada mensagem contém potência instantânea em kW, tensão, corrente, energia acumulada no período e status do conector. O serviço de ingestão normaliza e persiste esses registros como série temporal no banco de dados.

Na terceira etapa, quando o usuário desconecta o veículo ou a sessão atinge o tempo máximo configurado, o carregador emite StopTransaction com o timestamp de fim e a leitura final do medidor. O consumo bruto da sessão é calculado subtraindo a leitura inicial da leitura final, e o status da sessão é atualizado para concluída ou interrompida, dependendo do motivo do encerramento.

Na quarta etapa, o módulo de IA processa os dados da sessão encerrada junto ao histórico acumulado do mês. Essa etapa é descrita em detalhe na seção de aprofundamento.

Na quinta etapa, ao final do mês ou sob demanda do gestor, o motor de rateio consolida todas as sessões do período, aplica as regras de cálculo definidas pelo modelo adotado e lida com os casos excepcionais descritos abaixo.

Na sexta etapa, o sistema gera a fatura individual com detalhamento completo: número de sessões, kWh total consumido, valor calculado com base na tarifa vigente e total a pagar. A fatura é disponibilizada no aplicativo do usuário e o gestor recebe o relatório consolidado.


O modelo adotado pela equipe é o rateio por consumo individual medido em kWh, com ajuste por tarifa horária. A escolha por esse modelo se justifica pela sua precisão e pela sua transparência: cada usuário paga exatamente pela energia que consumiu, sem estimativas ou divisões proporcionais arbitrárias.

As variáveis utilizadas no cálculo são cinco. A primeira é o kWh por sessão, que é a energia efetivamente entregue ao veículo medida pelo medidor interno do GW7K-HCA-20. A segunda é a tarifa de energia em R$/kWh, que corresponde à tarifa vigente da distribuidora local, com distinção entre horário de ponta e fora de ponta. A terceira é o fator de demanda, que é o percentual de uso em horário de ponta, entre 18h e 21h, onde a tarifa é mais cara, calculado sessão a sessão. A quarta é o custo fixo mensal, que é a parcela da taxa condominial relacionada à infraestrutura de recarga, como manutenção e depreciação do equipamento, rateada igualmente entre os usuários ativos no mês. A quinta é o identificador da unidade condominial, que vincula todas as sessões de uma unidade a um único responsável pelo pagamento, independentemente de quantos veículos ela tenha.

A fórmula de cálculo da fatura individual é a seguinte:

```
Fatura da unidade = soma(kWh por sessão × tarifa ajustada) + custo fixo mensal / número de usuários ativos
```

Onde a tarifa ajustada é igual à tarifa base somada ao produto do fator de demanda pelo adicional de ponta. Essa lógica garante que usuários que carregam majoritariamente em horário de ponta paguem proporcionalmente mais, o que cria um incentivo natural para deslocar o uso para períodos de menor custo.

Para os casos excepcionais, o modelo funciona da seguinte forma. Quando uma sessão é interrompida, o consumo medido até o momento da interrupção é cobrado normalmente, pois a energia já foi entregue ao veículo independentemente do motivo do encerramento. O status de interrompida é registrado para auditoria, e se a interrupção foi causada por falha do equipamento, identificada pelo módulo de IA de detecção de anomalias, o gestor pode estornar a sessão manualmente. Quando um usuário não carregou no mês, a parcela variável de consumo em kWh é zero e ele não paga pela energia. A parcela do custo fixo só é cobrada se o usuário tem acesso ativo no sistema, com RFID cadastrado, e usuários com acesso suspenso são excluídos do rateio do custo fixo. Quando uma unidade tem dois veículos, o consumo de todas as sessões de ambos é somado e o cálculo é feito sobre o total da unidade, não por veículo, o que simplifica a gestão e evita disputas internas. Por fim, o sistema consulta mensalmente a bandeira tarifária vigente da ANEEL, verde, amarela ou vermelha, e ajusta automaticamente o valor base do kWh antes de calcular as faturas do período.

### Opção de Aprofundamento (B) — Definição do papel da IA

O condomínio não tem como saber, sem um modelo preditivo, quanto de energia os carregadores vão consumir nos próximos dias ou semanas. Sem essa informação, o gestor não consegue negociar a demanda contratada com a distribuidora. Contratar menos do que o necessário gera multa. Contratar muito mais gera desperdício. A previsão de demanda resolve esse problema diretamente.
A técnica utilizada é a regressão sobre séries temporais. Regressão é um tipo de modelo que aprende a relação entre variáveis de entrada e um valor de saída numérico. No caso, as entradas são o histórico de sessões com seus respectivos horários, dias da semana, consumo em kWh e variáveis de contexto como temperatura e feriados, e a saída é a estimativa de consumo futuro. Modelos como ARIMA, Prophet e XGBoost são candidatos para essa tarefa.

Os dados necessários para treinar o modelo são o histórico de sessões com timestamp de início e fim, kWh consumido por sessão, dia da semana, horário de início e dados de temperatura. O dataset do Kaggle de Electric Vehicle Charging Sessions, com registros reais de frota corporativa nos EUA, pode ser usado para prototipação inicial enquanto o histórico real do carregador da FIAP não está disponível.
O impacto esperado é a redução de custos com tarifas de demanda, a possibilidade de notificar usuários sobre os horários de menor custo para recarga e a geração de dados preditivos que o gestor pode usar para planejar manutenções preventivas nos períodos de menor uso previsto.

Sessões com comportamento atípico são difíceis de identificar manualmente em qualquer volume de dados. Consumo muito acima do esperado para um determinado veículo, duração anormalmente longa, interrupções frequentes em sequência ou uso do carregador por identidades não cadastradas são exemplos de situações que passam despercebidas sem monitoramento automatizado. Fraude por cartão RFID clonado, falha no equipamento entregando energia incorreta e consumo por dispositivos não relacionados a veículos elétricos são casos reais que esse módulo se propõe a capturar.

A técnica utilizada é a detecção de anomalias com algoritmos não supervisionados, sendo o Isolation Forest o candidato principal. Diferente dos modelos supervisionados, que precisam de exemplos rotulados de fraude para aprender, o Isolation Forest aprende o padrão normal das sessões e identifica automaticamente os pontos que se afastam significativamente desse padrão. O modelo pode ser complementado com regras determinísticas simples, como emitir alerta quando o consumo de uma sessão for superior ao dobro da média histórica do usuário.
Os dados necessários são o histórico de sessões por usuário com kWh, duração e horário, o modelo do veículo declarado na plataforma para validar se o consumo está dentro da capacidade da bateria, os registros granulares de MeterValues com a curva de potência ao longo da sessão e os logs de erro do equipamento reportados via StatusNotification.

O impacto esperado é a proteção contra fraudes e uso indevido da infraestrutura compartilhada, a identificação precoce de falhas no equipamento e o aumento da confiança dos usuários no sistema de rateio, pois anomalias são sinalizadas e investigadas antes da emissão da fatura.
Os dois módulos de IA utilizam os dados já coletados pelo fluxo principal de sessões, sem exigir qualquer infraestrutura adicional de sensores. O aprendizado é incremental: quanto mais sessões acumuladas, mais precisas ficam as previsões e mais calibrada fica a detecção de anomalias.


---

## Diagrama de Arquitetura

<img width="2720" height="2480" alt="ev_chargeops_arquitetura" src="https://github.com/user-attachments/assets/60e15c27-2470-45ed-8b62-5ae5f033dd27" />


"O diagrama representa as quatro camadas da plataforma, desde o carregador físico até as interfaces de acesso do gestor e do usuário."


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
