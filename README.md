# IFSC — Ciência da Computação

Repositório para centralizar exercícios e projetos desenvolvidos durante a graduação em Ciência da Computação.

## Organização

```text
subjects/
└── <disciplina>/
    ├── README.md
    ├── exercises/          # Atividades pequenas e listas de exercícios
    └── projects/           # Trabalhos e projetos maiores
```

Cada entrega fica em uma pasta própria, usando `kebab-case` e, quando a ordem for relevante, um prefixo numérico:

```text
subjects/estrutura-de-dados/projects/01-lista-encadeada/
```

A organização prioriza a disciplina e a entrega, não a linguagem de programação. Projetos com mais de uma tecnologia podem usar pastas como `apps/` e `services/` internamente.

## Projetos

Cada exercício ou projeto deve ser autocontido e incluir um `README.md` com:

- disciplina e período;
- objetivo ou enunciado;
- linguagem e versões necessárias;
- instalação de dependências;
- comandos de execução e testes;
- particularidades da entrega.

Os manifests de configuração devem permanecer no projeto correspondente. O Bun centraliza as dependências e o lockfile na raiz do workspace. Dependências, builds, caches, segredos e arquivos temporários não devem ser versionados.

## TypeScript

Os projetos TypeScript usam **Bun workspaces**. Para que um projeto seja reconhecido, ele deve estar em `subjects/<disciplina>/exercises/<entrega>/` ou `subjects/<disciplina>/projects/<entrega>/` e conter um `package.json` com um `name` único.

Instale as dependências de todos os pacotes a partir da raiz:

```bash
bun install
```

Execute um script de um pacote específico sem sair da raiz:

```bash
bun --filter <nome-do-pacote> test
bun --filter <nome-do-pacote> lint
bun --filter <nome-do-pacote> typecheck
```

Outras linguagens mantêm suas ferramentas nativas, como `uv`/pip para Python, Maven/Gradle para Java e CMake para C/C++.

## Documentação

O `README.md` de cada disciplina registra seu conteúdo, períodos cursados e entregas. Novas disciplinas devem seguir a mesma estrutura de `subjects/ciencia-de-dados/`.
