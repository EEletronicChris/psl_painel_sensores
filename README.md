# PSL — Painel de Sensores

Este repositório se destina ao desenvolvimento do projeto final da unidade curricular Programação em Sistamas Linux. O projeto consiste na elaboração de um programa que implementa um painel de monitoramento de sensores em ambiente Linux, executando em segundo plano como um serviço do sistema e exibindo métricas de hardware e ambiente em tempo real.


## Requisitos do Produto

O sistema foi projetado para atender aos seguintes pilares técnicos:

- **Daemon e `systemd`:** Execução contínua em segundo plano gerenciada como um serviço nativo do Linux.
- **Concorrência:** Leitura simultânea e não bloqueante dos múltiplos sensores.
- **IPC e Protocolo:** Comunicação entre processos/threads via fila de mensagens com controle de acesso por *mutex*.
- **Interface:** Visualização clara das leituras em tempo real.
- **Qualidade:** Tratamento de falhas e boas práticas de código.
- **Construção e Documentação:** Automação de *build* e documentação técnica completa.


##Sensores Monitoradoss (Previsão)

| Categoria | Sensor / Métrica | Descrição |
| :--- | :--- | :--- |
| **Hardware & Energia** | Temperatura da CPU | Monitoramento térmico do processador |
| **Hardware & Energia** | Outras temperaturas | Sensores térmicos auxiliares do hardware |
| **Hardware & Energia** | Velocidade de *Fan* | Rotação das ventoinhas (RPM) |
| **Hardware & Energia** | Tensão da bateria | Voltagem e estado de alimentação |
| **Ambiente & Movimento** | Sensor Hall | Detecção de campo magnético / estado de tampa |
| **Ambiente & Movimento** | Sensor de luz ambiente | Nível de luminosidade externa |
| **Ambiente & Movimento** | Acelerômetro, giroscópio e bússola | Orientação, aceleração e direção magnética |
| **Localização** | GPS | Coordenadas geográficas e posicionamento |


## Arquitetura e Concorrência (A definir)

- **Modelo de Execução:** **1 processo dedicado por sensor** *(ou 1 processo principal com 1 thread por sensor)*.
- **Comunicação (IPC):** As leituras são enviadas para uma **fila compartilhada** sincronizada com **`mutex`**, prevenindo condições de corrida (*race conditions*) durante a leitura e escrita simultânea.


### Instruções de compilação



### Instalação como Serviço (`systemd`)


### Execução da Interface


## Estrutura do Repositório

