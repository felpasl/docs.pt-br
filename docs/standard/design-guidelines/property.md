---
title: Design de propriedade
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 477b3b69ce1b8a3bb160e8e120885239e3d99e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="property-design"></a><span data-ttu-id="e682f-102">Design de propriedade</span><span class="sxs-lookup"><span data-stu-id="e682f-102">Property Design</span></span>
<span data-ttu-id="e682f-103">Embora tecnicamente muito semelhantes aos métodos de propriedades, eles são muito diferentes em termos de seus cenários de uso.</span><span class="sxs-lookup"><span data-stu-id="e682f-103">Although properties are technically very similar to methods, they are quite different in terms of their usage scenarios.</span></span> <span data-ttu-id="e682f-104">Eles devem ser considerados como campos inteligentes.</span><span class="sxs-lookup"><span data-stu-id="e682f-104">They should be seen as smart fields.</span></span> <span data-ttu-id="e682f-105">Eles têm a sintaxe de chamada de campos e a flexibilidade de métodos.</span><span class="sxs-lookup"><span data-stu-id="e682f-105">They have the calling syntax of fields, and the flexibility of methods.</span></span>  
  
 <span data-ttu-id="e682f-106">**FAZER ✓** criar propriedades somente obtenção se o chamador não deve ser capaz de alterar o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="e682f-106">**✓ DO** create get-only properties if the caller should not be able to change the value of the property.</span></span>  
  
 <span data-ttu-id="e682f-107">Tenha em mente que, se o tipo de propriedade é um tipo de referência mutável, o valor da propriedade pode ser alterado, mesmo se a propriedade é somente obtenção.</span><span class="sxs-lookup"><span data-stu-id="e682f-107">Keep in mind that if the type of the property is a mutable reference type, the property value can be changed even if the property is get-only.</span></span>  
  
 <span data-ttu-id="e682f-108">**X não** fornecer somente conjunto de propriedades ou propriedades setter ter acessibilidade mais ampla que o getter.</span><span class="sxs-lookup"><span data-stu-id="e682f-108">**X DO NOT** provide set-only properties or properties with the setter having broader accessibility than the getter.</span></span>  
  
 <span data-ttu-id="e682f-109">Por exemplo, não use propriedades com um setter público e um getter protegido.</span><span class="sxs-lookup"><span data-stu-id="e682f-109">For example, do not use properties with a public setter and a protected getter.</span></span>  
  
 <span data-ttu-id="e682f-110">Se a propriedade getter não pode ser fornecido, implemente a funcionalidade como um método em vez disso.</span><span class="sxs-lookup"><span data-stu-id="e682f-110">If the property getter cannot be provided, implement the functionality as a method instead.</span></span> <span data-ttu-id="e682f-111">Comece com o nome do método `Set` e acompanhe o que poderia ter chamado a propriedade.</span><span class="sxs-lookup"><span data-stu-id="e682f-111">Consider starting the method name with `Set` and follow with what you would have named the property.</span></span> <span data-ttu-id="e682f-112">Por exemplo, <xref:System.AppDomain> tem um método chamado `SetCachePath` em vez de ter uma propriedade somente conjunto chamada `CachePath`.</span><span class="sxs-lookup"><span data-stu-id="e682f-112">For example, <xref:System.AppDomain> has a method called `SetCachePath` instead of having a set-only property called `CachePath`.</span></span>  
  
 <span data-ttu-id="e682f-113">**FAZER ✓** fornecem valores padrão adequado para todas as propriedades, garantindo que os padrões não resultam em uma falha de segurança ou um código extremamente ineficiente.</span><span class="sxs-lookup"><span data-stu-id="e682f-113">**✓ DO** provide sensible default values for all properties, ensuring that the defaults do not result in a security hole or terribly inefficient code.</span></span>  
  
 <span data-ttu-id="e682f-114">**FAZER ✓** permitem que propriedades sejam definidas em qualquer ordem, mesmo que isso resulte em um estado inválido temporário do objeto.</span><span class="sxs-lookup"><span data-stu-id="e682f-114">**✓ DO** allow properties to be set in any order even if this results in a temporary invalid state of the object.</span></span>  
  
 <span data-ttu-id="e682f-115">É comum para duas ou mais propriedades para ser relacionados a um ponto em que alguns valores de uma propriedade podem ser inválidos dados os valores de outras propriedades no mesmo objeto.</span><span class="sxs-lookup"><span data-stu-id="e682f-115">It is common for two or more properties to be interrelated to a point where some values of one property might be invalid given the values of other properties on the same object.</span></span> <span data-ttu-id="e682f-116">Nesses casos, exceções resultantes do estado inválido devem ser adiadas até que as propriedades inter-relacionados, na verdade, são usadas juntos pelo objeto.</span><span class="sxs-lookup"><span data-stu-id="e682f-116">In such cases, exceptions resulting from the invalid state should be postponed until the interrelated properties are actually used together by the object.</span></span>  
  
 <span data-ttu-id="e682f-117">**FAZER ✓** preservar o valor anterior, se um setter de propriedade gera uma exceção.</span><span class="sxs-lookup"><span data-stu-id="e682f-117">**✓ DO** preserve the previous value if a property setter throws an exception.</span></span>  
  
 <span data-ttu-id="e682f-118">**X Evite** Lançando exceções getters de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e682f-118">**X AVOID** throwing exceptions from property getters.</span></span>  
  
 <span data-ttu-id="e682f-119">Getters de propriedade devem ser operações simples e não devem ter qualquer pré-condições.</span><span class="sxs-lookup"><span data-stu-id="e682f-119">Property getters should be simple operations and should not have any preconditions.</span></span> <span data-ttu-id="e682f-120">Se um getter pode lançar uma exceção, ela provavelmente deveria ser reprojetada para ser um método.</span><span class="sxs-lookup"><span data-stu-id="e682f-120">If a getter can throw an exception, it should probably be redesigned to be a method.</span></span> <span data-ttu-id="e682f-121">Observe que essa regra não se aplica a indexadores, onde esperamos exceções como resultado de validação de argumentos.</span><span class="sxs-lookup"><span data-stu-id="e682f-121">Notice that this rule does not apply to indexers, where we do expect exceptions as a result of validating the arguments.</span></span>  
  
### <a name="indexed-property-design"></a><span data-ttu-id="e682f-122">Propriedade indexada Design</span><span class="sxs-lookup"><span data-stu-id="e682f-122">Indexed Property Design</span></span>  
 <span data-ttu-id="e682f-123">Uma propriedade indexada é uma propriedade especial que pode ter parâmetros e pode ser chamada com a sintaxe especial semelhante a indexação de array.</span><span class="sxs-lookup"><span data-stu-id="e682f-123">An indexed property is a special property that can have parameters and can be called with special syntax similar to array indexing.</span></span>  
  
 <span data-ttu-id="e682f-124">Propriedades indexadas são conhecidas como indexadores.</span><span class="sxs-lookup"><span data-stu-id="e682f-124">Indexed properties are commonly referred to as indexers.</span></span> <span data-ttu-id="e682f-125">Indexadores devem ser usados somente nas APIs que fornecem acesso a itens em uma coleção lógica.</span><span class="sxs-lookup"><span data-stu-id="e682f-125">Indexers should be used only in APIs that provide access to items in a logical collection.</span></span> <span data-ttu-id="e682f-126">Por exemplo, uma cadeia de caracteres é um conjunto de caracteres e o indexador em <xref:System.String?displayProperty=nameWithType> foi adicionado para acessar seus caracteres.</span><span class="sxs-lookup"><span data-stu-id="e682f-126">For example, a string is a collection of characters, and the indexer on <xref:System.String?displayProperty=nameWithType> was added to access its characters.</span></span>  
  
 <span data-ttu-id="e682f-127">**✓ CONSIDERE** usando indexadores para fornecer acesso aos dados armazenados em uma matriz interna.</span><span class="sxs-lookup"><span data-stu-id="e682f-127">**✓ CONSIDER** using indexers to provide access to data stored in an internal array.</span></span>  
  
 <span data-ttu-id="e682f-128">**✓ CONSIDERE** fornecendo indexadores em tipos que representam coleções de itens.</span><span class="sxs-lookup"><span data-stu-id="e682f-128">**✓ CONSIDER** providing indexers on types representing collections of items.</span></span>  
  
 <span data-ttu-id="e682f-129">**X Evite** usando propriedades com mais de um parâmetro indexadas.</span><span class="sxs-lookup"><span data-stu-id="e682f-129">**X AVOID** using indexed properties with more than one parameter.</span></span>  
  
 <span data-ttu-id="e682f-130">Se o projeto requer vários parâmetros, reconsidere se a propriedade realmente representa um acessador para uma coleção lógica.</span><span class="sxs-lookup"><span data-stu-id="e682f-130">If the design requires multiple parameters, reconsider whether the property really represents an accessor to a logical collection.</span></span> <span data-ttu-id="e682f-131">Se não estiver, use métodos.</span><span class="sxs-lookup"><span data-stu-id="e682f-131">If it does not, use methods instead.</span></span> <span data-ttu-id="e682f-132">Comece com o nome do método `Get` ou `Set`.</span><span class="sxs-lookup"><span data-stu-id="e682f-132">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="e682f-133">**X Evite** indexadores com tipos de parâmetro diferente de <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, ou um enum.</span><span class="sxs-lookup"><span data-stu-id="e682f-133">**X AVOID** indexers with parameter types other than <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, or an enum.</span></span>  
  
 <span data-ttu-id="e682f-134">Se o projeto requer outros tipos de parâmetros, altamente reavalie se a API realmente representa um acessador para uma coleção lógica.</span><span class="sxs-lookup"><span data-stu-id="e682f-134">If the design requires other types of parameters, strongly reevaluate whether the API really represents an accessor to a logical collection.</span></span> <span data-ttu-id="e682f-135">Se não estiver, use um método.</span><span class="sxs-lookup"><span data-stu-id="e682f-135">If it does not, use a method.</span></span> <span data-ttu-id="e682f-136">Comece com o nome do método `Get` ou `Set`.</span><span class="sxs-lookup"><span data-stu-id="e682f-136">Consider starting the method name with `Get` or `Set`.</span></span>  
  
 <span data-ttu-id="e682f-137">**FAZER ✓** usar o nome `Item` para propriedades indexadas, a menos que haja um nome obviamente melhor (por exemplo, consulte o <xref:System.String.Chars%2A> propriedade em `System.String`).</span><span class="sxs-lookup"><span data-stu-id="e682f-137">**✓ DO** use the name `Item` for indexed properties unless there is an obviously better name (e.g., see the <xref:System.String.Chars%2A> property on `System.String`).</span></span>  
  
 <span data-ttu-id="e682f-138">No c#, indexadores são, por padrão, um Item nomeado.</span><span class="sxs-lookup"><span data-stu-id="e682f-138">In C#, indexers are by default named Item.</span></span> <span data-ttu-id="e682f-139">O <xref:System.Runtime.CompilerServices.IndexerNameAttribute> pode ser usado para personalizar esse nome.</span><span class="sxs-lookup"><span data-stu-id="e682f-139">The <xref:System.Runtime.CompilerServices.IndexerNameAttribute> can be used to customize this name.</span></span>  
  
 <span data-ttu-id="e682f-140">**X não** fornecem um indexador e métodos que são semanticamente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e682f-140">**X DO NOT** provide both an indexer and methods that are semantically equivalent.</span></span>  
  
 <span data-ttu-id="e682f-141">**X não** fornecer mais de uma família de indexadores de sobrecarga em um tipo.</span><span class="sxs-lookup"><span data-stu-id="e682f-141">**X DO NOT** provide more than one family of overloaded indexers in one type.</span></span>  
  
 <span data-ttu-id="e682f-142">Isso é imposto pelo compilador c#.</span><span class="sxs-lookup"><span data-stu-id="e682f-142">This is enforced by the C# compiler.</span></span>  
  
 <span data-ttu-id="e682f-143">**X não** propriedades indexadas de não-padrão de uso.</span><span class="sxs-lookup"><span data-stu-id="e682f-143">**X DO NOT** use nondefault indexed properties.</span></span>  
  
 <span data-ttu-id="e682f-144">Isso é imposto pelo compilador c#.</span><span class="sxs-lookup"><span data-stu-id="e682f-144">This is enforced by the C# compiler.</span></span>  
  
### <a name="property-change-notification-events"></a><span data-ttu-id="e682f-145">Eventos de notificação de alteração de propriedade</span><span class="sxs-lookup"><span data-stu-id="e682f-145">Property Change Notification Events</span></span>  
 <span data-ttu-id="e682f-146">Às vezes é útil fornecer um evento que notifica o usuário sobre as alterações em um valor de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e682f-146">Sometimes it is useful to provide an event notifying the user of changes in a property value.</span></span> <span data-ttu-id="e682f-147">Por exemplo, `System.Windows.Forms.Control` gera um `TextChanged` evento após o valor do seu `Text` propriedade foi alterada.</span><span class="sxs-lookup"><span data-stu-id="e682f-147">For example, `System.Windows.Forms.Control` raises a `TextChanged` event after the value of its `Text` property has changed.</span></span>  
  
 <span data-ttu-id="e682f-148">**✓ CONSIDERE** gerando eventos de notificação quando valores de propriedade em APIs de alto nível (geralmente designer componentes) são modificados de alteração.</span><span class="sxs-lookup"><span data-stu-id="e682f-148">**✓ CONSIDER** raising change notification events when property values in high-level APIs (usually designer components) are modified.</span></span>  
  
 <span data-ttu-id="e682f-149">Se houver um cenário válido para um usuário a saber quando uma propriedade de um objeto está sendo alterado, o objeto deve gerar um evento de notificação de alteração para a propriedade.</span><span class="sxs-lookup"><span data-stu-id="e682f-149">If there is a good scenario for a user to know when a property of an object is changing, the object should raise a change notification event for the property.</span></span>  
  
 <span data-ttu-id="e682f-150">No entanto, é improvável que vale a sobrecarga para gerar eventos para APIs de baixo nível, como tipos base ou coleções.</span><span class="sxs-lookup"><span data-stu-id="e682f-150">However, it is unlikely to be worth the overhead to raise such events for low-level APIs such as base types or collections.</span></span> <span data-ttu-id="e682f-151">Por exemplo, <xref:System.Collections.Generic.List%601> não geraria tais eventos quando um novo item é adicionado à lista e o `Count` alterações de propriedade.</span><span class="sxs-lookup"><span data-stu-id="e682f-151">For example, <xref:System.Collections.Generic.List%601> would not raise such events when a new item is added to the list and the `Count` property changes.</span></span>  
  
 <span data-ttu-id="e682f-152">**✓ CONSIDERE** gerando eventos de notificação quando o valor de uma propriedade é alterada por meio de forças externas de alteração.</span><span class="sxs-lookup"><span data-stu-id="e682f-152">**✓ CONSIDER** raising change notification events when the value of a property changes via external forces.</span></span>  
  
 <span data-ttu-id="e682f-153">Se um valor de propriedade for alterado por meio de alguns force externo (de forma diferente ao chamar métodos no objeto), aumentar os eventos indicam para o desenvolvedor que o valor está sendo alterada e foi alterado.</span><span class="sxs-lookup"><span data-stu-id="e682f-153">If a property value changes via some external force (in a way other than by calling methods on the object), raise events indicate to the developer that the value is changing and has changed.</span></span> <span data-ttu-id="e682f-154">Um bom exemplo é o `Text` propriedade de um controle de caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="e682f-154">A good example is the `Text` property of a text box control.</span></span> <span data-ttu-id="e682f-155">Quando o usuário digita texto em uma `TextBox`, o valor da propriedade alterada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e682f-155">When the user types text in a `TextBox`, the property value automatically changes.</span></span>  
  
 <span data-ttu-id="e682f-156">*Partes © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*</span><span class="sxs-lookup"><span data-stu-id="e682f-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e682f-157">*Reimpressas pela permissão de Pearson educação, Inc. de [diretrizes de Design do Framework: convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2ª edição](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008, Addison-Wesley Professional como parte da série de desenvolvimento do Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e682f-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e682f-158">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e682f-158">See Also</span></span>  
 [<span data-ttu-id="e682f-159">Diretrizes de Design de membro</span><span class="sxs-lookup"><span data-stu-id="e682f-159">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="e682f-160">Diretrizes de design do Framework</span><span class="sxs-lookup"><span data-stu-id="e682f-160">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)