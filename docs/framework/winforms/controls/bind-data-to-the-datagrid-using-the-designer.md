---
title: 'Como: Associar dados ao controle DataGridView do Windows Forms usando o Designer'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
ms.openlocfilehash: 51f190618c71731aad722b93562a01a4dc7b9b34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558209"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a>Como: Associar dados ao controle DataGridView do Windows Forms usando o Designer
Você pode usar o designer para conectar-se um <xref:System.Windows.Forms.DataGridView> controle a fontes de dados de diferentes variedades, incluindo bancos de dados, objetos de negócios ou serviços da Web. Quando você associa o controle a uma fonte de dados usando o designer, o controle é automaticamente associado a um <xref:System.Windows.Forms.BindingSource> componente que representa a fonte de dados. Além disso, as colunas são automaticamente geradas no controle para coincidir com as informações de esquema fornecidas pela fonte de dados.  
  
 Depois que as colunas tiverem sido geradas, você poderá modificá-las para atender às suas necessidades. Por exemplo, você pode remover ou ocultar colunas que você não queira exibir, pode reorganizar as colunas ou pode modificar os tipos de coluna. Para obter mais informações sobre como modificar colunas, consulte os tópicos listados na seção Consulte também.  
  
 Você também pode associar vários <xref:System.Windows.Forms.DataGridView> controles tabelas relacionadas para criar relações de mestre/detalhes. Nessa configuração, um controle exibe uma tabela pai e outro controle exibe somente as linhas de uma tabela filho que estão relacionadas à linha atual na tabela pai. Para obter mais informações, confira [Como: Exibir relacionados a dados em um Windows Forms Application](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).  
  
 O procedimento a seguir exige um **aplicativo do Windows** projeto com um formulário que contém um <xref:System.Windows.Forms.DataGridView> controle ou dois controles para um relacionamento mestre/detalhes. Para obter informações sobre como iniciar um projeto desse tipo, consulte [como: Criar um projeto de aplicativo do Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [como: Adicionar controles ao Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  As caixas de diálogo e os comandos de menu que você vê podem ser diferentes dos descritos na Ajuda, dependendo da sua edição ou das configurações ativas. Para alterar as configurações, escolha **Importar e Exportar Configurações** no menu **Ferramentas**. Para obter mais informações, confira [Personalizar o IDE do Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-bind-the-control-to-a-data-source"></a>Para associar o controle a uma fonte de dados  
  
1.  Clique no glifo de marca inteligente (![glifo de Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) no canto superior direito do <xref:System.Windows.Forms.DataGridView> controle.  
  
2.  Clique na seta suspensa para a opção **Escolher Fonte de Dados**.  
  
3.  Se seu projeto ainda não tiver uma fonte de dados, clique em **Adicionar Fonte de Dados do Projeto** e siga as etapas indicadas pelo assistente.  
  
     Para obter mais informações, consulte [Assistente de Configuração da Fonte de Dados](https://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f). A nova fonte de dados aparecerá na janela suspensa **Escolher Fonte de Dados**. Se a nova fonte de dados contiver apenas um membro, como uma única tabela de banco de dados, o controle será associado automaticamente a esse membro. Do contrário, continue para a próxima etapa.  
  
4.  Expanda os nós **Outras Fontes de Dados** e **Fontes de Dados do Projeto** se eles ainda não tiverem sido expandidos e, em seguida, selecione a fonte de dados à qual associar o controle.  
  
5.  Se sua fonte de dados contém mais de um membro, por exemplo, se você criou um <xref:System.Data.DataSet?displayProperty=nameWithType> que contenha várias tabelas, expanda a fonte de dados e, em seguida, selecione o membro específico para associar a.  
  
6.  Para criar uma relação mestre/detalhes, no **Choose Data Source** janela suspensa por um segundo <xref:System.Windows.Forms.DataGridView> controlar, expanda o <xref:System.Windows.Forms.BindingSource> criado para a tabela pai e, em seguida, selecione a tabela filho relacionada na lista mostrado.  
  
    > [!NOTE]
    >  Se o projeto já tiver uma fonte de dados, você também poderá usar a janela **Fontes de Dados** para criar um formulário de dados. Para obter mais informações, consulte [Janela de Fontes de Dados](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- [Como: Conectar a dados em um banco de dados](https://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)
- [Como: Adicionar e remover colunas no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [Como: Alterar a ordem das colunas no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)
- [Como: Alterar o tipo de uma coluna de DataGridView dos Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)
- [Como: Congelar colunas no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)
- [Como: Ocultar colunas no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)
- [Como: Tornar colunas somente leitura no controle DataGridView do Windows Forms usando o Designer](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)
- [Como: Criar um projeto de aplicativo do Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)
- [Como: Adicionar controles ao Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
- [Janela Fontes de Dados](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
- [Como: Exibir dados relacionados em um aplicativo do Windows Forms](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
