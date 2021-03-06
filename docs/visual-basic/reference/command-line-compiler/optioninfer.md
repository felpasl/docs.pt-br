---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: 82a8667c32c6396a868375555b003d0082ce1a73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709969"
---
# <a name="-optioninfer"></a>-optioninfer
Permite o uso de inferência de tipo local nas declarações de variáveis.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Termo|Definição|  
|---|---|  
|`+` &#124; `-`|Opcional. Especifique `-optioninfer+` para habilitar a inferência de tipo de local ou `-optioninfer-` para bloqueá-la. A opção `-optioninfer`, sem valor especificado, é a mesma de `-optioninfer+`. O valor padrão quando o comutador `-optioninfer` não estiver presente também é `-optioninfer+`. O valor padrão é definido no arquivo de resposta Vbc.rsp.|  
  
> [!NOTE]
>  Você pode usar a opção `-noconfig` para manter os padrões internos do compilador em vez dos especificados no vbc.rsp. O padrão do compilador para essa opção é `-optioninfer-`.  
  
## <a name="remarks"></a>Comentários  
 Se o arquivo de código fonte contém um [instrução opção inferir](../../../visual-basic/language-reference/statements/option-infer-statement.md), a instrução substitui a `-optioninfer` configuração do compilador de linha de comando.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>Definir - optioninfer no IDE do Visual Studio  
  
1.  Selecione um projeto no **Gerenciador de soluções**. No menu **Projeto**, clique em **Propriedades**.  
  
2.  Sobre o **compilar** guia, modifique o valor na **Option infer** caixa.  
  
## <a name="example"></a>Exemplo  
 O seguinte código compila `test.vb` com a inferência de tipo local habilitada.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Consulte também
- [Compilador de linha de comando do Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Linhas de Comando de Compilação de Exemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Instrução Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Inferência de Tipo de Variável Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Caixa de diálogo Padrões do Visual Basic, Projetos, Opções](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [Página de Compilação, Designer de Projeto (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Compilando da Linha de Comando](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
