# 🏆 RK Draft List & Double Elimination

> Uma ferramenta de navegador (Single-Page Application) leve, rápida e intuitiva para organizar torneios *Inhouse* de League of Legends. 

O sistema processa uma lista de 20 jogadores, define os capitães automaticamente com base no elo ou equilíbrio, conduz um *Draft* ao vivo e gere o chaveamento de Dupla Eliminação (*Double Elimination*).

---

## 🚀 Como Utilizar

### 1. Inicialização
Não é necessário instalar nada ou configurar servidores. 
* Guarda o código como um arquivo `.html` (ex: `index.html`).
* Abre o ficheiro em qualquer navegador moderno (Chrome, Edge, Opera, Firefox).

### 2. Formatação da Lista de Jogadores
Na tela inicial, cola **exatamente 20 jogadores** (sendo rigorosamente 4 de cada rota). O formato exigido por linha é:

`ROTA - Nome do Jogador ELO`

**Exemplo prático:**
    TOP - Guts CHALLENGER
    JG - Levi Ackerman GM
    MID - Gojo Satoru CHALL
    ADC - Vash the Stampede MESTRE
    SUP - Orihime Inoue DIMA

*(Dica: Adiciona 4 jogadores para cada uma das 5 rotas. Linhas em branco são ignoradas automaticamente).*

---

## ⚙️ Funcionamento do Torneio

### 🛡️ Seleção de Capitães
Agora podes escolher entre duas regras no início:

1.  **Maior Elo Individual (Padrão):** O sistema varre a lista completa de 20 nomes e define os **4 jogadores com os maiores elos** como os capitães, independentemente da rota em que jogam.
2.  **Rota Mais Equilibrada:** O sistema avalia qual das rotas tem os jogadores com elos mais próximos entre si (menor variância) e define esses 4 jogadores como capitães.

*A ordem de quem começa a escolher no Draft é **totalmente aleatória (sorteada)** pelo sistema para garantir justiça.*

### 🐍 O Draft (Snake Draft)
Após o processamento, o Draft é iniciado:
- Os capitães revezam-se na escolha dos jogadores disponíveis.
- Existe um cronómetro de **30 segundos** por escolha (com seleção automática caso o tempo acabe).
- **Regra de bloqueio:** Uma equipa não pode escolher dois jogadores da mesma rota (o sistema bloqueia automaticamente nomes de rotas já preenchidas no teu time).

### ⚔️ O Chaveamento
Com as equipas formadas, clica em "Gerar Chaveamento" para criar a tabela *Double Elimination*.
- **Avançar de fase:** Para definir o vencedor de uma partida, basta clicar no nome da equipa dentro do bloco do confronto.
- **Lados (Blue/Red):** O sistema sorteia os lados automaticamente. Na Grande Final, o finalista invicto tem o direito de escolher o lado no sistema.
- **Formato:** Partidas da chave são **MD1**, e a Grande Final é **MD3**.

---

## 📊 Exportação de Resultados

Ao finalizar o campeonato e definir o Campeão, o sistema liberta o botão:
`📥 Exportar Planilha de Resultados`

Isto gera um ficheiro `.csv` contendo a classificação final (1º ao 4º lugar), o nome das equipas e a escalação exata de cada membro por rota.

---

## 📚 Tabela de Pesos de Elo

| Pontos | Elos Reconhecidos (PT-BR, EN e Abreviações) |
| :---: | :--- |
| **10** | `CHALL`, `CHALLENGER`, `DESAFIANTE` |
| **9** | `GM`, `GRAO MESTRE`, `GRÃO MESTRE`, `GRAO-MESTRE`, `GRANDMASTER` |
| **8** | `MESTRE`, `MASTER` |
| **7** | `DIMA`, `DIAMANTE`, `DIAMOND` |
| **6** | `ESMERALDA`, `EMERALD` |
| **5** | `PLATINA`, `PLATINUM`, `PLAT` |
| **4** | `OURO`, `GOLD` |
| **3** | `PRATA`, `SILVER` |
| **2** | `BRONZE` |
| **1** | `FERRO`, `IRON` |
