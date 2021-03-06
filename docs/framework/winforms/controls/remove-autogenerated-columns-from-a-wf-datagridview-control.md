---
title: 'Como: Remover colunas geradas automaticamente de um controle de DataGridView dos Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], removing columns
- columns [Windows Forms], removing
ms.assetid: 92e28d98-95a3-446c-9150-41b7c7e5be15
ms.openlocfilehash: 2baee857aa21b22b0d4db52bc48f8849b0ddad87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721052"
---
# <a name="how-to-remove-autogenerated-columns-from-a-windows-forms-datagridview-control"></a>Como: Remover colunas geradas automaticamente de um controle de DataGridView dos Windows Forms
Quando seu <xref:System.Windows.Forms.DataGridView> controle estiver definida para gerar automaticamente suas colunas com base nos dados da fonte de dados, você poderá omitir seletivamente determinadas colunas. Você pode fazer isso chamando o <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> método no <xref:System.Windows.Forms.DataGridView.Columns%2A> coleção. Como alternativa, você pode ocultar colunas de exibição, definindo o <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> propriedade para `false`. Essa técnica é útil quando você deseja exibir as colunas ocultas em determinadas condições ou quando você precisa acessar os dados nas colunas sem exibi-lo.  
  
### <a name="to-remove-autogenerated-columns"></a>Para remover colunas geradas automaticamente  
  
-   Chame o <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> método no <xref:System.Windows.Forms.DataGridView.Columns%2A> coleção.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#111)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#111)]  
  
### <a name="to-hide-autogenerated-columns"></a>Para ocultar colunas geradas automaticamente  
  
-   Defina a coluna <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> propriedade para `false`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#112)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#112)]  
  
## <a name="example"></a>Exemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#110)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#110)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Um <xref:System.Windows.Forms.DataGridView> controle chamado `dataGridView1` ligado a uma tabela que contém `Fax` e `CustomerID` colunas, como o `Customers` tabela no banco de dados de exemplo Northwind.  
  
-   Referências aos assemblies <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [Exibindo dados no controle DataGridView do Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)
