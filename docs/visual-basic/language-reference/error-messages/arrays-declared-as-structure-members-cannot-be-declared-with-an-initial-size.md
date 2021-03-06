---
title: Matrizes declaradas como membros de estrutura não podem ser declaradas com um tamanho inicial
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 06e5e36f3e0522e0449c0ef9698f3a1b01b9cb5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549061"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>Matrizes declaradas como membros de estrutura não podem ser declaradas com um tamanho inicial
Uma matriz em uma estrutura é declarada com um tamanho inicial. Você não pode inicializar qualquer elemento de estrutura e a declaração de um tamanho da matriz é uma forma de inicialização.  
  
 **ID do erro:** BC31043  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
1.  Defina a matriz na sua estrutura como dinâmica (sem tamanho inicial).  
  
2.  Se você precisar de um determinado tamanho de matriz, você pode redimensionar uma matriz dinâmica com um [instrução ReDim](../../../visual-basic/language-reference/statements/redim-statement.md) quando seu código está em execução. O exemplo a seguir ilustra essa situação.  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>Consulte também
- [Matrizes](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Como: declarar uma estrutura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
