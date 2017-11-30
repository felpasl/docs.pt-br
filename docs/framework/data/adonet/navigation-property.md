---
title: "propriedade de navegação"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1677ab1be071eeabd72b29c7ce61d01aaf6164a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="navigation-property"></a><span data-ttu-id="9e795-102">propriedade de navegação</span><span class="sxs-lookup"><span data-stu-id="9e795-102">navigation property</span></span>
<span data-ttu-id="9e795-103">Um *propriedade de navegação* é uma propriedade opcional em uma [tipo de entidade](../../../../docs/framework/data/adonet/entity-type.md) que permite a navegação de um [final](../../../../docs/framework/data/adonet/association-end.md) de um [associação](../../../../docs/framework/data/adonet/association-type.md) para a outra extremidade.</span><span class="sxs-lookup"><span data-stu-id="9e795-103">A *navigation property* is an optional property on an [entity type](../../../../docs/framework/data/adonet/entity-type.md) that allows for navigation from one [end](../../../../docs/framework/data/adonet/association-end.md) of an [association](../../../../docs/framework/data/adonet/association-type.md) to the other end.</span></span> <span data-ttu-id="9e795-104">Ao contrário de outras [propriedades](../../../../docs/framework/data/adonet/property.md), propriedades de navegação não contêm dados.</span><span class="sxs-lookup"><span data-stu-id="9e795-104">Unlike other [properties](../../../../docs/framework/data/adonet/property.md), navigation properties do not carry data.</span></span>  
  
 <span data-ttu-id="9e795-105">Uma definição de propriedade de navegação inclui o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9e795-105">A navigation property definition includes the following:</span></span>  
  
-   <span data-ttu-id="9e795-106">Um nome.</span><span class="sxs-lookup"><span data-stu-id="9e795-106">A name.</span></span> <span data-ttu-id="9e795-107">(Necessário)</span><span class="sxs-lookup"><span data-stu-id="9e795-107">(Required)</span></span>  
  
-   <span data-ttu-id="9e795-108">A associação que navega.</span><span class="sxs-lookup"><span data-stu-id="9e795-108">The association that it navigates.</span></span> <span data-ttu-id="9e795-109">(Necessário)</span><span class="sxs-lookup"><span data-stu-id="9e795-109">(Required)</span></span>  
  
-   <span data-ttu-id="9e795-110">Termina de associação que navega.</span><span class="sxs-lookup"><span data-stu-id="9e795-110">The ends of the association that it navigates.</span></span> <span data-ttu-id="9e795-111">(Necessário)</span><span class="sxs-lookup"><span data-stu-id="9e795-111">(Required)</span></span>  
  
 <span data-ttu-id="9e795-112">Observe que as propriedades de navegação são opcionais em ambos os tipos de entidade termina de uma associação.</span><span class="sxs-lookup"><span data-stu-id="9e795-112">Note that navigation properties are optional on both entity types at the ends of an association.</span></span> <span data-ttu-id="9e795-113">Se você definir uma propriedade de navegação em um tipo de entidade no final de uma associação, você não precisa definir uma propriedade de navegação no tipo de entidade no outro extremo de associação.</span><span class="sxs-lookup"><span data-stu-id="9e795-113">If you define a navigation property on one entity type at the end of an association, you do not have to define a navigation property on the entity type at the other end of the association.</span></span>  
  
 <span data-ttu-id="9e795-114">O tipo de dados de uma propriedade de navegação é determinado pelo [multiplicidade](../../../../docs/framework/data/adonet/association-end-multiplicity.md) do seu remote [end de associação](../../../../docs/framework/data/adonet/association-end.md).</span><span class="sxs-lookup"><span data-stu-id="9e795-114">The data type of a navigation property is determined by the [multiplicity](../../../../docs/framework/data/adonet/association-end-multiplicity.md) of its remote [association end](../../../../docs/framework/data/adonet/association-end.md).</span></span> <span data-ttu-id="9e795-115">Por exemplo, suponha uma propriedade de navegação, `OrdersNavProp`, existe em um tipo de entidade de `Customer` e navegar em um para muitos associação entre `Customer` e `Order`.</span><span class="sxs-lookup"><span data-stu-id="9e795-115">For example, suppose a navigation property, `OrdersNavProp`, exists on a `Customer` entity type and navigates a one-to-many association between `Customer` and `Order`.</span></span> <span data-ttu-id="9e795-116">Porque o fim remoto da associação para a propriedade de navegação tem a multiplicidade de muitos (*), seu tipo de dados é uma coleção (de `Order`).</span><span class="sxs-lookup"><span data-stu-id="9e795-116">Because the remote association end for the navigation property has multiplicity of many (*), its data type is a collection (of `Order`).</span></span> <span data-ttu-id="9e795-117">Da mesma forma, se uma propriedade de navegação, `CustomerNavProp`, existe no tipo de entidade de `Order` , seu tipo de dados deve ser `Customer`, porque a multiplicidade de extremidade remoto é um (1).</span><span class="sxs-lookup"><span data-stu-id="9e795-117">Similarly, if a navigation property, `CustomerNavProp`, exists on the `Order` entity type, its data type would be `Customer`, because the multiplicity of the remote end is one (1).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e795-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9e795-118">Example</span></span>  
 <span data-ttu-id="9e795-119">O diagrama a seguir mostra um modelo conceitual com três tipos de entidade: `Book`, `Publisher`, e `Author`.</span><span class="sxs-lookup"><span data-stu-id="9e795-119">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="9e795-120">As propriedades de navegação, `Publisher` e `Authors`, são definidas no tipo de entidade de livro.</span><span class="sxs-lookup"><span data-stu-id="9e795-120">Navigation properties, `Publisher` and `Authors`, are defined on the Book entity type.</span></span> <span data-ttu-id="9e795-121">A propriedade `Books` de navegação é definida no tipo de entidade do Publisher e tipo de entidade de `Author` .</span><span class="sxs-lookup"><span data-stu-id="9e795-121">Navigation property `Books` is defined on both the Publisher entity type and the `Author` entity type.</span></span>  
  
 <span data-ttu-id="9e795-122">![Modelo com propriedades de navegação](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span><span class="sxs-lookup"><span data-stu-id="9e795-122">![Model with Navigation Properties](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")</span></span>  
  
 <span data-ttu-id="9e795-123">O [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa uma linguagem específica de domínio (DSL) chamada linguagem de definição de esquema conceitual ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir modelos conceituais.</span><span class="sxs-lookup"><span data-stu-id="9e795-123">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="9e795-124">CSDL seguir define o tipo de entidade de `Book` mostrado no diagrama anterior:</span><span class="sxs-lookup"><span data-stu-id="9e795-124">The following CSDL defines the `Book` entity type shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 <span data-ttu-id="9e795-125">Observe que os atributos XML são usados para comunicar informações necessárias para definir uma propriedade de navegação: O atributo `Name` contém o nome da propriedade, `Relationship` contém o nome da associação que navega, e `FromRole` e `ToRole` contêm terminar a associação.</span><span class="sxs-lookup"><span data-stu-id="9e795-125">Note that XML attributes are used to communicate the information necessary to define a navigation property: The attribute `Name` contains the name of the property, `Relationship` contains the name of the association it navigates, and `FromRole` and `ToRole` contain the ends of the association.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e795-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9e795-126">See Also</span></span>  
 [<span data-ttu-id="9e795-127">Conceitos chave do modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="9e795-127">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="9e795-128">Modelo de dados de entidade</span><span class="sxs-lookup"><span data-stu-id="9e795-128">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)