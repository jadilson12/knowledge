---
description: Dicas do pacman
---

# Pacman tips - pt-BR

Lista os pacotes órfãos

```bash
$ pacman -Qtd
```

Verifica a lista, caso queria deletar toda a lista de uma vez.

Remove toda a lista de pacotes órfãos, ou seja, aqueles que ja não são dependentes de nenhum outro pacote.

```text
$ pacman -Rsn $(pacman - Qdtq)
```

Limpa os pacotes antigos do cache que não estão instalado

```text
$ pacman -Sc
```

Limpa todo o cache

```text
$ pacman -Scc
```

