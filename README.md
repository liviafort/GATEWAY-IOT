# Sistema de Automação Residencial IoT

## 👨‍🏫 Instituição
**INSTITUTO FEDERAL DE EDUCAÇÃO, CIÊNCIA E TECNOLOGIA DA PARAÍBA**  
Campus Campina Grande  
**Bacharelado em Engenharia da Computação**

## 🧑‍🤝‍🧑 Equipe
- **Allan Victor Fonseca Pontes**
- **Jeremias Samuel Lucena Marques**
- **João Victor**
- **Livia Maria Fortunato de Sousa**
- **Disraeli Michelangelo Rafael da Costa Filho**

## 📅 Projeto
**Projeto de IoT - 2025.1**

## 📋 Descrição
Desenvolvimento de um sistema de automação residencial inteligente baseado em IoT, com foco em controle remoto, monitoramento e integração com a nuvem. Este repositório contém a implementação do **Gateway IoT (Grupo 2)**, responsável pela comunicação entre os dispositivos finais (Grupo 1) e a infraestrutura em nuvem (Grupo 3).

## 🌐 Arquitetura
A arquitetura do sistema pode ser visualizada através do diagrama completo no arquivo arquitetura do próprio repositório.
---

## ⚙️ Justificativa das Tecnologias

### 🔌 **Protocolo Zigbee**
- **Objetivo**: Integração com sensores de temperatura, umidade e presença.
- **Características**:
  - Baixo consumo de energia.
  - Alcance de alguns metros, adequado para sensores.
  - Topologia **mesh**, aumentando o alcance e garantindo confiabilidade, mesmo em ambientes com obstáculos.

### 📡 **Protocolo WiFi**
- **Objetivo**: Comunicação rápida e constante com atuadores de iluminação e fechaduras eletrônicas.
- **Características**:
  - Maior consumo de energia, mas balanceado pela alimentação elétrica dos atuadores.
  - Maior alcance e volume de dados, ideal para baixa latência e controle de dispositivos como iluminação e fechaduras.

### 📡 **Protocolo MQTT**
- **Objetivo**: Comunicação entre o **Gateway** e a **Nuvem**.
- **Características**:
  - Leve e eficiente, consome poucos recursos de processamento e energia.
  - Suporta **QoS** (qualidade de serviço), oferecendo diferentes níveis de confiabilidade na entrega de mensagens.
  - Arquitetura **publish/subscribe**, permitindo comunicação bidirecional eficiente entre todos os componentes do sistema.

---

## 🖥️ Hardware Utilizado

### **ESP32-C6** - Gateway
- Suporte nativo a **WiFi 6 (802.11ax)**, **Bluetooth 5** e **Zigbee 3.0**.
- Processador **RISC-V de 32 bits**, ideal para pré-processamento de dados.
- Modos de baixo consumo de energia para operação contínua.
- Custo acessível comparado a soluções que exigiriam múltiplos dispositivos.

### **ESP32-S3** - Dispositivos Finais
- Utilizados nos dispositivos finais do Grupo 1 para integração com sensores e atuadores.

### **Sensores**:
- **DHT22**: Temperatura e umidade.
- **BME280**: Temperatura, umidade e pressão atmosférica.
- **PIR**: Detecção de movimento.

### **Atuadores**:
- Relés
- LEDs
- Servo motor

---

## 🛠️ Funcionalidades Implementadas no Gateway

### 1. **Interface com Dispositivos Finais**  
- **WiFi**: Comunicação com dispositivos de iluminação inteligente e controle de acesso.
- **Coordinator Zigbee**: Integração com sensores ambientais (temperatura, umidade e presença).

### 2. **Processamento de Dados**  
- Pré-processamento dos dados brutos recebidos dos dispositivos.
- Filtragem de ruído e validação das leituras.
- Agregação de dados periódicos dos sensores ambientais.
- Buffer local para armazenamento temporário em caso de falha de conexão.

### 3. **Segurança**  
- Autenticação de dispositivos na conexão inicial.
- Criptografia **AES-128** para comunicação interna.
- **TLS/SSL** para comunicação segura com a nuvem.
- Proteção contra ataques comuns em dispositivos IoT.

### 4. **Comunicação com a Nuvem**  
- Cliente MQTT configurado com **QoS 1** para garantir entrega de mensagens.
- Sistema de reconexão automática em falhas de rede.
- Formatação padronizada de dados para processamento na nuvem.
- Comunicação bidirecional para recebimento de comandos da nuvem.

---

## 💻 Tecnologias Utilizadas

### **Hardware**
- **ESP32-C6**: Plataforma principal do Gateway.
- **ESP32-S3**: Dispositivos finais do Grupo 1.
- **Sensores**: DHT22, BME280, PIR.
- **Atuadores**: Relés, LEDs, Servo motor.

### **Software**
- **ESP-IDF**: Framework de desenvolvimento.
- **MQTT**: Protocolo de comunicação com a nuvem.
- **TLS/SSL**: Segurança na comunicação.
- **FreeRTOS**: Sistema operacional em tempo real.



