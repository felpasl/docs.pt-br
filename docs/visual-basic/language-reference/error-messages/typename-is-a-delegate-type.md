---
title: "'<typename>' é um tipo delegado"
ms.date: 07/20/2015
f1_keywords:
- bc32008
- vbc32008
helpviewer_keywords:
- BC32008
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
ms.openlocfilehash: 4278ea0fc6a8dc2c6a90b720d2da70b1c26f2a17
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283446"
---
# <a name="typename-is-a-delegate-type"></a>'\<typename >' é um tipo delegado
'\<typename >' é um tipo delegado. A construção Delegate permite apenas uma única expressão AddressOf como uma lista de argumentos. Geralmente, uma expressão de AddressOf pode ser usada em vez de uma construção de delegado.  
  
 Um `New` cláusula criando uma instância de uma classe de representante fornece uma lista de argumentos inválida para o construtor do delegado.  
  
 Você pode fornecer um único `AddressOf` expressão durante a criação de uma nova instância de delegado.  
  
 Esse erro pode resultar se você não passar argumentos para o construtor delegado, se você passar mais de um argumento ou se você passar um argumento único que não é válido `AddressOf` expressão.  
  
 **ID do erro:** BC32008  
  
## <a name="to-correct-this-error"></a>Para corrigir este erro  
  
-   Usar uma única `AddressOf` expressão na lista de argumentos para a classe de delegado no `New` cláusula.  
  
## <a name="see-also"></a>Consulte também
- [Operador New](../../../visual-basic/language-reference/operators/new-operator.md)
- [Operador AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Como: Invocar um método delegado](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
