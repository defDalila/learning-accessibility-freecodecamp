# <p align="center"><font color='#FF79C6'><strong>Learn Accessibility By Building a Quiz</strong></font></p>

<p align="center"> <i>Módulo de treinamento para a certificação <a href="https://www.freecodecamp.org/learn/2022/responsive-web-design/"><em>Responsive Web Design Certification</em></a> da plataforma FreeCodeCamp</i>.
<p>

<p align="center">
    <img src="https://skillicons.dev/icons?i=html,css,md,vscode,git,github,figma" height="30px">
</p>


<br>

## :memo: <font color='#8BE9FD'><strong>Notas de Aula</strong></font>

<br>

## Description

Um elemento meta importante para acessibilidade e SEO é a definição da descrição. O valor do atributo `content` é utilizado pelos mecanismos de busca para fornecer uma descrição da sua página. 

### **Exemplo de uso:**
```html
<meta name="description" content="Uma galeria de fotos com flexbox, criada para demonstrar técnicas modernas de CSS.">
```
Esse conteúdo pode aparecer nos resultados de pesquisa como um resumo da página, ajudando os usuários a entenderem do que se trata antes de acessá-la.


## Nav

A navegação é uma parte essencial da acessibilidade, e leitores de tela dependem de você para fornecer a estrutura da sua página. Isso é feito com **elementos semânticos** em HTML.  

### **Por que usar HTML semântico?**
- **Melhora a acessibilidade** → Leitores de tela entendem melhor o conteúdo.  
- **Melhora o SEO** → Motores de busca reconhecem a estrutura da página.  
- **Facilita a manutenção** → Código mais organizado e legível.  

### **Exemplos de elementos semânticos úteis para navegação**
```html
<header>
  <nav>
    <ul>
      <li><a href="#home">Início</a></li>
      <li><a href="#about">Sobre</a></li>
      <li><a href="#contact">Contato</a></li>
    </ul>
  </nav>
</header>
```
- `<nav>` → Define a área de navegação da página.  
- `<ul>` → Lista de links de navegação.  
- `<a>` → Links para diferentes seções.  

Usar elementos semânticos garante que sua página seja mais acessível e fácil de entender tanto para usuários quanto para mecanismos de busca. 🚀

## img

A imagem está assumindo seu tamanho padrão, que é muito grande. O CSS possui a função `max()`, que retorna o maior valor entre um conjunto de valores separados por vírgula.  

### **Exemplo de uso:**
```css
img {
  width: max(200px, 50%);
}
```
Nesse caso:  
- A largura da imagem será **o maior valor** entre `200px` e `50%` do contêiner pai.  
- Se `50%` do contêiner for menor que `200px`, a imagem terá `200px`.  
- Se `50%` do contêiner for maior que `200px`, a imagem terá `50%`.  

Isso ajuda a tornar o layout **mais flexível e responsivo**. 🚀


## Seletor `>`

O seletor de combinador de filho `>` é usado entre seletores para **selecionar apenas elementos que são filhos diretos** do primeiro seletor.  

### **Exemplo de uso:**
```css
div > p {
  color: blue;
}
```
**Explicação:**  
- Isso estiliza **apenas** `<p>` que são **filhos diretos** de `<div>`.  
- Não afeta `<p>` que estão **mais profundamente aninhados** dentro de outras tags.  

### **Exemplo prático em HTML:**
```html
<div>
  <p>Este parágrafo será azul.</p>
  <section>
    <p>Este parágrafo NÃO será azul porque não é filho direto da div.</p>
  </section>
</div>
```

O uso do `>` ajuda a **limitar o escopo** do estilo, evitando que ele afete elementos desnecessários. 🚀

## `Role`

O atributo `role` é utilizado para **indicar a função de um elemento na página** para tecnologias assistivas, melhorando a acessibilidade. Ele faz parte da **Web Accessibility Initiative (WAI)** e aceita valores predefinidos.  

### **Exemplo de uso do `role`:**
```html
<nav role="navigation">
  <ul>
    <li><a href="#">Início</a></li>
    <li><a href="#">Sobre</a></li>
    <li><a href="#">Contato</a></li>
  </ul>
</nav>
```
**Explicação:**  
- O `role="navigation"` informa aos leitores de tela que este `<nav>` **contém links de navegação**.  
- Isso ajuda usuários com deficiência visual a entenderem melhor a estrutura da página.  

### **Outros exemplos de `role` úteis:**
| **Valor**       | **Uso** |
|----------------|---------|
| `role="banner"` | Indica a **área principal** do cabeçalho. |
| `role="main"` | Define o **conteúdo principal** da página. |
| `role="complementary"` | Define **conteúdo complementar**, como uma barra lateral. |
| `role="button"` | Indica que o elemento age como um botão. |
| `role="alert"` | Define uma **mensagem importante**, como uma notificação. |

Adicionar o atributo `role` melhora **navegação, compreensão e usabilidade**, tornando a web mais inclusiva. 🌎✨

Para garantir que cada **região com um `role`** seja acessível, é necessário fornecer um **rótulo descritivo**. Isso ajuda usuários de leitores de tela a entenderem melhor a função da seção.  

### **Método: Usando `aria-labelledby`**
A maneira mais recomendada é adicionar um **elemento `<h1>` a `<h6>` dentro da região** e referenciá-lo com `aria-labelledby`.  

#### **Exemplo:**
```html
<aside role="complementary" aria-labelledby="news-heading">
  <h2 id="news-heading">Últimas Notícias</h2>
  <p>Confira as principais manchetes do dia.</p>
</aside>
```
🔹 O **`aria-labelledby="news-heading"`** referencia o `<h2 id="news-heading">`.  
🔹 O leitor de tela **lê o título** antes do conteúdo, deixando claro que se trata de uma seção de notícias.

---

### **Alternativa: Usando `aria-label`**
Se não houver um título visível, você pode usar **`aria-label`** para fornecer um nome diretamente:  

#### **Exemplo:**
```html
<nav role="navigation" aria-label="Menu principal">
  <ul>
    <li><a href="#">Início</a></li>
    <li><a href="#">Sobre</a></li>
    <li><a href="#">Contato</a></li>
  </ul>
</nav>
```
🔹 Aqui, o **leitor de tela informa que este `<nav>` é um "Menu principal"**, melhorando a navegação.

---

### **Resumo:**
| Método | Como funciona | Quando usar |
|--------|--------------|-------------|
| `aria-labelledby` | Faz referência a um ID de um elemento visível (ex: título `<h2>`) | Quando já há um cabeçalho na região |
| `aria-label` | Define um rótulo diretamente no atributo | Quando não há um cabeçalho visível |

Utilizar `aria-labelledby` ou `aria-label` melhora **usabilidade e acessibilidade**, garantindo que **todos os usuários compreendam a estrutura da página**! 🌍✨


## Input

Para garantir que **usuários de tecnologia assistiva** tenham uma **melhor experiência**, cada **input deve estar vinculado ao seu rótulo (`label`)**.  

### **Como Vincular um `<label>` a um `<input>`**
Isso é feito usando o **atributo `for` no `<label>`**, cujo valor deve ser **igual ao `id` do `<input>` correspondente**.  

#### **Exemplo:**
```html
<label for="name">Nome:</label>
<input type="text" id="name" name="name">
```
🔹 **O que acontece?**  
- Quando um usuário clica no **texto "Nome:"**, o cursor automaticamente foca no campo de entrada **`<input>`** correspondente.  
- Isso **melhora a acessibilidade** e facilita o preenchimento do formulário.  

---

### **Por que isso é importante?**
✅ **Melhora a usabilidade**: Usuários podem clicar no texto para ativar o campo.  
✅ **Facilita a navegação para leitores de tela**: Eles anunciam corretamente o rótulo do campo.  
✅ **Torna o formulário mais acessível**: Pessoas com dificuldades motoras podem interagir melhor.  

Caso o `<input>` esteja **dentro do `<label>`**, a conexão é automática, sem precisar do `for`:

```html
<label>
  Nome:
  <input type="text" name="name">
</label>
```
🔹 **Boa prática, mas menos comum**.  

Sempre vincule `<label>` e `<input>` corretamente para garantir **melhor acessibilidade e experiência do usuário!** 🎯✨

### **Melhores Práticas para Inputs em Formulários** ✅  

Ao definir **campos de entrada (`<input>`)**, siga estas diretrizes para garantir **boa usabilidade e acessibilidade**:  

1. **Use o atributo `type` correto** para cada campo.  
2. **Adicione um `name` significativo** para identificar os dados na submissão.  
3. **Inclua `placeholder` apenas se necessário**, sem substituir `label`.  

---

### **Exemplo de Formulário Melhorado** 🎯  

```html
<form action="/submit" method="POST">
  
  <!-- Nome: Texto simples -->
  <label for="name">Nome:</label>
  <input type="text" id="name" name="name" placeholder="Digite seu nome" required>
  
  <!-- E-mail: Tipo específico para validação -->
  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required>
  
  <!-- Senha: Oculta os caracteres -->
  <label for="password">Senha:</label>
  <input type="password" id="password" name="password" minlength="8" required>
  
  <!-- Data de Nascimento: Aceita apenas datas -->
  <label for="dob">Data de Nascimento:</label>
  <input type="date" id="dob" name="dob">
  
  <!-- Telefone: Para entrada numérica e formatação -->
  <label for="phone">Telefone:</label>
  <input type="tel" id="phone" name="phone" pattern="[0-9]{10,11}" placeholder="Apenas números">
  
  <!-- Aceitação de Termos: Checkbox obrigatório -->
  <label for="terms">
    <input type="checkbox" id="terms" name="terms" required>
    Eu aceito os termos e condições
  </label>
  
  <!-- Botão de Envio -->
  <input type="submit" value="Enviar">
  
</form>
```

---

### **🔹 O que foi aplicado?**  
✅ **Cada `<input>` tem um `type` apropriado** (ex: `email`, `password`, `date`).  
✅ **O `name` ajuda a identificar os dados submetidos.**  
✅ **O primeiro input (`name`) inclui um `placeholder` para orientar o usuário.**  
✅ **Requisitos de acessibilidade** (`required`, `minlength`, `pattern`).  

Isso melhora a **usabilidade**, **validação** e a **experiência do usuário**! 🚀


## Placeholder

Embora o **atributo `placeholder`** seja frequentemente usado para dar dicas ao usuário, ele não é considerado a melhor prática para **acessibilidade**. Isso ocorre porque o texto do **placeholder** pode ser confundido com o valor real do campo de entrada, especialmente quando o usuário começa a digitar, fazendo com que o texto desapareça.

### **Alternativa: Usar o `label` corretamente**  
A melhor prática é sempre **usar um `<label>` para descrever o campo**, o que oferece várias vantagens:

1. **Visibilidade**: O rótulo permanece visível ao lado ou acima do campo, proporcionando um contexto claro para o usuário, mesmo depois de começar a digitar.
2. **Acessibilidade**: Associar um `<label>` a um campo de entrada ajuda **leitores de tela** a entenderem melhor o propósito do campo.

### **Melhoria no Código** 🛠️

Aqui está a melhoria do exemplo anterior, **removendo o `placeholder`** e confiando completamente nos **`label`**:

```html
<form action="/submit" method="POST">
  
  <!-- Nome: Texto simples -->
  <label for="name">Nome:</label>
  <input type="text" id="name" name="name" required>
  
  <!-- E-mail: Tipo específico para validação -->
  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required>
  
  <!-- Senha: Oculta os caracteres -->
  <label for="password">Senha:</label>
  <input type="password" id="password" name="password" minlength="8" required>
  
  <!-- Data de Nascimento: Aceita apenas datas -->
  <label for="dob">Data de Nascimento:</label>
  <input type="date" id="dob" name="dob">
  
  <!-- Telefone: Para entrada numérica e formatação -->
  <label for="phone">Telefone:</label>
  <input type="tel" id="phone" name="phone" pattern="[0-9]{10,11}" required>
  
  <!-- Aceitação de Termos: Checkbox obrigatório -->
  <label for="terms">
    <input type="checkbox" id="terms" name="terms" required>
    Eu aceito os termos e condições
  </label>
  
  <!-- Botão de Envio -->
  <input type="submit" value="Enviar">
  
</form>
```

### **Benefícios dessa abordagem:**

- **Maior Clareza**: Os campos de entrada possuem rótulos visíveis e claros.
- **Acessibilidade**: Leitores de tela e outras tecnologias assistivas podem identificar e informar o conteúdo do campo corretamente.
- **Facilidade de uso**: O usuário sabe exatamente o que precisa ser preenchido, sem confusão com o texto de sugestão.

**Dica**: O uso de `placeholder` pode ser útil para fornecer dicas extras (como um formato específico ou exemplo de entrada), mas nunca deve substituir o `label`.

Para tornar o formulário mais acessível a **usuários com deficiência visual**, podemos adicionar texto descritivo visível apenas para **leitores de tela**. Uma maneira de fazer isso é usando o **atributo `aria-label`** ou o **atributo `aria-labelledby`** para associar descrições mais claras aos elementos, sem a necessidade de exibir esse texto na tela.

### **Exemplo de Código:**

Vamos melhorar o formulário, adicionando descrições mais detalhadas que serão lidas apenas por leitores de tela:

```html
<form action="/submit" method="POST">
  
  <!-- Nome -->
  <label for="name">Nome:</label>
  <input type="text" id="name" name="name" required aria-label="Digite seu nome completo">
  
  <!-- E-mail -->
  <label for="email">E-mail:</label>
  <input type="email" id="email" name="email" required aria-label="Digite seu endereço de e-mail">
  
  <!-- Senha -->
  <label for="password">Senha:</label>
  <input type="password" id="password" name="password" minlength="8" required aria-label="Escolha uma senha com no mínimo 8 caracteres">
  
  <!-- Data de Nascimento -->
  <label for="dob">Data de Nascimento:</label>
  <input type="date" id="dob" name="dob" aria-label="Selecione sua data de nascimento">
  
  <!-- Telefone -->
  <label for="phone">Telefone:</label>
  <input type="tel" id="phone" name="phone" pattern="[0-9]{10,11}" required aria-label="Digite seu número de telefone com 10 ou 11 dígitos">
  
  <!-- Aceitação de Termos -->
  <label for="terms">
    <input type="checkbox" id="terms" name="terms" required aria-label="Marque para aceitar os termos e condições">
    Eu aceito os termos e condições
  </label>
  
  <!-- Botão de Envio -->
  <input type="submit" value="Enviar" aria-label="Clique para enviar o formulário">
  
</form>
```

### **Explicação:**

1. **`aria-label`**: O atributo `aria-label` descreve o propósito de cada campo de entrada de uma maneira mais acessível. Por exemplo, o campo de **nome** agora tem `aria-label="Digite seu nome completo"`, que será lido por leitores de tela, ajudando o usuário a entender o que precisa ser preenchido.
   
2. **Evitar Dependência de Apenas Números**: Em vez de usar números (como "Pergunta 1", "Pergunta 2"), usamos descrições mais detalhadas, como "Digite seu nome completo", que são mais compreensíveis para leitores de tela e também para outros usuários.

### **Por que usar `aria-label`?**

- **Sem texto visível**: O **`aria-label`** não afeta a aparência do seu formulário, então ele pode ser usado para adicionar informações acessíveis sem interferir no design.
- **Acessibilidade**: Essencial para garantir que os usuários com deficiência visual possam interagir corretamente com o conteúdo, uma vez que os leitores de tela interpretam essas descrições.

Com essa prática, o formulário fica mais **intuitivo e acessível** para todos os usuários, incluindo aqueles que dependem de tecnologias assistivas!

## Somente Leitura

Um padrão comum para ocultar texto visualmente, mas mantê-lo acessível apenas para leitores de tela, é usar técnicas CSS. Isso permite fornecer contexto ou descrições para usuários de leitores de tela sem exibir o texto na página.

Aqui está um método amplamente utilizado:

### **CSS para Ocultar Texto Visualmente, Mas Manter Acessível para Leitores de Tela**

```css
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  border: 0;
  clip: rect(0, 0, 0, 0);
  overflow: hidden;
}
```

### **Explicação:**

- **`position: absolute;`**: Remove o elemento do fluxo normal do documento, para que ele não afete o layout da página.
- **`width: 1px; height: 1px;`**: Reduz o elemento a um tamanho minúsculo, essencialmente tornando-o invisível.
- **`margin: -1px; padding: 0; border: 0;`**: Garante que não haja espaço ou borda ao redor do elemento oculto.
- **`clip: rect(0, 0, 0, 0);`**: Recorta o elemento para uma área 0x0, tornando-o invisível.
- **`overflow: hidden;`**: Impede que o texto seja rolável ou visível.

### **Exemplo de HTML Usando a Classe CSS**

```html
<label for="email" class="visually-hidden">Por favor, insira seu endereço de e-mail</label>
<input type="email" id="email" name="email">
```

### **Uso:**

Você pode usar a classe **`visually-hidden`** para ocultar texto descritivo que é útil para leitores de tela, mas não necessário para usuários com visão. Por exemplo, você pode ocultar instruções, esclarecimentos ou detalhes adicionais sobre campos de formulário, tornando o formulário mais acessível sem sobrecarregar o layout visual.

### **Por que Usar Esse Padrão?**

- **Melhora a Acessibilidade**: Ele fornece mais contexto e orientação para usuários que dependem de leitores de tela, ajudando-os a entender melhor os elementos da página e seus propósitos.
- **Mantém o Design Limpo**: O texto fica oculto visualmente, para que não interfira no design ou layout da página, mas ainda oferece informações valiosas para tecnologias assistivas.

Este padrão é especialmente útil para **rótulos de formulários**, **links de navegação** e outros **elementos interativos**, onde informações adicionais são necessárias para acessibilidade, sem sobrecarregar a interface do usuário.

##  Before

Para evitar repetição desnecessária e melhorar a acessibilidade, você pode usar o pseudo-elemento `::before`. Ele permite inserir conteúdo antes de um elemento, sem a necessidade de adicionar elementos extras no HTML. Isso pode ser útil para fornecer informações adicionais ou criar um contexto mais claro, sem sobrecarregar a estrutura visual.

Aqui está um exemplo de como usar o pseudo-elemento `::before` para adicionar texto antes de um elemento, sem repetir o mesmo conteúdo:

### **Exemplo de CSS com o Pseudo-elemento `::before`:**

```css
input[type="email"]::before {
  content: "Email: ";
  display: block;
  font-weight: bold;
  margin-bottom: 5px;
  color: #333;
}
```

### **Explicação:**

- **`content: "Email: ";`**: O conteúdo que será inserido antes do elemento (neste caso, "Email: " será exibido antes do campo de entrada).
- **`display: block;`**: Faz com que o conteúdo inserido seja exibido em bloco, ocupando uma linha inteira, separando-o do elemento subsequente.
- **`font-weight: bold;`**: Torna o texto em negrito para destacá-lo.
- **`margin-bottom: 5px;`**: Adiciona um espaço abaixo do texto inserido para separar visualmente do próximo conteúdo.
- **`color: #333;`**: Define a cor do texto como um tom escuro.

### **Aplicando em um Formulário:**

```html
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>
```

### **Resultado:**
Ao aplicar o CSS, o texto **"Email:"** aparecerá antes do campo de entrada **`<input>`**, mas o conteúdo do HTML não precisa ser modificado diretamente. Isso melhora a semântica e acessibilidade, sem adicionar tags extras, e pode ser útil para incluir instruções adicionais, rótulos ou até mesmo mensagens de erro ou aviso.

### **Benefícios:**

1. **Melhora a Acessibilidade**: A adição de conteúdo de forma programática através de CSS não sobrecarrega o HTML, mas mantém a clareza para tecnologias assistivas.
2. **Evita Repetição**: Pode-se evitar a duplicação de texto ou elementos no HTML, economizando espaço e mantendo a estrutura limpa.
3. **Flexibilidade no Design**: É possível controlar melhor a aparência e o comportamento do conteúdo sem precisar mexer na estrutura HTML diretamente.

Essa técnica é útil quando você precisa adicionar algo visualmente ou semanticamente relevante sem modificar a estrutura do HTML.

## Contraste

A acessibilidade visual é um aspecto fundamental para garantir que todos os usuários, incluindo aqueles com deficiências visuais, possam navegar e interagir com o conteúdo de um site de forma eficiente. A **contraste** entre os elementos (como o texto e o fundo) é um dos principais fatores para melhorar a legibilidade.

### **Proporção de Contraste:**
Para garantir a legibilidade, a **proporção de contraste** entre o texto e o fundo deve ser de pelo menos **4.5:1** para texto normal, e **3:1** para texto grande ou negrito, conforme as diretrizes WCAG (Web Content Accessibility Guidelines).

### **Como Calcular o Contraste:**
A **proporção de contraste** é calculada com base na luminância relativa das cores usadas no texto e no fundo. Existem várias ferramentas online que podem calcular a proporção de contraste entre duas cores, como o [WebAIM Color Contrast Checker](https://webaim.org/resources/contrastchecker/).

### **Exemplo de CSS para Garantir Boa Legibilidade:**

Aqui está um exemplo de CSS com boas práticas para garantir contraste adequado entre o texto e o fundo de um título:

```css
/* Título com alto contraste */
h1 {
  color: #1a1a1a; /* Texto em um tom de cinza escuro */
  background-color: #ffffff; /* Fundo branco */
  font-size: 2rem;
  padding: 10px;
}
```

### **Verificando o Contraste:**
1. **Texto**: `#1a1a1a` (um cinza bem escuro)
2. **Fundo**: `#ffffff` (branco)

A proporção de contraste entre essas duas cores é de **21:1**, o que é muito bom e atende aos requisitos das diretrizes de acessibilidade.

### **Dicas para Garantir Bom Contraste:**

1. **Evite Usar Cores Muito Semelhantes**: Certifique-se de que o texto não tenha a mesma cor ou um tom muito próximo ao fundo. Evite combinações como texto em **cinza claro** em fundo **branco**.
   
2. **Use Cores Combináveis**: Cores como **preto** ou **cinza escuro** em fundo **branco** ou **amarelo forte** em fundo **preto** oferecem um ótimo contraste.

3. **Utilize Ferramentas de Acessibilidade**: Além de verificar manualmente o contraste, utilize ferramentas como o **Color Contrast Analyzer** ou o **Contrast Checker** para garantir que as cores atendem às recomendações.

### **Exemplo de Cores de Alto Contraste:**

```css
/* Contraste forte entre o texto e o fundo */
h2 {
  color: #000000; /* Preto */
  background-color: #ffcc00; /* Amarelo brilhante */
  font-size: 1.5rem;
  padding: 15px;
}
```

Este exemplo oferece um **contraste de 21:1**, que é facilmente legível e acessível para pessoas com baixa visão ou daltonismo.

### **Considerações Finais:**

- **Contraste Adequado**: Um bom contraste entre o texto e o fundo é essencial para usuários com visão reduzida ou deficiências visuais.
- **Experiência do Usuário**: Garantir que o conteúdo seja visível e compreensível para todos os usuários melhora a experiência geral e a usabilidade do seu site.
- **WCAG**: Siga as diretrizes WCAG para garantir que seu site esteja em conformidade com os padrões de acessibilidade.

Ajustar o contraste é uma das práticas mais simples e eficazes para melhorar a acessibilidade do seu site.

O **índice de contraste** (ou **contrast ratio**) é a medida que indica a diferença de luminosidade entre o texto e o fundo. Esse índice é fundamental para garantir a legibilidade do conteúdo, especialmente para pessoas com deficiência visual, como aquelas com baixa visão ou daltonismo.

### **Como o Contrast Ratio Funciona:**
O índice de contraste é calculado usando a **luminância relativa** das cores de primeiro plano (texto) e de fundo. A **luminância relativa** é um valor que representa a quantidade de luz que uma cor reflete para os olhos humanos.

A fórmula para calcular o índice de contraste é:


$$\text{Contraste} = \frac{(L1 + 0.05)}{(L2 + 0.05)}$$


Onde:
- **L1** é a luminância da cor mais clara (geralmente o fundo).
- **L2** é a luminância da cor mais escura (geralmente o texto).

O valor do índice varia entre **1:1** (sem contraste) e **21:1** (máximo contraste). Quanto maior o número, melhor é a legibilidade.

### **Diretrizes WCAG:**
A **Web Content Accessibility Guidelines** (WCAG) especifica os seguintes requisitos mínimos de contraste para tornar o conteúdo legível e acessível:

1. **Texto normal**: A proporção de contraste entre o texto e o fundo deve ser **pelo menos 4.5:1**.
2. **Texto grande (14pt negrito ou 18,66pt normal)**: A proporção de contraste deve ser **pelo menos 3:1**.
3. **Texto e elementos gráficos**: O contraste deve ser de **pelo menos 3:1**.

### **Exemplo de Cálculo de Contraste:**
Suponha que você tenha as cores:
- **Texto**: Preto (hex: #000000)
- **Fundo**: Branco (hex: #FFFFFF)

Neste caso, o índice de contraste entre essas cores seria **21:1**, o que é considerado ideal.

### **Ferramentas para Calcular o Contraste:**
Existem diversas ferramentas online que podem calcular facilmente o índice de contraste entre duas cores. Algumas opções populares incluem:

- **[WebAIM Color Contrast Checker](https://webaim.org/resources/contrastchecker/)**: Uma ferramenta simples para verificar o contraste entre duas cores e verificar se elas atendem aos requisitos WCAG.
- **[Contrast Ratio](https://contrast-ratio.com/)**: Outra ferramenta que permite comparar duas cores e calcular o índice de contraste entre elas.

### **Importância do Contraste:**
- **Acessibilidade**: Garantir bom contraste entre o texto e o fundo é crucial para tornar o conteúdo acessível a pessoas com deficiências visuais, como baixa visão, daltonismo e outros tipos de deficiência.
- **Melhora na Leitura**: O contraste adequado torna o texto mais legível, o que melhora a experiência do usuário e torna o conteúdo mais fácil de ler, especialmente em dispositivos móveis ou ambientes com pouca iluminação.

### **Exemplo de Implementação CSS:**
Aqui está um exemplo de como você pode garantir um bom contraste usando CSS:

```css
/* Texto escuro sobre fundo claro */
h1 {
  color: #000000; /* Preto */
  background-color: #ffffff; /* Branco */
  font-size: 2rem;
}

/* Texto claro sobre fundo escuro */
h2 {
  color: #ffffff; /* Branco */
  background-color: #333333; /* Cinza escuro */
  font-size: 1.5rem;
}
```

Neste caso, o **h1** tem um contraste máximo de **21:1**, e o **h2** possui um bom contraste de **15:1**, ambos atendendo aos requisitos WCAG. 

### **Considerações Finais:**
- O **índice de contraste** é essencial para garantir a legibilidade e acessibilidade do conteúdo.
- Ferramentas de contraste ajudam a verificar se o seu design está acessível, de acordo com as diretrizes WCAG.
- Um bom contraste é necessário para garantir que pessoas com deficiências visuais possam acessar e entender o conteúdo da sua página com facilidade.

## Links em Listas

Para garantir que os links dentro dos elementos de lista tenham uma **taxa de contraste de pelo menos 7:1**, escolha uma cor para o texto que forneça alta visibilidade em relação ao fundo. Aqui estão algumas opções seguras:

- **Fundo Branco (#FFFFFF)** → Texto Preto (#000000) → **21:1** (Ótimo contraste)  
- **Fundo Cinza Claro (#F5F5F5)** → Texto Azul Escuro (#00274D) → **7.5:1** (Bom contraste)  
- **Fundo Preto (#000000)** → Texto Branco (#FFFFFF) → **21:1** (Ótimo contraste)  

### **Exemplo de Implementação CSS**
Aqui está um código CSS para garantir um contraste mínimo de **7:1** nos links dentro de listas (`li`):

```css
li a {
  color: #00274D; /* Azul escuro para alto contraste */
  text-decoration: none; /* Remove o sublinhado para um design mais limpo */
}

li a:hover {
  color: #000000; /* Preto para ainda mais contraste ao passar o mouse */
  text-decoration: underline; /* Adiciona sublinhado ao passar o mouse */
}
```

Se o fundo for escuro, inverta a lógica para usar **texto branco (#FFFFFF)** para obter o contraste necessário.

Caso tenha dúvidas sobre o contraste das cores escolhidas, você pode testar em ferramentas como:
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [Contrast Ratio](https://contrast-ratio.com/)

Isso melhora a **acessibilidade** e a **legibilidade** da sua página, tornando-a mais inclusiva para usuários com baixa visão. 🚀

## Estilizar os botões de navegação

Aqui está o CSS para estilizar os botões de navegação, removendo o sublinhado dos links e adicionando um efeito de hover para trocar as cores do fundo e do texto:  

```css
/* Remove o sublinhado dos links de navegação */
nav a {
  text-decoration: none;
  padding: 10px 15px;
  border-radius: 5px;
  background-color: #00274D; /* Azul escuro */
  color: #FFFFFF; /* Texto branco */
  transition: background-color 0.3s ease, color 0.3s ease;
}

/* Efeito de hover nos itens da lista de navegação */
nav li:hover {
  background-color: #FFFFFF; /* Fundo branco */
  color: #00274D; /* Texto azul escuro */
  cursor: pointer;
}

/* Garante que o link dentro do <li> também mude de cor no hover */
nav li:hover a {
  color: #00274D;
}
```

### **Explicação do Código**:
1. **Removemos o sublinhado (`text-decoration: none;`)** dos links (`a`) dentro da navegação.
2. **Estilizamos os links como botões**, adicionando um **padding**, **borda arredondada** e um **fundo azul escuro com texto branco**.
3. **Criamos um efeito de hover** para os itens da lista (`li`), onde as cores do fundo e do texto **são invertidas** ao passar o mouse.
4. **Mudamos o cursor para `pointer`** para indicar que o item é clicável.
5. **Garantimos que o texto dentro do link (`a`) também troque de cor no hover** para manter a harmonia do design.

Isso deixará a navegação mais intuitiva e visualmente agradável. 🚀

## navigation bar overflow

Para corrigir o problema de transbordamento da lista de navegação em telas pequenas, siga estes passos:  

### **Correção com Flexbox**:
```css
/* Garante que a barra de navegação use Flexbox */
nav {
  display: flex;
  justify-content: center; /* Centraliza os itens */
  align-items: center; /* Alinha verticalmente */
}

/* Permite que os itens da lista quebrem linha se necessário */
nav ul {
  display: flex;
  flex-wrap: wrap; /* Permite que os itens se ajustem em telas pequenas */
  justify-content: center; /* Centraliza os itens */
  padding: 0;
  margin: 0;
  list-style: none;
}

/* Ajusta o espaçamento dos itens da lista */
nav li {
  margin: 5px 10px;
}
```

### **Explicação do Código**:
1. **`display: flex;` na `<nav>`** → Transforma a navegação em um flex container.
2. **`justify-content: center;` na `<nav>`** → Centraliza os itens horizontalmente.
3. **`align-items: center;` na `<nav>`** → Alinha verticalmente os itens.
4. **`display: flex;` na `<ul>`** → Torna a lista um flex container.
5. **`flex-wrap: wrap;` na `<ul>`** → Permite que os itens quebrem linha em telas menores.
6. **`justify-content: center;` na `<ul>`** → Centraliza os itens da lista.
7. **Remove `padding`, `margin` e `list-style` da `<ul>`** para evitar espaçamentos desnecessários.
8. **`margin: 5px 10px;` nos `<li>`** → Adiciona um espaçamento uniforme entre os itens.

Isso garante que a navegação se ajuste corretamente em dispositivos pequenos, sem transbordar a tela. 🚀


## Radio

Se você quiser remover os marcadores (bullets) da lista onde os botões de rádio estão, pode usar a propriedade `list-style: none;`.  

### **Correção no CSS**:
```css
ul {
  list-style: none; /* Remove os marcadores */
  padding: 0; /* Remove o recuo padrão */
  margin: 0; /* Ajusta o espaçamento */
}
```

### **Explicação**:
1. **`list-style: none;`** → Remove os marcadores (bullets).
2. **`padding: 0;`** → Elimina o espaço à esquerda que a lista normalmente tem.
3. **`margin: 0;`** → Garante um alinhamento correto da lista.

Se precisar de mais ajustes, me avise! 😊

## Scroll

Para tornar a navegação mais suave e menos abrupta, você pode adicionar um **scroll suave** usando CSS.  

### **Solução com CSS**:
```css
html {
  scroll-behavior: smooth;
}
```

### **Explicação**:
- A propriedade **`scroll-behavior: smooth;`** faz com que a rolagem ao clicar nos links de navegação seja animada, evitando saltos bruscos na tela.

Isso melhora a experiência do usuário, especialmente para pessoas que podem achar mudanças repentinas desorientadoras.  

Se precisar de mais personalizações, me avise! 😊

## Media

Para respeitar as preferências do usuário quanto a animações e evitar desconforto para pessoas com distúrbios vestibulares, você pode usar a regra `@media (prefers-reduced-motion: reduce)`.  

### **Exemplo de Código CSS**:
```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none !important;
    transition: none !important;
    scroll-behavior: auto !important;
  }
}
```

### **Explicação**:
- `animation: none;` → Desativa animações.
- `transition: none;` → Remove transições suaves.
- `scroll-behavior: auto;` → Desativa o **scroll suave** para usuários que preferem menos movimento.

Isso melhora a acessibilidade e respeita as configurações de quem pode ter sensibilidade a animações. 🚀