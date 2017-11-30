---
title: "Usando configurações do aplicativo e configurações do usuário"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user settings [Windows Forms]
- application settings [Windows Forms], how-to topics
ms.assetid: 54682d3b-1cbf-4683-9351-012b8b4286b5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f9544b6af74608bd1b29db3250e887999ae3187f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="using-application-settings-and-user-settings"></a><span data-ttu-id="80c2e-102">Usando configurações do aplicativo e configurações do usuário</span><span class="sxs-lookup"><span data-stu-id="80c2e-102">Using Application Settings and User Settings</span></span>
<span data-ttu-id="80c2e-103">Ao começar com o .NET Framework 2.0, é possível criar e acessar valores mantidos entre as sessões de execução do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80c2e-103">Starting with the .NET Framework 2.0, you can create and access values that are persisted between application execution sessions.</span></span> <span data-ttu-id="80c2e-104">Esses valores são chamados de *configurações*.</span><span class="sxs-lookup"><span data-stu-id="80c2e-104">These values are called *settings*.</span></span> <span data-ttu-id="80c2e-105">Configurações podem representar preferências do usuário ou informações valiosas que o aplicativo precisar usar.</span><span class="sxs-lookup"><span data-stu-id="80c2e-105">Settings can represent user preferences, or valuable information the application needs to use.</span></span> <span data-ttu-id="80c2e-106">Por exemplo, é possível criar uma série de configurações que armazenam as preferências do usuário para o esquema de cores de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80c2e-106">For example, you might create a series of settings that store user preferences for the color scheme of an application.</span></span> <span data-ttu-id="80c2e-107">Ou, então, você pode armazenar a cadeia de conexão que especifica um banco de dados usado pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80c2e-107">Or you might store the connection string that specifies a database that your application uses.</span></span> <span data-ttu-id="80c2e-108">As configurações lhe permitem manter informações críticas ao aplicativo fora do código e criar perfis que armazenam as preferências dos usuários individualmente.</span><span class="sxs-lookup"><span data-stu-id="80c2e-108">Settings allow you to both persist information that is critical to the application outside the code, and to create profiles that store the preferences of individual users.</span></span>  
  
 <span data-ttu-id="80c2e-109">Os tópicos nesta seção descrevem como usar as configurações no tempo de design e tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="80c2e-109">The topics in this section describe how to use settings at design time and run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80c2e-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="80c2e-110">In This Section</span></span>  
 [<span data-ttu-id="80c2e-111">Como Criar uma Nova Configuração em Tempo de Design</span><span class="sxs-lookup"><span data-stu-id="80c2e-111">How To: Create a New Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)  
  
 <span data-ttu-id="80c2e-112">Explica como usar o Visual Studio para criar uma nova configuração para um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80c2e-112">Explains how to use Visual Studio to create a new setting for an application.</span></span>  
  
 [<span data-ttu-id="80c2e-113">Como Alterar o Valor de uma Configuração Existente em Tempo de Design</span><span class="sxs-lookup"><span data-stu-id="80c2e-113">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)  
  
 <span data-ttu-id="80c2e-114">Descreve como usar o Visual Studio para alterar o valor de uma configuração existente.</span><span class="sxs-lookup"><span data-stu-id="80c2e-114">Describes how to use Visual Studio to change the value of an existing setting.</span></span>  
  
 [<span data-ttu-id="80c2e-115">Como Alterar o Valor de uma Configuração entre Sessões do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="80c2e-115">How To: Change the Value of a Setting Between Application Sessions</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-a-setting-between-application-sessions.md)  
  
 <span data-ttu-id="80c2e-116">Detalha como alterar o valor de uma configuração em um aplicativo compilado entre sessões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="80c2e-116">Details how to change the value of a setting in a compiled application between application sessions.</span></span>  
  
 [<span data-ttu-id="80c2e-117">Como Ler Configurações em Tempo de Execução com C#</span><span class="sxs-lookup"><span data-stu-id="80c2e-117">How To: Read Settings at Run Time With C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="80c2e-118">Descreve como usar código para ler as configurações com c#.</span><span class="sxs-lookup"><span data-stu-id="80c2e-118">Describes how to use code to read settings with C#.</span></span>  
  
 [<span data-ttu-id="80c2e-119">Como Gravar Configurações do Usuário em Tempo de Execução com C#</span><span class="sxs-lookup"><span data-stu-id="80c2e-119">How To: Write User Settings at Run Time with C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
  
 <span data-ttu-id="80c2e-120">Explica como usar o código para gravar e salvar os valores das configurações do usuário com c#.</span><span class="sxs-lookup"><span data-stu-id="80c2e-120">Explains how to use code to write and save the values of user settings with C#.</span></span>  
  
 [<span data-ttu-id="80c2e-121">Como Adicionar Vários Conjuntos de Configurações a um Aplicativo em C#</span><span class="sxs-lookup"><span data-stu-id="80c2e-121">How To: Add Multiple Sets of Settings To Your Application in C#</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-multiple-sets-of-settings-to-your-application-in-csharp.md)  
  
 <span data-ttu-id="80c2e-122">Detalha como adicionar vários conjuntos de configurações a um aplicativo em C#.</span><span class="sxs-lookup"><span data-stu-id="80c2e-122">Details how to add multiple sets of settings to an application with C#.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c2e-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="80c2e-123">See Also</span></span>  
 [<span data-ttu-id="80c2e-124">Configurações do Aplicativo para o Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80c2e-124">Application Settings for Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/application-settings-for-windows-forms.md)