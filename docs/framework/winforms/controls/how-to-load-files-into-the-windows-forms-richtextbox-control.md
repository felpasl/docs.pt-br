---
title: Como carregar arquivos no controle RichTextBox dos Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ba0e2aec42fa3656b64140134efa27fe8e940e1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="eb40b-102">Como carregar arquivos no controle RichTextBox dos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb40b-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="eb40b-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> controle pode exibir um texto sem formatação, em texto sem formatação Unicode ou arquivo de formato de Rich Text (RTF).</span><span class="sxs-lookup"><span data-stu-id="eb40b-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="eb40b-104">Para fazer isso, chame o <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> método.</span><span class="sxs-lookup"><span data-stu-id="eb40b-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="eb40b-105">Você também pode usar o <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> método para carregar dados de um fluxo.</span><span class="sxs-lookup"><span data-stu-id="eb40b-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="eb40b-106">Para obter mais informações, consulte <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="eb40b-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="eb40b-107">Para carregar um Arquivo no controle RichTextBox</span><span class="sxs-lookup"><span data-stu-id="eb40b-107">To load a file into the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="eb40b-108">Determinar o caminho do arquivo a ser aberto usando o <xref:System.Windows.Forms.OpenFileDialog> componente.</span><span class="sxs-lookup"><span data-stu-id="eb40b-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="eb40b-109">Para obter uma visão geral, consulte [Visão geral do componente OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="eb40b-109">For an overview, see [OpenFileDialog Component Overview](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="eb40b-110">Chamar o <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> método o <xref:System.Windows.Forms.RichTextBox> controle, especificando o arquivo para carregar e, opcionalmente, um tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="eb40b-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="eb40b-111">No exemplo a seguir, o arquivo a ser carregado é obtido a <xref:System.Windows.Forms.OpenFileDialog> do componente <xref:System.Windows.Forms.FileDialog.FileName%2A> propriedade.</span><span class="sxs-lookup"><span data-stu-id="eb40b-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="eb40b-112">Se você chamar o método com um nome de arquivo como seu único argumento, o tipo de arquivo será considerado como RTF.</span><span class="sxs-lookup"><span data-stu-id="eb40b-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="eb40b-113">Para especificar outro tipo de arquivo, chame o método com um valor de <xref:System.Windows.Forms.RichTextBoxStreamType> enumeração como seu segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="eb40b-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="eb40b-114">No exemplo a seguir, o <xref:System.Windows.Forms.OpenFileDialog> componente é mostrado quando um botão é clicado.</span><span class="sxs-lookup"><span data-stu-id="eb40b-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="eb40b-115">O arquivo selecionado é aberto e exibido no <xref:System.Windows.Forms.RichTextBox> controle.</span><span class="sxs-lookup"><span data-stu-id="eb40b-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="eb40b-116">Este exemplo supõe que um formulário tem um botão, `btnOpenFile`.</span><span class="sxs-lookup"><span data-stu-id="eb40b-116">This example assumes a form has a button,`btnOpenFile`.</span></span>  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     <span data-ttu-id="eb40b-117">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Coloque o seguinte código no construtor de formulários para registrar o manipulador de eventos.</span><span class="sxs-lookup"><span data-stu-id="eb40b-117">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="eb40b-118">Para executar esse processo, seu assembly pode exigir um nível de privilégio concedido pela <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> classe.</span><span class="sxs-lookup"><span data-stu-id="eb40b-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="eb40b-119">Se você estiver executando em um contexto de confiança parcial, o processo poderá gerar uma exceção em razão dos privilégios insuficientes.</span><span class="sxs-lookup"><span data-stu-id="eb40b-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="eb40b-120">Para obter mais informações, consulte [Noções Básicas da Segurança de Acesso do Código](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="eb40b-120">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb40b-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="eb40b-121">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="eb40b-122">Controle RichTextBox</span><span class="sxs-lookup"><span data-stu-id="eb40b-122">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="eb40b-123">Controles a serem usados nos Windows Forms</span><span class="sxs-lookup"><span data-stu-id="eb40b-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)