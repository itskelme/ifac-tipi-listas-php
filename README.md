# Listas de Programação Web em PHP

> Dezenove exercícios de lógica de programação resolvidos em PHP, cada um com formulário HTML e página de resultado.

**Contexto:** IFAC · Técnico em Informática para Internet (TIPI) · Programação Web · 2º ano · 2022

## Sobre

O projeto reúne as respostas da lista de exercícios de Programação Web. A página `index.html` mostra todas as questões, uma embaixo da outra, cada uma com seu formulário. Ao enviar, o formulário faz um `POST` para o arquivo `php/lista-NN.php` correspondente, que lê os valores com `$_POST`, faz o cálculo e devolve o resultado numa página simples.

O objetivo foi praticar o básico de PHP no servidor: receber dados de formulário, usar variáveis e operadores, `if`/`elseif`/`else`, laços `while` e montar HTML com `echo`.

## Funcionalidades

| Questão | O que faz |
|---|---|
| 01 | Lê um número e mostra o antecessor e o sucessor. |
| 02 | Lê o lado de um quadrado (cm) e mostra área e perímetro. |
| 03 | Lê um horário (`HH:MM`) e calcula quantos minutos se passaram desde 00:00. |
| 04 | Diz se o número é positivo, negativo ou nulo. |
| 05 | Lê dois números e diz qual é o maior. |
| 06 | Lê dois números, diz se são iguais ou diferentes e, se diferentes, qual é o maior. |
| 07 | Lê três lados, verifica se formam um triângulo e classifica em equilátero, isósceles ou escaleno. |
| 08 | Lê três números e diz qual é o maior e qual é o menor. |
| 09 | Calculadora com as quatro operações (escolhidas por botão de opção), com aviso para divisão por zero. |
| 10 | Lê três números e mostra em ordem crescente (recusa ordenar se houver números iguais). |
| 11 | Verifica se o número está no intervalo de 10 a 500. |
| 12 | Lê dois números e diz qual é o maior. A validação em JavaScript (`js/script.js`) impede o envio se os números forem iguais. |
| 13 | Lista os números pares de 1 a 1000 (sem formulário). |
| 14 | Lê sete números e mostra o quadrado de cada um. |
| 15 | Lista os múltiplos de 5 de 1 a 40 (sem formulário). |
| 16 | Mostra a soma de todos os números de 1 a 100 (sem formulário). |
| 17 | Lê um número e lista os ímpares menores ou iguais a ele, em ordem decrescente, até 1. |
| 18 | Lista os pares de 1 a 250 e, ao final, a soma deles (sem formulário). |
| 19 | Lê dois números e lista o intervalo entre eles em ordem crescente e depois decrescente. |

## Tecnologias

- PHP (`$_POST`, `if`/`else`, `while`, `date()` e `strtotime()` na questão 03)
- HTML5 e CSS3 (`php/css/`)
- JavaScript puro para validar o formulário da questão 12

Não usa banco de dados nem bibliotecas externas.

## Estrutura do projeto

| Caminho | Descrição |
|---|---|
| `index.html` | Página inicial com os formulários das 19 questões. |
| `php/lista-01.php` … `php/lista-19.php` | Uma questão por arquivo: lê os dados enviados e imprime o resultado. |
| `php/css/reset.css`, `style.css`, `forms.css` | Estilos da página inicial e das páginas de resultado. |
| `php/favicon.ico` | Ícone das páginas. |
| `php/teste.php` | Arquivo vazio. |
| `js/script.js` | Validação da questão 12 (campos vazios ou números iguais). |
| `js/lista-08.js` | Tentativa de validação para a questão 08. Está comentada no `index.html` e não é usada. |
| `images/` | Ícones de sucesso e erro usados na validação da questão 12. |
| `.vscode/` | Configurações do VS Code (corretor ortográfico e depuração no navegador). |

## Como rodar

### Pré-requisitos

- PHP 7.4 ou superior instalado, **ou** o XAMPP (que já traz Apache e PHP).
- Um navegador.

### Passo a passo

Com o servidor embutido do PHP, a partir da raiz do repositório:

```bash
git clone https://github.com/itskelme/ifac-tipi-listas-php.git
cd ifac-tipi-listas-php
php -S localhost:8000
```

Abra http://localhost:8000 no navegador.

Com o XAMPP:

1. Copie a pasta `ifac-tipi-listas-php` para `C:\xampp\htdocs\`.
2. Inicie o Apache no painel do XAMPP.
3. Abra http://localhost/ifac-tipi-listas-php/

O servidor precisa ser iniciado na raiz do repositório, porque os formulários do `index.html` apontam para `php/lista-NN.php`.

## Como usar

1. Na página inicial, role até a questão desejada.
2. Preencha os campos e clique em **Enviar**. Nas questões 13, 15, 16 e 18 basta clicar em **Ir ao PHP**.
3. O resultado aparece numa nova página. Use o botão voltar do navegador para testar outra questão.

Os arquivos de resultado dependem do `POST` do formulário. Abrir `php/lista-01.php` direto na barra de endereço gera avisos de índice indefinido.

## Observações

Pontos conhecidos do código, mantidos como foram entregues:

- A descrição da questão 16 no `index.html` repete o texto da 18 (pares de 1 a 250), mas `lista-16.php` calcula a soma de 1 a 100.
- Questão 08: combinações com números repetidos, como `2, 2, 1`, caem no `else` final e mostram o maior e o menor trocados.
- Questão 10: a checagem de igualdade não compara o 1º com o 3º número, então `1, 2, 1` sai fora de ordem.
- Questão 07: o teste usa `>` em vez de `>=`, então lados como `1, 1, 2` são aceitos como triângulo.
- Os valores digitados são impressos sem `htmlspecialchars()`.
- `lista-02.php` aponta o favicon para `pfavicon.ico`, que não existe.

## Referências

- [PHP: `$_POST`](https://www.php.net/manual/pt_BR/reserved.variables.post.php)
- [PHP: estruturas de controle (`if`, `while`)](https://www.php.net/manual/pt_BR/language.control-structures.php)
- [PHP: `date()`](https://www.php.net/manual/pt_BR/function.date.php) e [`strtotime()`](https://www.php.net/manual/pt_BR/function.strtotime.php)
- [PHP: servidor web embutido](https://www.php.net/manual/pt_BR/features.commandline.webserver.php)
- [MDN: enviando dados de formulário](https://developer.mozilla.org/pt-BR/docs/Learn/Forms/Sending_and_retrieving_form_data)

## Autores

- Diego Kelme Santos da Silva — [@itskelme](https://github.com/itskelme)

## Licença

Este projeto está sob a licença [CC BY-NC 4.0](LICENSE): uso pessoal e modificação permitidos com atribuição; uso comercial proibido.
