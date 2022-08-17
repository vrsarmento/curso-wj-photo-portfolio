# Boas Práticas

## Merge / Rebase

> Está atualizando sua branch pegando as coisas do main?

USE REBASE (PULL --REBASE)

> Terminou sua feature na branch e quer jogar para o main?

USE MERGE

---

## Reverter uma alteração errada / bug

> Commit errado na **main**

USE REVERT

Desse modo, o histórico se manterá inalterado, evitando problemas com outros usuários que porventura já tenham realizado _pull_ dessa mudança. Um _commit_ da reversão será criado.  
**Nunca altere o histórico no MAIN**

> Commit errado numa **branch** separada

USE RESET --hard / --mixed / --soft

---

## Adicionar uma alteração ao último _commit_

> Use apenas se o commit não foi enviada para o repositório remoto, pois altera o histórico.

GIT COMMIT --AMEND

---

## Adicionar trechos de alterações a um commit

> Usado quando se faz muitas mudanças em 1 arquivo e se deseja separá-las em mais de 1 commit.

GIT ADD -P

---

## Juntar vários commits menores em apenas um

> Usado quando se faz muitos commits que são relacionados a uma feature.

GIT REBASE -I HEAD~<número de commits abaixo do HEAD>

---

## Juntar vários commits de _fixup_ em um usando _squash_

> Usado quando se faz commits de ajuste (--fixup) em outro relacionado a uma feature. Usado em _features branches_

GIT COMMIT --FIXUP <hash>
GIT REBASE -I --AUTOSQUASH <hash>

---

## Criar um arquivo _zip_ do repositório

GIT ARCHIVE <BRANCH> --FORMAT=ZIP --OUTPUT=<FILENAME>

---

## Customizando o _log_

> Visualização

GIT LOG --PRETTY=ONELINE --GRAPH --ALL
GIT LOG -5 (Exibe os 5 últimos commits)
GIT SHORTLOG

> Filtros

GIT LOG --SINCE='AGO 5 2022' --UNTIL='AGO 9 2022'
GIT LOG --AUTHOR='VICTOR'

---

## Log mais detalhado com _reflog_

> Útil para recuperar commits depois de um _git reset --hard_ ou depois de outra ação que eliminou alguma informação importante

GIT REFLOG

---

## Issues and Pull Requests

> https://github.com/devspace/awesome-github-templates

---

## Workflows

> Centralized

- Branch única (master / main)
- Funciona melhor com equipes bem pequenas (3 ou 4 pessoas)
- Arriscado

> Feature Branch

- Uma branch para cada feature
- Evita conflitos e permite trabalhos em paralelo
- Funciona bem com equipes maiores
- Facilita a visualização do histórico
- Criar Branch -> Realizar as Mudanças -> Push -> Pull Request -> Code Review -> Merge com Main

> Gitflow

- Parecido com o Feature Branch
- Para projetos explicitamente versionados ou se há a necessidade de suportar múltiplas versões do software.
- Um post a respeito: [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)

> GitHub Flow

- Mais simples que o Git Flow
- Melhor para projetos que usam CD(Continuous Delivery)
- [Doc](https://docs.github.com/pt/get-started/quickstart/github-flow)
