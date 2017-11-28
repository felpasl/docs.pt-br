---
title: "Consulte expressões (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8b30deea78efe275ccaf6beabafb16a84357ba26
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="query-expressions-entity-sql"></a>Consulte expressões (Entity SQL)
Uma expressão de consulta combina muitos diferentes operadores de consulta em uma única sintaxe. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]fornece vários tipos de expressões, incluindo o seguinte: [literais](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [parâmetros](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [variáveis](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), operadores, [funções](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), operadores de conjunto e assim por diante. Para obter mais informações, consulte [referência de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md).  
  
## <a name="clauses"></a>Cláusulas  
 Uma expressão de consulta é composta de uma série de cláusulas que operações sucessivas aplicam a uma coleção de objetos. Eles se baseiam nas mesmas cláusulas encontradas no padrão de uma instrução select SQL: [selecione](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [onde](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [Ter](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), e [ORDENAR por](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md).  
  
## <a name="scope"></a>Escopo  
 Nomes definidos na cláusula são apresentados no escopo por ordem de aparência, da esquerda para a direita. Na lista JOIN, as expressões podem referir-se nomes definidos anteriormente na lista. As propriedades públicas de elementos identificadas na cláusula não são adicionadas ao escopo: Sempre devem ser referenciados com o nome qualificado alias-. Normalmente, todas as partes da expressão selecionar são considerados dentro do escopo.  
  
## <a name="see-also"></a>Consulte também  
 [Referência de Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)