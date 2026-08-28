# 📊 PGAM - Plataforma de Gestão Acessível para Microempreendedores

![Status do Projeto](https://img.shields.io/badge/Status-Concluído-brightgreen)
![Acessibilidade](https://img.shields.io/badge/Acessibilidade-WCAG_2.1_AAA-blue)
![Sustentabilidade](https://img.shields.io/badge/Sustentabilidade-TI_Verde-success)
![Tecnologias](https://img.shields.io/badge/Tech-HTML5_%7C_CSS3_%7C_Vanilla_JS-orange)

> Uma aplicação web leve, inclusiva e offline-first desenhada para democratizar a gestão financeira e a precificação para pequenos produtores artesanais e autônomos.

---


## 📸 Demonstração Visual
| :---: | :---: | :---: |

<img width="1044" height="886" alt="Captura de Tela (156)" src="https://github.com/user-attachments/assets/59b4f8ed-1b37-4f9e-8b66-53f3efea9f2e" /> | 
<img width="1062" height="888" alt="Captura de Tela (157)" src="https://github.com/user-attachments/assets/b6bec922-150a-4aa4-8d9a-c11507271700" /> | 
<img width="1044" height="883" alt="Captura de Tela (158)" src="https://github.com/user-attachments/assets/97563f86-1f4d-4a06-a933-5f8d2ad21b7d" />


---

## 📖 Visão Geral e Contexto (O Problema)

Microempreendedores e artesãos — especialmente os que trabalham com produtos fracionados como papelaria criativa, encadernação, impressão personalizada e confeitaria — enfrentam uma alta taxa de mortalidade nos negócios. O motivo principal não é a falta de vendas, mas a **precificação incorreta** e o **descontrole do fluxo de caixa**.

Os softwares de gestão (ERPs) atuais do mercado apresentam grandes barreiras:
1. **Linguagem excludente:** Uso de jargões técnicos (DRE, Fluxo de Caixa Projetado).
2. **Exigência de Hardware:** Sistemas pesados que não rodam em smartphones antigos.
3. **Dependência de Conexão:** Falham em regiões periféricas com internet intermitente.

A **PGAM** resolve esse problema traduzindo a gestão financeira para uma interface mobile-first, com linguagem humana ("Dinheiro que Entrou", "Sobrou no Bolso") e foco absoluto em acessibilidade.

---

## 🚀 Como Funciona e Exemplos Práticos

A plataforma concentra-se nas rotinas diárias essenciais:
* **Registrador Rápido (Caixa):** Com dois toques, o usuário registra entradas e saídas.
* **Calculadora de Precificação:** O usuário insere os custos fracionados (ex: custo do papel autocopiativo, fitas, tintas de impressão) e o tempo de mão de obra. O sistema calcula automaticamente o preço de venda ideal com base no lucro desejado.
* **Assistente de Áudio Nativo:** Um botão global permite que o sistema leia os valores e instruções da tela, auxiliando pessoas com baixa visão ou letramento reduzido.

---

## 🛠️ Decisões Técnicas e Arquitetura

Para garantir que o sistema rodasse nas condições mais adversas (celulares antigos, conexões instáveis), tomei as seguintes decisões de engenharia:

* **Vanilla JavaScript & DOM Leve:** Optei por não utilizar frameworks pesados (como React ou Angular). O uso de HTML5, CSS3 e JS puro garante que a aplicação carregue quase instantaneamente e consuma o mínimo de bateria e memória RAM do dispositivo (Sustentabilidade / TI Verde).
* **Armazenamento Local (LocalStorage):** Toda a persistência de dados ocorre localmente no navegador do usuário. Isso garante o funcionamento 100% **Offline** e elimina a necessidade imediata de servidores e bancos de dados complexos, além de garantir a privacidade dos dados financeiros do usuário.
* **Web Speech API:** A integração da síntese de voz nativa do navegador eliminou a necessidade de APIs externas pagas para acessibilidade de áudio, reduzindo a latência a zero.
* **Design System Acessível:** Implementação de variáveis CSS nativas para controle de tema, permitindo a alternância instantânea para um **Modo Alto Contraste** que atende às diretrizes internacionais WCAG 2.1 nível AAA.

---

## 🚧 Desafios Enfrentados e Soluções

**Desafio:** Substituir alertas invasivos do sistema (`alert()`) que causam má experiência e não são amigáveis para leitores de tela.  
**Solução:** Desenvolvi um sistema de notificações "Toast" não-bloqueantes. Essas notificações aparecem de forma sutil na tela e, simultaneamente, disparam um aviso em áudio via Web Speech API, garantindo feedback multissensorial sem travar a navegação.

**Desafio:** Atualização reativa de valores sem frameworks modernos.  
**Solução:** Utilizei *Event Listeners* (`input`) atrelados aos campos da calculadora para atualizar o DOM (Document Object Model) em tempo real. Sempre que um custo de matéria-prima é digitado, o preço sugerido é recalculado na mesma fração de segundo.

---

## 💻 Instruções de Instalação e Uso

Como a aplicação é construída com tecnologias web padrão e roda no lado do cliente (Client-side), a instalação é extremamente simples:

1. **Clone o repositório:**
   ```bash
   git clone [https://github.com/SeuUsuario/pgam-acessibilidade.git](https://github.com/SeuUsuario/pgam-acessibilidade.git)
