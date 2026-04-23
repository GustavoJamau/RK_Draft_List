# 🏆 RK Draft List & Tournament Bracket

> Uma aplicação web (Single-Page Application) leve, responsiva e intuitiva para organizar torneios *Inhouse* de League of Legends. 

O sistema processa uma lista de jogadores, define os capitães automaticamente com base no elo ou equilíbrio das rotas, conduz um *Draft* ao vivo e gerencia o chaveamento. A interface foi desenhada priorizando a organização espacial e a centralização dos elementos, garantindo que o layout da tabela se adapte perfeitamente a diferentes telas.

---

## 🚀 Como Utilizar

### 1. Inicialização
Não é necessário instalar nada ou configurar servidores. A aplicação roda diretamente no navegador.
* Salve o código fonte como um arquivo `.html` (ex: `index.html`).
* Abra o arquivo em qualquer navegador moderno (Chrome, Edge, Opera, Firefox).

### 2. Formatação da Lista de Jogadores
Na tela inicial, cole a lista de jogadores (o padrão inicial exige **exatamente 20 jogadores**, sendo rigorosamente 4 de cada rota). O formato exigido por linha é:

`ROTA - Nome do Jogador ELO`

**Exemplo prático:**
> TOP - Guts CHALLENGER
> JG - Levi Ackerman GM
> MID - Gojo Satoru CHALL
> ADC - Vash the Stampede MESTRE
> SUP - Orihime Inoue DIMA

*(Dica: Linhas em branco são ignoradas automaticamente pelo sistema).*

---

## ⚙️ Funcionamento do Torneio

### 🛡️ Seleção de Capitães
Você pode escolher entre duas regras estratégicas no início:

1. **Maior Elo Individual (Padrão):** O sistema varre a lista completa e define os **4 jogadores com os maiores elos** como os capitães, independentemente da rota em que jogam.
2. **Rota Mais Equilibrada:** O sistema avalia qual das rotas possui os jogadores com elos mais próximos entre si (menor variância) e define esses 4 jogadores como os líderes das equipes.

*A ordem de escolha no Draft é **totalmente aleatória (sorteada)** pelo sistema para garantir um processo justo.*

### 🐍 O Draft (Snake Draft)
Após o processamento e definição das lideranças, a fase de Draft é iniciada:
* Os capitães se revezam na escolha dos jogadores disponíveis.
* Há um cronômetro visual de **30 segundos** por escolha. Se o tempo esgotar, o sistema realiza um *Auto-Pick*.
* **Regra de Bloqueio:** Uma equipe não pode escolher dois jogadores da mesma rota. O sistema desabilita automaticamente as rotas já preenchidas no time atual.

### ⚔️ Estruturas e Chaveamento
Com as equipes formadas, clique em "Gerar Chaveamento" para montar a tabela interativa.

* **Layout Padrão (4 Equipes):** Gera uma tabela de Dupla Eliminação (*Double Elimination*). As partidas da chave regular são disputadas em formato **MD1**, enquanto a Grande Final é **MD3**.
* **Escalabilidade (6 Equipes):** O sistema possui arquitetura para suportar torneios maiores (até 30 jogadores). Nessas configurações, a estrutura do torneio se adapta para dois grupos de três times, mantendo a fase de grupos em **MD1** e a Grande Final em **MD3**.
* **Avançar de Fase:** Para definir o vencedor de uma partida, basta clicar no nome da equipe dentro do bloco do confronto.
* **Lados (Blue/Red):** O sistema sorteia os lados automaticamente. Na Grande Final, o time invicto recebe o direito de escolher o seu lado no sistema.

---

## 📊 Exportação de Resultados

Ao finalizar o campeonato e definir o grande Campeão, o sistema habilita o botão:
`📥 Exportar Planilha de Resultados`

Isso gera e baixa um arquivo `.csv` contendo a classificação final (1º ao 4º lugar), o nome das equipes e a escalação exata de cada membro por rota, facilitando o registro do torneio.

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
