---
title: Operador = – Referência de C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 2c999e76a9238e6401e89af0faa81967b13a3995
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244382"
---
# <a name="-operator-c-reference"></a>Operador = (Referência de C#)

O operador de atribuição `=` atribui o valor do operando do lado direito a uma variável, uma [propriedade](../../programming-guide/classes-and-structs/properties.md) ou um elemento [indexador](../../../csharp/programming-guide/indexers/index.md) fornecido pelo operando do lado esquerdo. O resultado de uma expressão de atribuição é o valor atribuído a um operando do lado esquerdo. O tipo do operandos do lado direito deve ser do mesmo tipo ou implicitamente conversível para o operando do lado esquerdo.

O operador de atribuição é associativo direito, ou seja, uma expressão da forma

```csharp
a = b = c
```

é avaliada como

```csharp
a = (b = c)
```

O exemplo a seguir demonstra o uso do operador de atribuição para atribuir valores a uma variável local, uma propriedade e um elemento do indexador:

[!code-csharp-interactive[assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#Assignments)]

## <a name="ref-assignment-operator"></a>Operador de atribuição ref

Começando pelo C# 7.3, você pode usar o operador de atribuição ref `= ref` para reatribuir uma variável [ref local](../keywords/ref.md#ref-locals) ou [ref readonly local](../keywords/ref.md#ref-readonly-locals). O exemplo a seguir demonstra o uso do operador de atribuição ref:

[!code-csharp[ref assignment operator](~/samples/snippets/csharp/language-reference/operators/AssignmentExamples.cs#RefAssignment)]

No caso do operador de atribuição ref, o tipo do operando esquerdo e do direito deve ser o mesmo.

Para saber mais, confira a [nota da proposta do recurso](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.3/ref-local-reassignment.md).

## <a name="operator-overloadability"></a>Capacidade de sobrecarga do operador

Um tipo definido pelo usuário não pode sobrecarregar o operador de atribuição. No entanto, um tipo definido pelo usuário pode definir uma conversão implícita em outro tipo. Dessa forma, o valor de um tipo definido pelo usuário pode ser atribuído a uma variável, uma propriedade ou um elemento do indexador de outro tipo. Para saber mais, confira o artigo de palavra-chave [implícito](../keywords/implicit.md).

## <a name="c-language-specification"></a>Especificação da linguagem C#

Para saber mais, confira a seção [Atribuição simples](~/_csharplang/spec/expressions.md#simple-assignment) na [especificação da linguagem C#](../language-specification/index.md).

## <a name="see-also"></a>Consulte também

- [Referência de C#](../index.md)
- [Guia de Programação em C#](../../programming-guide/index.md)
- [Operadores do C#](index.md)
- [ref keyword](../keywords/ref.md)
