# Dungeon_Infinita
Um pequeno mini joguinho de uma masmorra infinita

Claro! Aqui está uma documentação divertida e fácil de entender para o código:

---

# Masmorra Infinita - Um Jogo de Aventura

Bem-vindo à **Masmorra Infinita**! Este é um emocionante jogo de texto onde você, o destemido herói, explora uma masmorra cheia de perigos. Você encontrará monstros assustadores e usará suas habilidades para derrotá-los. Mas cuidado, a masmorra é traiçoeira e não há escapatória! Vamos explorar o código para entender como jogar e como ele funciona.

## Estrutura do Jogo

### Classes

O jogo é composto por duas classes principais: `Personagem` e `Batalha`.

#### Classe Personagem

Essa classe representa qualquer personagem no jogo, seja você, o herói, ou os monstros que você encontra.

```python
class Personagem:
    def __init__(self, nome, poder):
        self.nome = nome
        self.poder = poder

    def __str__(self):
        return f"\nVocê está andando pela masmorra até que um {self.nome} aparece!"
```

- **`__init__`**: Inicializa um personagem com um nome e um poder.
- **`__str__`**: Retorna uma mensagem que descreve o encontro com o personagem.

### Exemplos de Personagens

Criamos alguns personagens: um herói e três monstros.

```python
heroi = Personagem("Herói", ["Espada", "Fogo", "Água"])
esqueleto = Personagem("Esqueleto", "Espada")
monstroAcido = Personagem("Monstro de Ácido", "Ácido")
monstroFogo = Personagem("Monstro de Fogo", "Fogo")

listaMonstros = [esqueleto, monstroAcido, monstroFogo]
```

#### Classe Batalha

A classe `Batalha` controla a introdução do jogo e o sistema de combate.

```python
class Batalha:
    def introducao():
        print("Olá destemido Herói, tome cuidado dentro da masmorra, você encontrará muitos perigos!\nAcredite, essa masmorra não tem fim, e quando você entra é impossível sair")
        while True:
            startEscolha = input("Você tem certeza que deseja continuar?\n's' para SIM e 'n' para NÃO: ").lower()
            if startEscolha == "s":
                print("\nContinuando...")
                Batalha.sistemaBatalha()
                break
            elif startEscolha == "n":
                print("\nÓtima escolha Herói")
                break
            else:
                print("\nEscolha inválida. Por favor, digite 's' ou 'n'.")

    def sistemaBatalha():
        while True:
            monstroEscolhido = random.choice(listaMonstros)
            print(monstroEscolhido)
            escolhaHeroi = int(input(f"\nVocê precisa fazer alguma coisa, o que você vai fazer?\n1 - {heroi.poder[0]}\n2 - {heroi.poder[1]}\n3 - {heroi.poder[2]}\n"))

            if escolhaHeroi == 1:
                if monstroEscolhido.poder == "Espada":
                    print(f"Você ataca com sua espada!\nVocê derrotou o {monstroEscolhido.nome}")
                else:
                    print("Você morreu!")
                    Batalha.introducao()
            elif escolhaHeroi == 2:
                if monstroEscolhido.poder == "Ácido":
                    print(f"Você usou magia de fogo!\nVocê derrotou o {monstroEscolhido.nome}")
                else:
                    print("Você morreu!")
                    Batalha.introducao()
            elif escolhaHeroi == 3:
                if monstroEscolhido.poder == "Fogo":
                    print(f"Você usou magia de água!\nVocê derrotou o {monstroEscolhido.nome}")
                else:
                    print("Você morreu!")
                    Batalha.introducao()
            else:
                print("Escolha uma opção válida:")
```

- **`introducao`**: Dá boas-vindas ao jogador e pergunta se ele quer continuar.
- **`sistemaBatalha`**: Controla o fluxo de combate. O jogador escolhe uma ação e, dependendo do tipo de monstro encontrado, vence ou perde.

## Como Jogar

1. **Início do Jogo**: Ao iniciar o jogo, você será saudado e perguntado se deseja continuar.
2. **Encontro com Monstros**: Você encontrará monstros aleatoriamente.
3. **Escolha de Ação**: Escolha entre suas habilidades (Espada, Fogo, Água) para derrotar o monstro.
4. **Resultado**: Se a habilidade escolhida for eficaz contra o monstro, você vence. Caso contrário, você perde e o jogo recomeça.

## Executando o Jogo

Para iniciar a sua aventura, basta chamar a função `introducao` da classe `Batalha`.

```python
Batalha.introducao()
```

Boa sorte, destemido herói! A masmorra espera por você.

---

Agora você está pronto para enfrentar os perigos da masmorra infinita! Divirta-se jogando e quem sabe, um dia, você conseguirá escapar!
