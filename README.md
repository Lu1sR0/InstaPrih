<div align="center">

# InstaPrih

Rede social inspirada no Instagram, com feed, posts com imagem, curtidas, salvos e perfis de usuário.

![React](https://img.shields.io/badge/React-0D0D0D?style=for-the-badge&logo=react&logoColor=FF003C)
![TypeScript](https://img.shields.io/badge/TypeScript-0D0D0D?style=for-the-badge&logo=typescript&logoColor=FF003C)
![Vite](https://img.shields.io/badge/Vite-0D0D0D?style=for-the-badge&logo=vite&logoColor=FF003C)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-0D0D0D?style=for-the-badge&logo=tailwindcss&logoColor=FF003C)
![Appwrite](https://img.shields.io/badge/Appwrite-0D0D0D?style=for-the-badge&logo=appwrite&logoColor=FF003C)
![React Query](https://img.shields.io/badge/React_Query-0D0D0D?style=for-the-badge&logo=reactquery&logoColor=FF003C)
![shadcn/ui](https://img.shields.io/badge/shadcn%2Fui-0D0D0D?style=for-the-badge&logo=shadcnui&logoColor=FF003C)

</div>

## Sobre

O **InstaPrih** é uma aplicação web de rede social: o usuário cria uma conta, publica fotos com legenda, localização e tags, explora posts de outras pessoas, curte, salva e visita perfis. O back-end fica todo no **Appwrite** (autenticação, banco de dados e armazenamento de imagens), e o front-end usa **React Query** para cache, paginação e atualização dos dados.

A interface foi traduzida e adaptada para o português.

> Projeto desenvolvido acompanhando o tutorial de rede social do canal [JavaScript Mastery](https://www.youtube.com/@javascriptmastery) ([vídeo](https://youtu.be/_W3R2VwRyF4) · [repositório original](https://github.com/adrianhajdin/social_media_app)).

## Funcionalidades

- **Cadastro e login** com e-mail e senha (Appwrite Auth), com validação dos formulários em português.
- **Rotas protegidas**: usuários sem sessão são redirecionados para `/sign-in`.
- **Feed** com os posts mais recentes e uma lista de membros da comunidade.
- **Explorar** com busca por legenda (debounce de 500 ms) e rolagem infinita.
- **Criar, editar e excluir posts** com upload de imagem por arrastar e soltar (JPEG/PNG).
- **Curtir e salvar** posts, com página de **Salvos** e aba de **Curtidas** no próprio perfil.
- **Detalhes do post** com a seção "Posts do mesmo autor".
- **Perfil** com contagem de posts e **edição de perfil** (foto, nome, usuário e bio).
- **Lista de usuários** cadastrados.
- **Layout responsivo**: barra lateral no desktop, barra superior e barra inferior no mobile.

## Tecnologias

- [React 18](https://react.dev/) + [TypeScript 5](https://www.typescriptlang.org/)
- [Vite 4](https://vitejs.dev/)
- [Tailwind CSS 3](https://tailwindcss.com/) + componentes [shadcn/ui](https://ui.shadcn.com/) (Radix UI)
- [Appwrite 13](https://appwrite.io/) — Auth, Databases, Storage e Avatars
- [TanStack React Query 4](https://tanstack.com/query) — queries, mutations e infinite queries
- [React Router 6](https://reactrouter.com/)
- [React Hook Form](https://react-hook-form.com/) + [Zod](https://zod.dev/) — formulários e validação
- [react-dropzone](https://react-dropzone.js.org/) e [react-intersection-observer](https://github.com/thebuilder/react-intersection-observer)
- Deploy na [Vercel](https://vercel.com/) (rewrite de SPA em `vercel.json`)

## Estrutura

```
src/
├── _auth/            # layout e formulários de login e cadastro
├── _root/            # layout autenticado e páginas (Home, Explorar, Perfil, Salvos…)
├── components/
│   ├── forms/        # formulário de post
│   ├── shared/       # sidebar, topbar, bottombar, cards, upload de arquivos
│   └── ui/           # componentes shadcn/ui
├── context/          # AuthContext (sessão do usuário)
├── hooks/            # useDebounce
├── lib/
│   ├── appwrite/     # client e funções de acesso à API
│   ├── react-query/  # queries, mutations e query keys
│   └── validation/   # schemas Zod
└── types/
```

## Como rodar localmente

Pré-requisitos: Node.js 18+ e um projeto no [Appwrite](https://appwrite.io/) com um banco de dados (coleções de usuários, posts e salvos) e um bucket de armazenamento.

```bash
git clone https://github.com/Lu1sR0/InstaPrih.git
cd InstaPrih
npm install
```

Crie um arquivo `.env.local` na raiz com as variáveis:

```env
VITE_APPWRITE_URL=
VITE_APPWRITE_PROJECT_ID=
VITE_APPWRITE_DATABASE_ID=
VITE_APPWRITE_STORAGE_ID=
VITE_APPWRITE_USER_COLLECTION_ID=
VITE_APPWRITE_POST_COLLECTION_ID=
VITE_APPWRITE_SAVES_COLLECTION_ID=
```

Depois rode:

```bash
npm run dev       # servidor de desenvolvimento em http://localhost:5173
npm run build     # checagem de tipos + build de produção
npm run preview   # pré-visualiza o build
```

---

<div align="center">
Desenvolvido por <a href="https://github.com/Lu1sR0">Luis Roberto</a> · <a href="https://outframe.dev">Outframe</a>
</div>
