---
title: "'.' ou '!' à esquerda só podem aparecer dentro de uma instrução 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 367da8e7c9fd8c14a16a09b1f023e7637d78309d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259544"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a>'.' ou '!' à esquerda só podem aparecer dentro de uma instrução 'With'
Um ponto (.) ou um ponto de exclamação (!) que não está dentro um `With` bloco ocorre sem uma expressão à esquerda. Acesso de membro (`.`) e acesso de membro de dicionário (`!`) exigem uma expressão que especifica o elemento que contém o membro. Isso deve aparecer imediatamente à esquerda do acessador ou como o destino de um `With` bloco que contém o acesso de membro.  
  
 **ID do erro:** BC30157  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1.  Certifique-se de que o `With` bloco está formatado corretamente.  
  
2.  Se não houver nenhum `With` de blocos, adicione uma expressão à esquerda do acessador que é avaliada para um elemento definido que contém o membro.  
  
## <a name="see-also"></a>Consulte também
- [Caracteres Especiais no Código](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [Instrução With ... End With](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
