---
description: Dicas do YAY
---

# Yay tips - pt-BR

O uso do YAY é semelhante a outros auxiliares e gerenciadores de pacotes do AUR.

Para limpar todas as dependências indesejadas do seu sistema, execute o seguinte comando:

```text
$ yay -Yc
```

Para imprimir a lista de pacotes que precisam ser atualizados, execute o seguinte comando:

```text
$ yay -Pu
```

Se você deseja imprimir as estatísticas do sistema, execute o seguinte comando:

```text
$ yay -Ps
```

Para instalar um pacote do utilitário YAY, execute o seguinte comando:

```text
$ yay -s arch-wiki-man
```

Para procurar um pacote no AUR e no repositório oficial, execute o seguinte comando:

```text
$ yay -Ss arch-wiki-cli
```

Para ver as informações detalhadas sobre um determinado pacote:

```text
$ yay -Si arch-wiki-cli
```

Podemos pesquisar o pacote já instalado usando a seguinte opção:

```text
$ yay -Qs arch-wiki-man
```

Para obter informações sobre o pacote instalado:

```text
$ yay -Qi arch-wiki-man
```

Use o comando abaixo para atualizar qualquer pacote ou pacote no seu sistema:

```text
$ yay -Syu
```

