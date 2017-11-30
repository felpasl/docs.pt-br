---
title: Inferindo colunas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ba06bce55db53de1da1c07d2a6451d5664fa23bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-columns"></a><span data-ttu-id="2c478-102">Inferindo colunas</span><span class="sxs-lookup"><span data-stu-id="2c478-102">Inferring Columns</span></span>
<span data-ttu-id="2c478-103">Depois que o ADO.NET determinou de um documento XML que elementos inferir como tabelas para um <xref:System.Data.DataSet>, ele infere, em seguida, as colunas para as tabelas.</span><span class="sxs-lookup"><span data-stu-id="2c478-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="2c478-104">O ADO.NET 2.0 introduziu um novo mecanismo de inferência de esquema que infere um tipo de dados fortemente tipados para cada **simpleType** elemento.</span><span class="sxs-lookup"><span data-stu-id="2c478-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="2c478-105">Nas versões anteriores, o tipo de dados de um deduzido **simpleType** elemento era sempre **xsd: string**.</span><span class="sxs-lookup"><span data-stu-id="2c478-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="2c478-106">Migração e compatibilidade com versões anteriores</span><span class="sxs-lookup"><span data-stu-id="2c478-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="2c478-107">O **ReadXml** método usa um argumento de tipo **InferSchema**.</span><span class="sxs-lookup"><span data-stu-id="2c478-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="2c478-108">Esse argumento permite que você especifique o comportamento de inferência compatível com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="2c478-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="2c478-109">Os valores disponíveis para o **InferSchema** enumeração são mostrados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2c478-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="2c478-110">Fornece compatibilidade com versões anteriores, sempre inferir um tipo simples como <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="2c478-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="2c478-111">Infere um tipo de dados fortemente tipados.</span><span class="sxs-lookup"><span data-stu-id="2c478-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="2c478-112">Gera uma exceção se usado com um <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="2c478-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="2c478-113">Ignora qualquer esquema embutido e carrega os dados no esquema <xref:System.Data.DataSet> existente.</span><span class="sxs-lookup"><span data-stu-id="2c478-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="2c478-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="2c478-114">Attributes</span></span>  
 <span data-ttu-id="2c478-115">Conforme definido em [inferindo tabelas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), um elemento com atributos será inferido como uma tabela.</span><span class="sxs-lookup"><span data-stu-id="2c478-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="2c478-116">Os atributos desse elemento, em seguida, serão inferidos como colunas para a tabela.</span><span class="sxs-lookup"><span data-stu-id="2c478-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="2c478-117">O **ColumnMapping** definirá a propriedade das colunas **MappingType.Attribute**, para garantir que os nomes de coluna serão gravados como atributos se o esquema será gravado no XML.</span><span class="sxs-lookup"><span data-stu-id="2c478-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="2c478-118">Os valores dos atributos são armazenados em uma linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="2c478-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="2c478-119">Por exemplo, considere o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="2c478-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2c478-120">O processo de inferência produzirá uma tabela chamada **Element1** com duas colunas, **attr1** e **attr2**.</span><span class="sxs-lookup"><span data-stu-id="2c478-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="2c478-121">O **ColumnMapping** definirá a propriedade de ambas as colunas **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="2c478-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="2c478-122">**Conjunto de dados:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2c478-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2c478-123">**Tabela:** Element1</span><span class="sxs-lookup"><span data-stu-id="2c478-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2c478-124">attr1</span><span class="sxs-lookup"><span data-stu-id="2c478-124">attr1</span></span>|<span data-ttu-id="2c478-125">attr2</span><span class="sxs-lookup"><span data-stu-id="2c478-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="2c478-126">value1</span><span class="sxs-lookup"><span data-stu-id="2c478-126">value1</span></span>|<span data-ttu-id="2c478-127">value2</span><span class="sxs-lookup"><span data-stu-id="2c478-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="2c478-128">Elementos sem atributos ou elementos filho</span><span class="sxs-lookup"><span data-stu-id="2c478-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="2c478-129">Se um elemento não tem elementos filhos ou atributos, ele será inferido como uma coluna.</span><span class="sxs-lookup"><span data-stu-id="2c478-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="2c478-130">O **ColumnMapping** definirá a propriedade da coluna **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="2c478-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="2c478-131">O texto para elementos filho é armazenado em uma linha na tabela.</span><span class="sxs-lookup"><span data-stu-id="2c478-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="2c478-132">Por exemplo, considere o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="2c478-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="2c478-133">O processo de inferência produzirá uma tabela chamada **Element1** com duas colunas, **ChildElement1** e **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="2c478-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="2c478-134">O **ColumnMapping** definirá a propriedade de ambas as colunas **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="2c478-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="2c478-135">**Conjunto de dados:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="2c478-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="2c478-136">**Tabela:** Element1</span><span class="sxs-lookup"><span data-stu-id="2c478-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="2c478-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="2c478-137">ChildElement1</span></span>|<span data-ttu-id="2c478-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="2c478-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="2c478-139">Texto1</span><span class="sxs-lookup"><span data-stu-id="2c478-139">Text1</span></span>|<span data-ttu-id="2c478-140">Texto2</span><span class="sxs-lookup"><span data-stu-id="2c478-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c478-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2c478-141">See Also</span></span>  
 [<span data-ttu-id="2c478-142">Inferindo estrutura relacional do conjunto de dados do XML</span><span class="sxs-lookup"><span data-stu-id="2c478-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="2c478-143">Carregar um conjunto de dados do XML</span><span class="sxs-lookup"><span data-stu-id="2c478-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="2c478-144">Carregando informações de esquema de conjunto de dados de XML</span><span class="sxs-lookup"><span data-stu-id="2c478-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 <span data-ttu-id="2c478-145">[Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md) (Usando XML em um DataSet)</span><span class="sxs-lookup"><span data-stu-id="2c478-145">[Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)</span></span>  
 <span data-ttu-id="2c478-146">[DataSets, DataTables, and DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md) (DataSets, DataTables e DataViews)</span><span class="sxs-lookup"><span data-stu-id="2c478-146">[DataSets, DataTables, and DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)</span></span>  
 <span data-ttu-id="2c478-147">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="2c478-147">[ADO.NET Managed Providers and DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)</span></span>