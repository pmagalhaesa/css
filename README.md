# SMACSS - Arquitetura escalável e modular para CSS

## Categorizando regras CSS
- Existem cinco tipos de categorias:
  - Base
  - Layout
  - Módulo
  - Estado
  - Tema
- Um **estilo base** diz que onde quer que este elemento está na página, ele deve ser parecido esta:
```css
html, body, form { margin: 0; padding: 0; }
input[type=text] { border: 1px solid #999; }
a { color: #039; }
a:hover { color: #03C; }
```
- As **regras de layout** dividem a página em seções. Layouts mantêm um ou mais módulos juntos.
- Os **módulos** são as peças reutilizáveis e modulares do nosso projeto.
- As **regras do estado** são maneiras de descrever como nossos módulos ou layouts serão vistos quando em um determinado estado. É escondido ou expandido? É ativo ou inativo? Eles são sobre descrever como um módulo ou layout parece em telas menores ou maiores. Eles também descrevem como um módulo pode parecer em diferentes visualizações, como a página inicial ou a página interna.
- As **regras do tema** são semelhantes às regras do estado, na medida em que descrevem como os módulos ou layouts podem parecer. A maioria dos sites não requer uma camada de temas, mas é bom estar ciente disso.
### Regras de Nomeação
- A convenção de nomenclatura é benéfica para entender imediatamente a qual categoria pertence um estilo específico e seu papel dentro do escopo geral da página.
- Em grandes projetos, é mais provável ter estilos divididos em vários arquivos. Nesses casos facilita a descoberta de qual arquivo pertence um estilo.
- Usar um prefixo para diferenciar as regras Layout, State e Module. Para Layout **l-** mas **layout-** também funciona. O uso de prefixos **grid-** também fornece clareza suficiente para separar estilos de layout de outros estilos. Para as regras do estado, eu gosto **is-** como em is-hiddenou is-collapsed. Isso ajuda a descrever as coisas de uma forma muito legível.
- Os módulos serão a maior parte de qualquer projeto. Os módulos apenas usam o nome do próprio módulo, sem prefixos como:
```css
/* Example Module */
.example { }

/* Callout Module */
.callout { }

/* Callout Module with State */
.callout.is-collapsed { }

/* Form field module */
.field { }

/* Inline layout  */
.l-inline { }
```
- Elementos relacionados dentro de um módulo usam o nome da base como um prefixo.
- Os módulos que são uma variação em outro módulo também devem usar o nome do módulo base como um prefixo.

## Regras Básicas
- Uma regra base é aplicada aos elementos, não inclui qualquer classe ou seletor ID. Com isso é definindo o estilo padrão para como esse elemento deve procurar em todas as ocorrências na página.
- Os estilos básicos incluem a definição de tamanhos de título, estilos de link padrão, estilos de fonte padrão e fundos do corpo, como mostra abaixo:

```css
body, form {
    margin: 0;
    padding: 0;
}

a {
    color: #039;
}

a:hover {
    color: #03F;    
}
```
### CSS Resets
- Um Reset CSS é um conjunto de estilos de base destinadas a retirar ou colocar a margem predefinida, preenchimento, e outras propriedades. 
- O objetivo é definir uma base consistente em todos os navegadores para construir o site.
- Desenvolver o seu próprio conjunto de estilos padrão que você use consistentemente de projeto para projeto também pode ser vantajoso.
