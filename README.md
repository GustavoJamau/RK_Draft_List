# 🏆 RK Draft List & Double Elimination

> Uma ferramenta de navegador (Single-Page Application) leve, rápida e intuitiva para organizar torneios *Inhouse* de League of Legends. 

O sistema processa uma lista de 20 jogadores, define os capitães automaticamente baseando-se no balanceamento das rotas, conduz um *Draft* ao vivo e gerencia o chaveamento de Dupla Eliminação (*Double Elimination*).

---

## 🚀 Como Utilizar

### 1. Inicialização
Não é necessário instalar nada ou configurar servidores. 
* Salve o código como um arquivo `.html` (ex: `index.html`).
* Dê um duplo clique para abri-lo em qualquer navegador moderno (Chrome, Edge, Opera, Firefox).

### 2. Formatação da Lista de Jogadores
Na tela inicial, cole **exatamente 20 jogadores** (sendo rigorosamente 4 de cada rota). O formato exigido por linha é:

    ROTA - Nome do Jogador ELO

**Exemplo prático:**
    TOP - Guts CHALLENGER
    JG - Levi Ackerman GM
    MID - Gojo Satoru CHALL
    ADC - Vash the Stampede MESTRE
    SUP - Orihime Inoue DIMA

*(Dica: Adicione 4 jogadores para cada uma das 5 rotas. Linhas em branco são ignoradas automaticamente).*

---

## ⚙️ Funcionamento do Torneio

### 🛡️ Seleção de Capitães
O sistema avalia automaticamente a variação de elo de todas as rotas. Os 4 jogadores da rota **mais parelha e equilibrada** (com a menor diferença de nível entre si) são definidos como os capitães das equipes. Em caso de empate no equilíbrio, a rota com a maior soma de elos tem a preferência. Além disso, a ordem de quem começa escolhendo no Draft é **totalmente aleatória (sorteada)** pelo sistema para garantir justiça entre os times.

### 🐍 O Draft (Snake Draft)
Após o processamento, o Draft é iniciado:
- Os capitães se revezam na escolha dos jogadores disponíveis.
- Existe um cronômetro de **30 segundos** por escolha (com seleção automática caso o tempo acabe).
- **Regra de bloqueio:** Uma equipe não pode escolher dois jogadores da mesma rota.

### ⚔️ O Chaveamento
Com as equipes formadas, clique em "Gerar Chaveamento" para criar a tabela *Double Elimination*.
- **Avançar de fase:** Para definir o vencedor de uma partida, basta clicar no nome da equipe dentro do bloco do confronto.
- **Formato:** Todas as partidas da chave (Superior e Inferior) são **MD1**, enquanto a Grande Final é **MD3**.

---

## 📊 Exportação de Resultados

Ao finalizar o campeonato e definir o grande Campeão, o sistema libera o botão:
`📥 Exportar Planilha de Resultados`

Isso irá gerar e baixar um arquivo `.csv` automaticamente, contendo a classificação final (1º ao 4º lugar), o nome das equipes e a escalação exata de cada membro na sua respectiva rota, pronto para ser aberto no Excel ou Google Sheets.

---

## 📚 Elos e Abreviações Suportadas

O sistema é inteligente e flexível. Ele entende as seguintes variações na hora de calcular a força dos jogadores:

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
