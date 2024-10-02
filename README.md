# Golang Curso - Guia para Iniciantes

Bem-vindo ao repositório **Golang Curso**, que tem como objetivo auxiliar iniciantes a aprenderem a programar em Go (Golang). Abaixo, você encontrará um guia passo a passo sobre os principais conceitos, ferramentas e técnicas que você precisa conhecer para começar a programar com a linguagem Go.

## Sumário

1. [Instalação do Go](#instalacao-do-go)
2. [Primeiros Passos com Go](#primeiros-passos-com-go)
3. [Estrutura de um Programa Go](#estrutura-de-um-programa-go)
4. [Tipos de Dados](#tipos-de-dados)
5. [Controle de Fluxo](#controle-de-fluxo)
6. [Funções](#funcoes)
7. [Manipulação de Pacotes](#manipulacao-de-pacotes)
8. [Trabalhando com Goroutines](#trabalhando-com-goroutines)
9. [Go Modules e Dependências](#go-modules-e-dependencias)
10. [Boas Práticas e Dicas](#boas-praticas-e-dicas)
11. [Recursos Adicionais](#recursos-adicionais)

---

## 1. Instalação do Go <a name="instalacao-do-go"></a>

Antes de começar a programar em Go, você precisa instalar a linguagem no seu sistema. Siga os passos abaixo para instalar o Go:

### Instalação no Windows:

1. Acesse [o site oficial do Go](https://golang.org/dl/) e baixe o instalador apropriado para seu sistema operacional.
2. Execute o instalador e siga as instruções.
3. Após a instalação, abra o terminal (ou PowerShell) e digite `go version` para verificar se o Go foi instalado corretamente.

### Instalação no Linux/MacOS:

1. No terminal, execute os comandos abaixo:

   ```bash
   wget https://golang.org/dl/go1.XX.X.linux-amd64.tar.gz
   sudo tar -C /usr/local -xzf go1.XX.X.linux-amd64.tar.gz
   export PATH=$PATH:/usr/local/go/bin
   ```

2. Verifique a instalação com `go version`.

---

## 2. Primeiros Passos com Go <a name="primeiros-passos-com-go"></a>

Depois de instalar o Go, vamos criar nosso primeiro programa.

1. Crie um novo diretório para o seu projeto:

   ```bash
   mkdir meu_primeiro_programa
   cd meu_primeiro_programa
   ```

2. Crie um arquivo chamado `main.go`:

   ```go
   package main

   import "fmt"

   func main() {
       fmt.Println("Olá, Go!")
   }
   ```

3. Execute o programa:

   ```bash
   go run main.go
   ```

Se tudo estiver correto, você verá a mensagem **"Olá, Go!"** no terminal.

---

## 3. Estrutura de um Programa Go <a name="estrutura-de-um-programa-go"></a>

Todo programa Go começa com o pacote `main` e uma função `main`. Essa função é o ponto de entrada do programa. Além disso, utilizamos o pacote `fmt` para realizar saídas no terminal.

```go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

### Explicação:

- `package main`: Define o pacote principal do programa.
- `import "fmt"`: Importa o pacote `fmt`, usado para imprimir no console.
- `func main()`: Função principal onde o programa inicia sua execução.

---

## 4. Tipos de Dados <a name="tipos-de-dados"></a>

Go possui diversos tipos de dados. Os mais comuns são:

- **int**: Inteiros.
- **float64**: Números com ponto flutuante.
- **string**: Cadeias de caracteres.
- **bool**: Booleanos (verdadeiro ou falso).

Exemplo de uso:

```go
package main

import "fmt"

func main() {
    var idade int = 25
    var altura float64 = 1.75
    nome := "Mateus"
    aprovado := true

    fmt.Printf("Nome: %s, Idade: %d, Altura: %.2f, Aprovado: %t\n", nome, idade, altura, aprovado)
}
```

---

## 5. Controle de Fluxo <a name="controle-de-fluxo"></a>

Go oferece as estruturas de controle típicas de outras linguagens, como:

- **if/else**: Para controle condicional.
- **for**: Para loops.
- **switch**: Para múltiplas condições.

### Exemplo:

```go
package main

import "fmt"

func main() {
    idade := 18

    if idade >= 18 {
        fmt.Println("Você é maior de idade.")
    } else {
        fmt.Println("Você é menor de idade.")
    }

    for i := 0; i < 5; i++ {
        fmt.Println(i)
    }

    switch idade {
    case 18:
        fmt.Println("Exatamente 18 anos!")
    default:
        fmt.Println("Idade desconhecida.")
    }
}
```

---

## 6. Funções <a name="funcoes"></a>

Em Go, funções são declaradas usando a palavra-chave `func`. Elas podem ou não retornar valores.

```go
package main

import "fmt"

func soma(a int, b int) int {
    return a + b
}

func main() {
    resultado := soma(3, 4)
    fmt.Println("Resultado:", resultado)
}
```

---

## 7. Manipulação de Pacotes <a name="manipulacao-de-pacotes"></a>

Pacotes em Go permitem organizar e reutilizar código. Para usar pacotes de terceiros ou criar seus próprios, é importante entender como Go lida com dependências.

1. Instale pacotes usando:

   ```bash
   go get github.com/nome_do_pacote
   ```

2. Importe o pacote no seu código:

   ```go
   import "github.com/nome_do_pacote"
   ```

---

## 8. Trabalhando com Goroutines <a name="trabalhando-com-goroutines"></a>

Go é conhecido por seu suporte ao **paralelismo** com **goroutines**, que são leves e de fácil uso para executar tarefas concorrentes.

```go
package main

import (
    "fmt"
    "time"
)

func rotina() {
    fmt.Println("Executando goroutine")
}

func main() {
    go rotina()  // Inicia uma goroutine
    time.Sleep(time.Second) // Aguarda para ver o resultado
}
```

---

## 9. Go Modules e Dependências <a name="go-modules-e-dependencias"></a>

Os módulos são o sistema de gerenciamento de dependências do Go. Para iniciar um novo módulo, basta executar:

```bash
go mod init meu_modulo
```

Isso criará o arquivo `go.mod`, onde as dependências do projeto serão gerenciadas.

---

## 10. Boas Práticas e Dicas <a name="boas-praticas-e-dicas"></a>

- **Nomeie bem suas variáveis e funções**: Utilize nomes descritivos para facilitar a manutenção do código.
- **Comentários**: Explique trechos complexos de código com comentários claros.
- **Testes**: Sempre escreva testes para validar seu código. Use o pacote `testing` para criar testes unitários.
- **Erros**: Em Go, o tratamento de erros é feito manualmente. Sempre verifique erros e lide com eles adequadamente.

---

## 11. Recursos Adicionais <a name="recursos-adicionais"></a>

Aqui estão alguns recursos que podem ajudá-lo a se aprofundar mais na linguagem Go:

- [Documentação Oficial do Go](https://golang.org/doc/)
- [Tour do Go](https://tour.golang.org/welcome/1)
- [Effective Go](https://golang.org/doc/effective_go.html)

---

Esperamos que este guia ajude você a dar os primeiros passos na programação com Go!
