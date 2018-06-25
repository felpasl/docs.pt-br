---
title: Comando dotnet tool list – CLI do .NET Core
description: O comando dotnet tool list lista a Ferramenta Global do .NET Core especificada no computador.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 5f4793cd37c3a8df06eb6930ad9f381ac70d4e67
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696719"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>Nome

`dotnet tool list` – lista todas as [Ferramentas Globais do .NET Core](global-tools.md) atualmente instaladas no diretório padrão do computador ou no caminho especificado.

## <a name="synopsis"></a>Sinopse

```
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a>Descrição

O comando `dotnet tool list` fornece uma maneira de listar todas as Ferramentas Globais do .NET Core instaladas de todos os usuários no computador (perfil do usuário atual) ou no caminho especificado. O comando lista o nome do pacote, a versão instalada e o comando da Ferramenta Global. Para usar o comando list, você precisa especificar que deseja ver todas as ferramentas de todos os usuários usando a opção `--global` ou especificar um caminho personalizado usando a opção `--tool-path`.

## <a name="options"></a>Opções

`-g|--global`

Lista as Ferramentas Globais de todos os usuários. Não pode ser combinada com a opção `--tool-path`. Se você não especificar essa opção, especifique a opção `--tool-path`.

`-h|--help`

Imprime uma ajuda breve para o comando.

`--tool-path <PATH>`

Especifica um local personalizado no qual encontrar as Ferramentas Globais. PATH pode ser absoluto ou relativo. Não pode ser combinada com a opção `--global`. Se você não especificar essa opção, especifique a opção `--global`.

## <a name="examples"></a>Exemplos

Lista todas as Ferramentas Globais instaladas de todos os usuários no computador (perfil do usuário atual):

`dotnet tool list -g`

Lista as Ferramentas Globais de uma pasta específica do Windows:

`dotnet tool list --tool-path c:\global-tools`

Lista as Ferramentas Globais de uma pasta específica do Linux/macOS:

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a>Consulte também

[Ferramentas Globais do .NET Core](global-tools.md)