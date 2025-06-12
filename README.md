# 🚢 Batalha Naval Simplificada

Um jogo de batalha naval em C para um jogador, onde o objetivo é encontrar e afundar 3 navios escondidos em um tabuleiro 5x5.

## 📋 Características do Jogo

- **Tabuleiro:** 5x5 (25 posições)
- **Navios:** 3 submarinos (1 casa cada)
- **Jogadores:** 1 (contra o computador)
- **Posicionamento:** Automático e aleatório
- **Sistema de dicas:** Mostra quantos navios há na linha e coluna do seu tiro

## 🛠️ Como Compilar e Executar

### Pré-requisitos

- Compilador GCC instalado
- Sistema operacional com suporte a C (Windows, Linux, macOS)

### Compilação

```bash
gcc batalha_naval.c -o batalha_naval
```

### Execução

```bash
./batalha_naval
```

## 🎮 Como Jogar

### Objetivo

Encontre e afunde os 3 navios escondidos no tabuleiro com o menor número de tentativas possível.

### Interface do Tabuleiro

```
	1 	2 	3 	4 	5
1	~	~	~	~	~
2	~	~	*	~	~
3	~	~	~	X	~
4	~	~	~	~	~
5	~	~	~	~	~
```

#### Símbolos:

- **~** : Água (posição não atacada)
- **\*** : Tiro na água (erro)
- **X** : Navio atingido (acerto)

### Como Atacar

1. **Digite a linha** (1 a 5)
2. **Digite a coluna** (1 a 5)

Exemplo:

```
	1 	2 	3 	4 	5
1	~	~	~	~	~
2	~	~	~	~	~
3	~	~	~	~	~
4	~	~	~	~	~
5	~	~	~	~	~

Linha: 3
Coluna: 4
```

### Sistema de Dicas

Após cada tiro, o jogo fornece dicas valiosas:

```
Dica 1:
linha 3 -> 1 navios
coluna 4 -> 2 navios
```

**Interpretação:**

- Na linha 3 há **1 navio**
- Na coluna 4 há **2 navios**

### Resultados dos Tiros

#### ✅ Acerto

```
Você acertou o tiro (3,4)

Dica 1:
linha 3 -> 1 navios
coluna 4 -> 2 navios
```

#### ❌ Erro

```
Dica 2:
linha 2 -> 0 navios
coluna 1 -> 1 navios
```

### Fim do Jogo

O jogo termina quando você acerta os 3 navios:

```
Jogo terminado. Você acertou os 3 navios em 8 tentativas

	1 	2 	3 	4 	5
1	~	~	*	X	~
2	*	~	~	~	~
3	~	~	~	X	*
4	~	X	~	~	~
5	*	~	~	~	~
```

## 🎯 Estratégias e Dicas

### 1. Use as Dicas Inteligentemente

- Se uma linha tem **0 navios**, não atire mais nela
- Se uma linha tem **1 navio** e você já acertou, não atire mais nela
- Foque nas linhas/colunas com mais navios

### 2. Padrão de Busca Eficiente

- Comece com um padrão em diagonal ou xadrez
- Use as dicas para refinar sua busca

### 3. Exemplo de Estratégia

```
Tiro 1: (3,3) -> "linha 3 -> 1 navios, coluna 3 -> 0 navios"
Conclusão: O navio da linha 3 NÃO está na coluna 3

Tiro 2: (3,1) -> "linha 3 -> 1 navios, coluna 1 -> 1 navios"
Conclusão: Pode ser que o navio esteja em (3,1)

Tiro 3: (1,1) -> "linha 1 -> 0 navios, coluna 1 -> 1 navios"
Conclusão: O navio da coluna 1 NÃO está na linha 1, então está na linha 3!
```

## 📊 Pontuação

Tente conseguir a menor quantidade de tentativas possível:

- **3-5 tentativas:** 🏆 Excelente!
- **6-8 tentativas:** 😊 Muito bom!
- **9-12 tentativas:** 👍 Bom!
- **13+ tentativas:** 🤔 Pode melhorar...

## 🔧 Estrutura do Código

### Funções Principais:

- **`inicializaTabuleiro()`** - Inicializa o tabuleiro com água (~)
- **`iniciaNavios()`** - Posiciona 3 navios aleatoriamente
- **`mostraTabuleiro()`** - Exibe o tabuleiro atual
- **`darTiro()`** - Captura a entrada do jogador
- **`acertou()`** - Verifica se o tiro acertou um navio
- **`dica()`** - Calcula e mostra as dicas
- **`alteraTabuleiro()`** - Atualiza o tabuleiro com o resultado

### Lógica do Jogo:

1. Inicializa tabuleiro vazio
2. Posiciona 3 navios aleatoriamente (sem sobreposição)
3. Loop principal:
   - Mostra tabuleiro
   - Jogador atira
   - Verifica acerto/erro
   - Mostra dicas
   - Atualiza tabuleiro
4. Termina quando todos os 3 navios são encontrados

## 🚀 Possíveis Melhorias

- Adicionar níveis de dificuldade (tabuleiros maiores)
- Implementar navios de tamanhos diferentes
- Adicionar modo multiplayer
- Sistema de ranking/recordes
- Interface gráfica

---

**Divirta-se caçando navios! ⚓**
