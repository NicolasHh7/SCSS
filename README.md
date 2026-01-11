`# 📘 Introdução ao SCSS (Sass)

Este repositório tem como objetivo servir como uma introdução ao **SCSS**, abordando desde os conceitos iniciais da linguagem até o uso completo de seus principais recursos, como variáveis, mixins, aninhamento, organização de estilos e automação da compilação.

<p align="left">
  <img src="https://skillicons.dev/icons?i=git,github,html,css,sass" />
</p>


---

## 🚀 Conceitos Iniciais

O **SCSS** é uma sintaxe do **Sass (Syntactically Awesome Style Sheets)** que estende o CSS tradicional, adicionando recursos que facilitam a escrita, leitura e manutenção de estilos.

> **Observações Importantes:**
> * SCSS é um **pré-processador** de CSS.
> * O navegador **não interpreta SCSS diretamente**.
> * O código SCSS precisa ser compilado para CSS.
> * Todo código CSS válido também é SCSS válido.

---

## 📦 Organização e Escopo de Estilos

### CSS Tradicional
No CSS tradicional, todos os estilos compartilham o mesmo escopo global, o que pode causar conflitos de nomes, duplicação de código e dificuldade de manutenção em projetos grandes.

### SCSS (Abordagem Moderna)
O SCSS permite organizar os estilos por responsabilidade, separando regras em arquivos menores e reutilizáveis.
* **Recursos principais:** variáveis, mixins, aninhamento, imports e modularização.

### Arquivos Parciais
Arquivos iniciados com `_` (ex: `_variables.scss`) são considerados **parciais** e não geram arquivos CSS isoladamente, sendo usados apenas para organização e importação.

---

## 🎨 Variáveis

Variáveis permitem armazenar valores reutilizáveis, como cores, fontes e tamanhos.

```scss
$bg-primary: #ff6b6b;
$bg-secondary: #4ecdc4;
$bg-white: #ffffff;
$bg-dark: #2e2e2e;
$text-light: #ffffff;
$text-primary: #2e2e2e;`

Use code with caution.

**Vantagens:** Evitam repetição, facilitam a manutenção e permitem a troca de temas com facilidade.

---

**🧩 Aninhamento (Nesting)**

O SCSS permite aninhar seletores de acordo com a estrutura do HTML, tornando o código muito mais legível.

**scss**

`.card {
  background-color: $bg-primary;

  button {
    background-color: $bg-white;
    color: $text-primary;

    &:hover {
      background-color: $bg-secondary;
    }
  }
}`

Use code with caution.

> ⚠️ Aviso: Evite aninhamento excessivo (mais de 3 níveis) para não gerar seletores CSS excessivamente específicos.
> 

---

**🧱 Mixins**

Mixins funcionam como funções de estilo, permitindo a reutilização de blocos inteiros de código com suporte a parâmetros.

**scss**

`@mixin flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}

@mixin flex-custom($justify: center) {
  display: flex;
  justify-content: $justify;
  align-items: center;
}

// Uso:
header {
  @include flex-custom(space-between);
}`

Use code with caution.

---

**🔁 Reutilização com Extend**

Permite que um seletor herde as propriedades de outro, útil para estilos base de componentes.

**scss**

`%card-base {
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
}

.card-produto {
  @extend %card-base;
  background-color: $bg-white;
}`

Use code with caution.

---

**⚙️ Compilação e Automação**

O SCSS deve ser convertido para CSS. O modo Watch é a forma mais eficiente de trabalhar.

**Compilação Simples:**

**bash**

`sass main.scss main.css`

Use code with caution.

**Compilação de Diretórios:**

**bash**

`sass scss:css`

Use code with caution.

**Watch Mode (Automático):**

**bash**

`sass --watch scss:css`

Use code with caution.

> "Automatizar o processo é essencial para manter o foco no desenvolvimento e não na repetição."
> 

---

**🧠 Resumo de Conceitos**

1. **Variáveis:** Centralizam valores reutilizáveis do projeto.
2. **Aninhamento:** Representa fielmente a hierarquia do HTML.
3. **Mixins:** Funções reutilizáveis para blocos de estilo.
4. **Extend:** Compartilhamento de estilos base entre seletores.
5. **Organização:** Separação de arquivos por responsabilidade.
6. **Compilação:** Conversão necessária de SCSS para CSS.
7. **Watch Mode:** Compilação automática contínua ao salvar arquivos.
