# 🧑‍💻 Sistema de Gerenciamento de Nomes

### Descrição

Este projeto é uma aplicação web para gerenciamento de nomes de usuários. Implementado com HTML, CSS e JavaScript, o sistema permite cadastrar, visualizar, editar e remover nomes em uma lista dinâmica, essa atividade foi proposta pelo docente Leonardo Rocha.

<br>
------------------------------------------------------------------------------------------------------------------

<br>

## Funcionalidades Principais

- **Autenticação Básica:** Valida e redireciona usuários para a página de cadastro se os campos de e-mail e senha estiverem preenchidos.
- **Cadastro de Nomes:** Adiciona nomes à lista e os mostra em uma tabela.
- **Visualização e Edição:** Exibe a lista de nomes com opções para editar ou excluir entradas.
- **Exclusão de Nomes:** Remove nomes da lista e atualiza a visualização.

<br>

## Código Fonte

### Função de Autenticação
```javascript
function acessar() {
    let loginEmail = document.getElementById('loginEmail').value;
    let loginSenha = document.getElementById('loginSenha').value;
    
    if (!loginEmail || !loginSenha) {
        alert("Preencha todos os campos.");
    } else {
        window.location.href = 'cadastro.html';
    }
}
```

### Função para Salvar Nomes
```javascript
var dadosLista = [];
 
function salvarUser() {
    let nomeUser = document.getElementById('nomeUser').value;
    if (nomeUser) {
        dadosLista.push(nomeUser);
        criaLista();
        document.getElementById('nomeUser').value = "";
    } else {
        alert("Informe um nome.");
    }
}
```

### Função para Criar Tabela
```javascript
function criaLista() {
    let tabela = "<tr><th>Nome</th><th>Ações</th></tr>";
    for (let i = 0; i < dadosLista.length; i++) {
        tabela += `<tr><td>${dadosLista[i]}</td>
                   <td>
                       <button onclick='editar(${i})'>Editar</button>
                       <button onclick='excluir(${i})'>Excluir</button>
                   </td></tr>`;
    }
    document.getElementById('tabela').innerHTML = tabela;
}
```

### Função de Edição
```javascript
function editar(i) {
    document.getElementById('nomeUser').value = dadosLista[i];
    dadosLista.splice(i, 1);
}
```

### Função de Exclusão
```javascript
function excluir(i) {
    dadosLista.splice(i, 1);
    criaLista(); // Atualiza a lista após exclusão
}
```

<br>

## Tecnologias Usadas

- **HTML5:** Estrutura da Página
- **JavaScript:** Lógica e Interatividade


<br>

## Instruções Rápidas

1. Crie um arquivo HTML e inclua o código JavaScript fornecido.
2. Abra o arquivo em um navegador para começar a usar a aplicação.

<br>

## Métodos e Funções

- `getElementById()`: Obtém um elemento pelo seu ID.
- `value`: Obtém ou define o valor dos campos de entrada.
- `alert()`: Exibe uma mensagem de alerta.
- `window.location.href`: Redireciona o navegador.
- `push()`: Adiciona itens ao final de um array.
- `innerHTML`: Define ou obtém o HTML interno de um elemento.
- `splice()`: Remove ou adiciona itens em um array.
- `deleteRow()`: Remove uma linha de uma tabela.

<br>

# Desenvolvedor

| [<img src="https://avatars.githubusercontent.com/u/140809956?v=4" width=95><br><sub>Nicolas Modesto</sub>](https://github.com/tubarao16)
| :--: |

# Orientador

| [<img src="https://avatars.githubusercontent.com/u/86802310?v=4" width=95><br><sub>Leonardo Rocha</sub>](https://github.com/LeonardoRochaMarista)
| :---: |

---