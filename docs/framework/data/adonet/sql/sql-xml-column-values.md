---
title: Valores de coluna de XML do SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 1cd6962a02a50ecd9f9b634148eeb38ad0a45e05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664038"
---
# <a name="sql-xml-column-values"></a>Valores de coluna de XML do SQL
SQL Server oferece suporte a `xml` tipo de dados, e os desenvolvedores podem recuperar conjuntos de resultados, incluindo esse tipo usando o comportamento padrão da <xref:System.Data.SqlClient.SqlCommand> classe. Uma `xml` coluna pode ser recuperada, assim como qualquer coluna é recuperada (em um <xref:System.Data.SqlClient.SqlDataReader>, por exemplo), mas se você quiser trabalhar com o conteúdo da coluna como XML, você deve usar um <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Exemplo  
 O aplicativo de console a seguir seleciona duas linhas, cada uma contendo uma `xml` coluna, do **Sales** na tabela a **AdventureWorks** banco de dados a um <xref:System.Data.SqlClient.SqlDataReader> instância. Para cada linha, o valor da `xml` coluna é lido usando o <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> método <xref:System.Data.SqlClient.SqlDataReader>. O valor é armazenado em um <xref:System.Xml.XmlReader>. Observe que você deve usar <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> em vez de <xref:System.Data.IDataRecord.GetValue%2A> método se você quiser definir o conteúdo um <xref:System.Data.SqlTypes.SqlXml> variável; <xref:System.Data.IDataRecord.GetValue%2A> retorna o valor da `xml` coluna como uma cadeia de caracteres.  
  
> [!NOTE]
>  O **AdventureWorks** banco de dados de exemplo não é instalado por padrão quando você instala o SQL Server. Você pode instalá-lo executando a instalação do SQL Server.  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Data.SqlTypes.SqlXml>
- [Dados XML no SQL Server](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)
- [ADO.NET Managed Providers and DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917) (Central de desenvolvedores do DataSet e de provedores gerenciados do ADO.NET)
