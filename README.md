# Design System para ReactJS

Um **Design System** é um conjunto de componentes reutilizáveis, padrões visuais, boas práticas de código e diretrizes de experiência do usuário (UX) que garantem consistência, escalabilidade e eficiência no desenvolvimento de interfaces digitais.

Este guia é focado em como aplicar padrões de design e boas práticas no contexto de desenvolvimento com **ReactJS** seguindo o paradigma funcional.

---

## 📐 1. Princípios de Design System

- **Consistência visual**: uso padronizado de cores, tipografia, espaçamentos e estilos.
- **Reusabilidade**: componentes isolados e reutilizáveis para evitar duplicação de código.
- **Escalabilidade**: fácil manutenção e expansão do sistema ao longo do tempo.
- **Acessibilidade (a11y)**: interfaces inclusivas por padrão.

---

## ⚛️ 2. Arquitetura de Componentes em React

### 2.1 Atomic Design

Utilize a abordagem **Atomic Design** para estruturar seus componentes:

- **Átomos**: botões, inputs, ícones.
- **Moléculas**: conjunto de átomos (ex: campo de busca com ícone).
- **Organismos**: seções reutilizáveis (ex: navbar).
- **Templates**: layout de páginas com componentes organizados.
- **Páginas**: instâncias reais com dados.

### 2.2 Composição de Componentes

- Prefira **composição** em vez de herança.
- Use `children`, **slots**, ou `render props` para permitir flexibilidade.

---

## 🎨 3. Guia de Estilo

### 3.1 Tipografia

- Defina fontes principais, tamanhos, pesos e alturas de linha.
- Use tokens de estilo (ex: `text-sm`, `text-lg`) integrados ao seu sistema.

### 3.2 Cores

- Paleta base: primária, secundária, neutros e estados (erro, sucesso, alerta).
- Tokens de cor (ex: `--color-primary` ou `theme.primary`).
- Suporte a modo escuro (dark mode).

### 3.3 Espaçamentos

- Padronize margens e paddings com escala (ex: `4px`, `8px`, `16px`).
- Use classes utilitárias ou variáveis.

---

## 🧩 4. Padrões de Componentes

### 4.1 Componentes Controlados vs Não Controlados

- Prefira **componentes controlados** para inputs e formulários.
- Exemplo:
  ```tsx
  <Input value={value} onChange={setValue} />
  ```

### 4.2 Estado Local vs Estado Global

- Estado **local**: use `useState`, `useReducer` dentro do componente.
- Estado **global**: use contextos, Zustand, Redux, etc. com moderação.

### 4.3 Separação de Responsabilidades

- Separe lógica e visual:
  - `ComponentName.tsx` → apenas apresentação.
  - `useComponentName.ts` → lógica e efeitos colaterais.
  - `types.ts` → tipos e interfaces.

---

## 📦 5. Organização do Design System

### 5.1 Estrutura de Pastas

```bash
/design-system
  /components
    /Button
      index.tsx
      styles.ts
      types.ts
  /tokens
    colors.ts
    spacing.ts
    typography.ts
  /hooks
  /icons
```

### 5.2 Tokens de Design

- Centralize os estilos reutilizáveis em arquivos de **tokens**.
- Exemplo:
  ```ts
  export const spacing = {
    xs: '4px',
    sm: '8px',
    md: '16px',
    lg: '24px',
  }
  ```

---

## 🔧 6. Ferramentas e Boas Práticas

- **Storybook**: documente e visualize seus componentes isoladamente.
- **Figma**: alinhe o design visual com o time de design.
- **Stylelint / ESLint**: imponha consistência de código.
- **Tailwind CSS ou styled-components**: escolha conforme o contexto do time.

---

## 🧪 7. Testes de Componentes

- Use **React Testing Library** para testes focados no comportamento do usuário.
- Teste:
  - Renderização
  - Interações
  - Estados visuais
  - Acessibilidade (`axe-core`)

---

## 🌐 8. Acessibilidade

- Use `aria-*` e roles semânticos (`button`, `nav`, `main`, etc.).
- Certifique-se que seus componentes são navegáveis por teclado.
- Contraste de cores e foco visível são obrigatórios.

---

## 📚 9. Referências

- [Atomic Design](https://bradfrost.com/blog/post/atomic-web-design/)
- [Storybook](https://storybook.js.org/)
- [WAI-ARIA Guidelines](https://www.w3.org/WAI/standards-guidelines/aria/)
- [A Complete Guide to Building a Design System (Smashing Magazine)](https://www.smashingmagazine.com/2020/03/guide-building-design-systems/)

---
