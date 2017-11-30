---
title: Estruturas (F#)
description: 'Saiba mais sobre a estrutura F #, um tipo de objeto compact geralmente mais eficiente do que uma classe para tipos com uma pequena quantidade de dados e comportamento simple.'
keywords: "visual f#, f#, programação funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 50819506-3210-418f-9602-0ee1c9a52177
ms.openlocfilehash: 542b69a5aacb8fcfb0e8f6d6c943fe1954c4c59c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="structures"></a><span data-ttu-id="822dc-104">Estruturas</span><span class="sxs-lookup"><span data-stu-id="822dc-104">Structures</span></span>

<span data-ttu-id="822dc-105">Um *estrutura* é um tipo de objeto compact que pode ser mais eficiente do que uma classe para tipos que têm uma pequena quantidade de dados e comportamento simple.</span><span class="sxs-lookup"><span data-stu-id="822dc-105">A *structure* is a compact object type that can be more efficient than a class for types that have a small amount of data and simple behavior.</span></span>

## <a name="syntax"></a><span data-ttu-id="822dc-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="822dc-106">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements
```

## <a name="remarks"></a><span data-ttu-id="822dc-107">Comentários</span><span class="sxs-lookup"><span data-stu-id="822dc-107">Remarks</span></span>
<span data-ttu-id="822dc-108">Estruturas são *os tipos de valor*, o que significa que eles são armazenados diretamente na pilha ou, quando eles são usados como campos ou tipo de elementos da matriz, embutido no pai.</span><span class="sxs-lookup"><span data-stu-id="822dc-108">Structures are *value types*, which means that they are stored directly on the stack or, when they are used as fields or array elements, inline in the parent type.</span></span> <span data-ttu-id="822dc-109">Ao contrário de classes e registros, as estruturas têm semântica de passar-por-valor.</span><span class="sxs-lookup"><span data-stu-id="822dc-109">Unlike classes and records, structures have pass-by-value semantics.</span></span> <span data-ttu-id="822dc-110">Isso significa que elas são úteis principalmente para pequenos agregados de dados que são acessados e copiados com frequência.</span><span class="sxs-lookup"><span data-stu-id="822dc-110">This means that they are useful primarily for small aggregates of data that are accessed and copied frequently.</span></span>

<span data-ttu-id="822dc-111">Na sintaxe anterior, duas formas são mostradas.</span><span class="sxs-lookup"><span data-stu-id="822dc-111">In the previous syntax, two forms are shown.</span></span> <span data-ttu-id="822dc-112">A primeira não é a sintaxe leve, mas ela é usada com frequência, pois quando você usa as palavras-chave `struct` e `end`, é possível omitir o atributo `StructAttribute`, que aparece na segunda forma.</span><span class="sxs-lookup"><span data-stu-id="822dc-112">The first is not the lightweight syntax, but it is nevertheless frequently used because, when you use the `struct` and `end` keywords, you can omit the `StructAttribute` attribute, which appears in the second form.</span></span> <span data-ttu-id="822dc-113">É possível abreviar `StructAttribute` como apenas `Struct`.</span><span class="sxs-lookup"><span data-stu-id="822dc-113">You can abbreviate `StructAttribute` to just `Struct`.</span></span>

<span data-ttu-id="822dc-114">O *elementos de definição do tipo* na sintaxe anterior representa definições e declarações de membro.</span><span class="sxs-lookup"><span data-stu-id="822dc-114">The *type-definition-elements* in the previous syntax represents member declarations and definitions.</span></span> <span data-ttu-id="822dc-115">As estruturas podem ter construtores e campos mutáveis e imutáveis e podem declarar membros e implementações de interface.</span><span class="sxs-lookup"><span data-stu-id="822dc-115">Structures can have constructors and mutable and immutable fields, and they can declare members and interface implementations.</span></span> <span data-ttu-id="822dc-116">Para obter mais informações, consulte [membros](members/index.md).</span><span class="sxs-lookup"><span data-stu-id="822dc-116">For more information, see [Members](members/index.md).</span></span>

<span data-ttu-id="822dc-117">As estruturas não podem participar da herança, não podem conter associações `let` ou `do` e não podem conter recursivamente campos de seu próprio tipo (embora possam conter células de referência que fazem referência ao seu próprio tipo).</span><span class="sxs-lookup"><span data-stu-id="822dc-117">Structures cannot participate in inheritance, cannot contain `let` or `do` bindings, and cannot recursively contain fields of their own type (although they can contain reference cells that reference their own type).</span></span>

<span data-ttu-id="822dc-118">Como as estruturas não permitem associações `let`, você deve declarar campos em estruturas usando a palavra-chave `val`.</span><span class="sxs-lookup"><span data-stu-id="822dc-118">Because structures do not allow `let` bindings, you must declare fields in structures by using the `val` keyword.</span></span> <span data-ttu-id="822dc-119">A palavra-chave `val` define um campo e seu tipo, mas não permite inicialização.</span><span class="sxs-lookup"><span data-stu-id="822dc-119">The `val` keyword defines a field and its type but does not allow initialization.</span></span> <span data-ttu-id="822dc-120">Em vez disso, as declarações `val` são inicializadas como zero ou nulo.</span><span class="sxs-lookup"><span data-stu-id="822dc-120">Instead, `val` declarations are initialized to zero or null.</span></span> <span data-ttu-id="822dc-121">Por esse motivo, as estruturas que possuem um construtor implícito (ou seja, parâmetros que são fornecidos imediatamente após o nome da estrutura na declaração) requerem que declarações `val` sejam anotadas com o atributo `DefaultValue`.</span><span class="sxs-lookup"><span data-stu-id="822dc-121">For this reason, structures that have an implicit constructor (that is, parameters that are given immediately after the structure name in the declaration) require that `val` declarations be annotated with the `DefaultValue` attribute.</span></span> <span data-ttu-id="822dc-122">As estruturas que tenham um construtor definido ainda oferecem suporte à inicialização como zero.</span><span class="sxs-lookup"><span data-stu-id="822dc-122">Structures that have a defined constructor still support zero-initialization.</span></span> <span data-ttu-id="822dc-123">Portanto, o atributo `DefaultValue` é uma declaração de que um valor zero é válido para o campo.</span><span class="sxs-lookup"><span data-stu-id="822dc-123">Therefore, the `DefaultValue` attribute is a declaration that such a zero value is valid for the field.</span></span> <span data-ttu-id="822dc-124">Construtores implícitos para estruturas não executam nenhuma ação, pois as associações `let` e `do` não são permitidas no tipo, mas os valores de parâmetro construtor implícito passados estão disponíveis como campos particulares.</span><span class="sxs-lookup"><span data-stu-id="822dc-124">Implicit constructors for structures do not perform any actions because `let` and `do` bindings aren’t allowed on the type, but the implicit constructor parameter values passed in are available as private fields.</span></span>

<span data-ttu-id="822dc-125">Construtores explícitos podem envolver inicialização de valores do campo.</span><span class="sxs-lookup"><span data-stu-id="822dc-125">Explicit constructors might involve initialization of field values.</span></span> <span data-ttu-id="822dc-126">Quando você tem uma estrutura que possui um construtor explícito, ela ainda suporta inicialização como zero; no entanto, você não usa o atributo `DefaultValue` nas declarações `val`, pois ela entra em conflito com o construtor explícito.</span><span class="sxs-lookup"><span data-stu-id="822dc-126">When you have a structure that has an explicit constructor, it still supports zero-initialization; however, you do not use the `DefaultValue` attribute on the `val` declarations because it conflicts with the explicit constructor.</span></span> <span data-ttu-id="822dc-127">Para obter mais informações sobre `val` declarações, consulte [campos explícitos: A `val` palavra-chave](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="822dc-127">For more information about `val` declarations, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="822dc-128">Modificadores de atributos e de acessibilidade são permitidos em estruturas e seguem as mesmas regras dos outros tipos.</span><span class="sxs-lookup"><span data-stu-id="822dc-128">Attributes and accessibility modifiers are allowed on structures, and follow the same rules as those for other types.</span></span> <span data-ttu-id="822dc-129">Para obter mais informações, consulte [atributos](attributes.md) e [controle de acesso](access-control.md).</span><span class="sxs-lookup"><span data-stu-id="822dc-129">For more information, see [Attributes](attributes.md) and [Access Control](access-control.md).</span></span>

<span data-ttu-id="822dc-130">Os exemplos de código a seguir ilustram definições de estrutura.</span><span class="sxs-lookup"><span data-stu-id="822dc-130">The following code examples illustrate structure definitions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="struct-records-and-discriminated-unions"></a><span data-ttu-id="822dc-131">Registros de estrutura e uniões discriminadas</span><span class="sxs-lookup"><span data-stu-id="822dc-131">Struct Records and Discriminated Unions</span></span>

<span data-ttu-id="822dc-132">A partir do F # 4.1, você pode representar [registros](records.md) e [uniões discriminada](discriminated-unions.md) como estruturas com o `[<Struct>]` atributo.</span><span class="sxs-lookup"><span data-stu-id="822dc-132">Starting with F# 4.1, you can represent [Records](records.md) and [Discriminated Unions](discriminated-unions.md) as structs with the `[<Struct>]` attribute.</span></span>  <span data-ttu-id="822dc-133">Consulte cada artigo para saber mais.</span><span class="sxs-lookup"><span data-stu-id="822dc-133">See each article to learn more.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="822dc-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="822dc-134">See Also</span></span>
[<span data-ttu-id="822dc-135">Referência da Linguagem F#</span><span class="sxs-lookup"><span data-stu-id="822dc-135">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="822dc-136">Classes</span><span class="sxs-lookup"><span data-stu-id="822dc-136">Classes</span></span>](classes.md)

[<span data-ttu-id="822dc-137">Registros</span><span class="sxs-lookup"><span data-stu-id="822dc-137">Records</span></span>](records.md)

[<span data-ttu-id="822dc-138">Membros</span><span class="sxs-lookup"><span data-stu-id="822dc-138">Members</span></span>](members/index.md)