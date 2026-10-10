# Aplicativo de Controle de Entrada / Saída

Este projeto é um aplicativo Flutter para controlar a quantidade de pessoas dentro de um ambiente, como um restaurante, loja ou sala de aula. A interface exibe a quantidade atual, informa se a entrada está liberada ou se o local está cheio e permite aumentar ou diminuir a contagem com botões.

## Objetivo

Desenvolver uma aplicação simples e didática para ensinar conceitos básicos de Flutter e Dart, como:

- criação de interface com widgets;
- uso de estado com `StatefulWidget`;
- manipulação de variáveis;
- eventos de clique em botões;
- condicionais para limitar a capacidade;
- uso de imagens e estilos visuais.

## Funcionalidades

- contador de pessoas com valor inicial em `0`;
- botão para registrar entrada;
- botão para registrar saída;
- limite máximo de `30` pessoas;
- mensagem dinâmica:
  - `Pode entrar!` quando a capacidade ainda não foi atingida;
  - `Casa cheia!` quando o limite é alcançado;
- interface visual com fundo e imagem de ambiente.

## Estrutura do projeto

```text
app-contador-flutter/
├── android/              # projeto Android
├── ios/                  # projeto iOS
├── lib/
│   └── main.dart         # código principal da aplicação
├── imagens/
│   └── restaurant.png    # imagem de fundo usada na tela
├── test/                 # testes automatizados
├── .metadata
├── .gitignore
├── analysis_options.yaml
├── pubspec.yaml          # dependências e configuração do Flutter
├── README.md             # documentação do projeto
└── ...
```

## Tecnologias

- Flutter
- Dart
- Material Design

## Pré-requisitos

Antes de executar o projeto, certifique-se de que o ambiente está preparado:

- Flutter SDK instalado;
- Android Studio ou VS Code configurado;
- Emulador Android ou dispositivo físico conectado;
- Git instalado (opcional, para clonagem).

## Como executar o projeto

1. Clone o repositório:

```bash
git clone https://github.com/faurizel-mobile/app-contador-flutter.git
cd app-contador-flutter
```

2. Instale as dependências:

```bash
flutter pub get
```

3. Verifique se o Flutter está funcionando corretamente:

```bash
flutter doctor
```

4. Execute a aplicação:

```bash
flutter run
```

Se houver mais de um dispositivo/emulador disponível, selecione um da lista.

## Procedimento didático para a aula (passo a passo)

A seguir está uma proposta de roteiro para a aula, com abordagem prática e simples.

### Etapa 1 - Apresentação do problema

Explique que o objetivo é criar um sistema para controlar a quantidade de pessoas em um ambiente. Pergunte:

- Como a gente pode representar essa contagem?
- Como mostrar mensagens condicionalmente?
- Como impedir que a quantidade passe do limite?

Nesse momento, a ideia é conectar o aplicativo com um problema real, como restaurante, cinema ou sala de aula.

### Etapa 2 - Explicação do projeto

Mostre a estrutura do projeto e a função principal:

```dart
void main() {
  runApp(
    MaterialApp(
      home: Contador(),
    ),
  );
}
```

Comente que:

- `runApp()` inicia a aplicação;
- `MaterialApp` define o tema visual do app;
- `home` define a tela principal.

### Etapa 3 - Criação do estado da tela

Apresente a classe `Contador` e a ideia de `StatefulWidget`.

```dart
class Contador extends StatefulWidget {
  const Contador({super.key});

  @override
  State<Contador> createState() => _ContadorState();
}
```

Explique que o widget precisa ser "mutável" porque o valor do contador muda durante a execução do app.

### Etapa 4 - Variável do contador

Mostre a variável principal:

```dart
int contador = 0;
```

Explique que esse número representa a quantidade de pessoas no ambiente e será atualizado toda vez que o usuário clicar nos botões.

### Etapa 5 - Funções de incremento e decremento

Apresente as funções:

```dart
void increment() {
  setState(() {
    if (contador < 30) {
      contador++;
    }
  });
}

void decrement() {
  setState(() {
    if (contador > 0) {
      contador--;
    }
  });
}
```

Discuta:

- `setState()` informa ao Flutter que a interface precisa ser atualizada;
- `if (contador < 30)` impede que o valor ultrapasse o limite;
- `if (contador > 0)` evita contagem negativa.

### Etapa 6 - Mensagem condicional

Mostre a lógica de exibição da mensagem:

```dart
Text(contador < 30 ? "Pode entrar!" : "Casa cheia!")
```

Explique o operador ternário:

- se a condição for verdadeira, mostra `Pode entrar!`;
- caso contrário, mostra `Casa cheia!`.

### Etapa 7 - Construção da interface

Explique os principais widgets usados:

- `Scaffold` -> estrutura da tela;
- `Container` -> container com imagem de fundo;
- `Column` -> alinhamento vertical;
- `Row` -> alinhamento dos botões;
- `TextButton` -> botões clicáveis;
- `Text` -> textos da interface.

A imagem de fundo é carregada com:

```dart
DecorationImage(
  image: AssetImage("imagens/restaurant.png"),
  fit: BoxFit.cover,
)
```

### Etapa 8 - Teste e validação

No emulador, peça que os alunos:

1. abram o projeto;
2. executem `flutter run`;
3. testem os botões de entrada e saída;
4. verifiquem a mudança na mensagem e no contador;
5. confirmem que o limite de 30 não é ultrapassado.

### Etapa 9 - Debriefing da aula

Conduza uma reflexão com perguntas como:

- O que acontece quando o contador chega a 30?
- Por que usamos `setState()`?
- Qual a função do `if` no código?
- Como esse projeto pode ser expandido para outra funcionalidade?

### Etapa 10 - Exercício complementar

Sugira desafios para os alunos:

- adicionar campo para nome do ambiente;
- criar limite configurável;
- alterar a cor da tela conforme a lotação;
- adicionar histórico de entradas/saídas;
- criar um botão para resetar o contador.

## Dicas para aula prática

- comece pela lógica do contador antes da estética;
- ensine o uso de `StatefulWidget` como base para interfaces dinâmicas;
- mostre como a UI reage às mudanças de estado;
- destaque a importância da organização do código em blocos lógicos.

## Observações finais

Este projeto é uma excelente introdução ao desenvolvimento em Flutter porque trabalha com conceitos simples e visualmente imediatos. Ele permite que os alunos entendam, de forma prática, como a interface interage com dados e como pequenas decisões de programação geram comportamento real no aplicativo.

## Autor

Projeto desenvolvido em Flutter para fins didáticos.

## Licença

Este projeto foi criado para fins de aprendizado e pode ser adaptado conforme a necessidade da aula.

---

Se quiser, posso também criar uma versão do README com foco em uma aula mais estruturada por disciplina, por exemplo:

- README para professor;
- README para alunos;
- README com objetivos de aprendizagem, competências e avaliação.
