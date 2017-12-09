---
title: "Como criar um fornecedor de token de segurança personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0bf616b1af46c62166b0430c1b67b3a97f0613ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="3d0c8-102">Como criar um fornecedor de token de segurança personalizado</span><span class="sxs-lookup"><span data-stu-id="3d0c8-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="3d0c8-103">Este tópico mostra como criar novos tipos de token com um provedor de token de segurança personalizada e como integrar o provedor de um Gerenciador de token de segurança personalizada.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d0c8-104">Criar um provedor de token personalizado se os tokens fornecidos pelo sistema encontrado no <xref:System.IdentityModel.Tokens> namespace não correspondam aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="3d0c8-105">O provedor de token de segurança cria uma representação de token de segurança com base nas informações de credenciais de cliente ou serviço.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="3d0c8-106">Para usar o provedor de token de segurança personalizada no [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] segurança, você deve criar credenciais personalizadas e implementações de Gerenciador de token de segurança.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-106">To use the custom security token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="3d0c8-107">Para obter mais informações sobre credenciais personalizadas e Gerenciador de token de segurança, consulte o [passo a passo: criação de cliente personalizadas e as credenciais de serviço](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="3d0c8-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="3d0c8-108">Para obter mais informações sobre credenciais, símbolo manager, o provedor e o autenticador de classes de segurança, consulte o [arquitetura de segurança](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span><span class="sxs-lookup"><span data-stu-id="3d0c8-108">For more information about credentials, security token manager, provider and authenticator classes, see the [Security Architecture](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="3d0c8-109">Para criar um provedor de token de segurança personalizada</span><span class="sxs-lookup"><span data-stu-id="3d0c8-109">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="3d0c8-110">Definir uma nova classe que deriva de <xref:System.IdentityModel.Selectors.SecurityTokenProvider> classe.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="3d0c8-111">Implementar o método de <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> .</span><span class="sxs-lookup"><span data-stu-id="3d0c8-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="3d0c8-112">O método é responsável por criar e retornar uma instância do token de segurança.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="3d0c8-113">O exemplo a seguir cria uma classe denominada `MySecurityTokenProvider`e substitui o <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> método para retornar uma instância do <xref:System.IdentityModel.Tokens.X509SecurityToken> classe.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="3d0c8-114">O construtor de classe requer uma instância do <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> classe.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="3d0c8-115">Para integrar um provedor de token de segurança personalizada com um Gerenciador de token de segurança personalizadas</span><span class="sxs-lookup"><span data-stu-id="3d0c8-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="3d0c8-116">Definir uma nova classe que deriva de <xref:System.IdentityModel.Selectors.SecurityTokenManager> classe.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="3d0c8-117">(O exemplo a seguir é derivado a <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> classe que deriva de <xref:System.IdentityModel.Selectors.SecurityTokenManager> classe.)</span><span class="sxs-lookup"><span data-stu-id="3d0c8-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="3d0c8-118">Substituir o <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> método se já não é substituída.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="3d0c8-119">O <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> método é responsável por retornar uma instância do <xref:System.IdentityModel.Selectors.SecurityTokenProvider> classe apropriado para o <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parâmetro passado para o método pelo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] estrutura de segurança.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework.</span></span> <span data-ttu-id="3d0c8-120">Modifique o método para retornar a implementação de provedor de token de segurança personalizado (criada no procedimento anterior) quando o método é chamado com um parâmetro de token de segurança apropriado.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="3d0c8-121">Para obter mais informações sobre o Gerenciador de token de segurança, consulte o [passo a passo: Criando personalizado cliente e credenciais de serviço](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="3d0c8-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="3d0c8-122">Adicionar lógica personalizada para o método para habilitá-lo retornar o provedor de token de segurança personalizada com base no <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parâmetro.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="3d0c8-123">O exemplo a seguir retorna o provedor de token de segurança personalizada, se o token requisitos forem atendidos.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="3d0c8-124">Os requisitos incluem um token de segurança x. 509 e a direção da mensagem (que o token é usado para a saída de mensagem).</span><span class="sxs-lookup"><span data-stu-id="3d0c8-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="3d0c8-125">Para todos os outros casos, o código chama a classe base para manter o comportamento fornecido pelo sistema para outros requisitos de token de segurança.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="3d0c8-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3d0c8-126">Example</span></span>  
 <span data-ttu-id="3d0c8-127">A seguir mostra uma completa <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementação junto com um correspondente <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementação.</span><span class="sxs-lookup"><span data-stu-id="3d0c8-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="3d0c8-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3d0c8-128">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [<span data-ttu-id="3d0c8-129">Passo a passo: Criando credenciais de serviço e cliente personalizados</span><span class="sxs-lookup"><span data-stu-id="3d0c8-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="3d0c8-130">Como: criar um autenticador de Token de segurança personalizadas</span><span class="sxs-lookup"><span data-stu-id="3d0c8-130">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="3d0c8-131">Arquitetura de segurança</span><span class="sxs-lookup"><span data-stu-id="3d0c8-131">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)