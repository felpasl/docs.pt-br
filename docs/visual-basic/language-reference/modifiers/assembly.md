---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: e6cb7e7a2520d6bb586dab4ed0af75abb04fabd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726462"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Especifica que um atributo no início de um arquivo de origem se aplica a todo o assembly.  
  
## <a name="remarks"></a>Comentários  
 Muitos atributos referem-se a um elemento de programação individual, como uma classe ou propriedade. Aplicar tal um atributo, anexando o bloco de atributo, entre colchetes angulares (`< >`), diretamente à instrução de declaração.  
  
 Se um atributo pertence não apenas para o seguinte elemento mas ao conjunto inteiro, você coloca o bloco de atributo no início do arquivo de origem e identifica o atributo com o `Assembly` palavra-chave. Se ele se aplica ao módulo assembly atual, você usar o [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) palavra-chave.  
  
 Você também pode aplicar um atributo a um assembly no arquivo AssemblyInfo vb, caso em que você não precisa usar um bloco de atributo em seu arquivo de código-fonte principal.  
  
## <a name="see-also"></a>Consulte também
- [Módulo \<palavra-chave >](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Visão geral de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)

