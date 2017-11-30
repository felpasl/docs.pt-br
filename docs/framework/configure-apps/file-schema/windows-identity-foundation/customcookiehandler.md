---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: df95e8d47d6a19e4fd488fa14bc771bc2c2b56b7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="cd081-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="cd081-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="cd081-103">Define o tipo de manipulador de cookie personalizado.</span><span class="sxs-lookup"><span data-stu-id="cd081-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="cd081-104">Esse elemento só pode estar presente se a `mode` atributo o `<cookieHandler>` elemento é "Custom".</span><span class="sxs-lookup"><span data-stu-id="cd081-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="cd081-105">O tipo personalizado deve ser derivado de <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="cd081-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="cd081-106">\<System ></span><span class="sxs-lookup"><span data-stu-id="cd081-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="cd081-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cd081-107">\<federationConfiguration></span></span>  
<span data-ttu-id="cd081-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="cd081-108">\<cookieHandler></span></span>  
<span data-ttu-id="cd081-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="cd081-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd081-110">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cd081-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd081-111">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="cd081-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cd081-112">As seções a seguir descrevem atributos, elementos filho e elementos pai.</span><span class="sxs-lookup"><span data-stu-id="cd081-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd081-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cd081-113">Attributes</span></span>  
  
|<span data-ttu-id="cd081-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="cd081-114">Attribute</span></span>|<span data-ttu-id="cd081-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd081-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd081-116">tipo</span><span class="sxs-lookup"><span data-stu-id="cd081-116">type</span></span>|<span data-ttu-id="cd081-117">Especifica um tipo personalizado que deriva de <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="cd081-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="cd081-118">Para obter mais informações sobre como especificar o `type` de atributo, consulte [referências de tipo personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="cd081-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd081-119">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="cd081-119">Child Elements</span></span>  
 <span data-ttu-id="cd081-120">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cd081-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd081-121">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="cd081-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cd081-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="cd081-122">Element</span></span>|<span data-ttu-id="cd081-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="cd081-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd081-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="cd081-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="cd081-125">Configura o <xref:System.IdentityModel.Services.CookieHandler> que o <xref:System.IdentityModel.Services.SessionAuthenticationModule> usa para ler e gravar cookies.</span><span class="sxs-lookup"><span data-stu-id="cd081-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd081-126">Comentários</span><span class="sxs-lookup"><span data-stu-id="cd081-126">Remarks</span></span>  
 <span data-ttu-id="cd081-127">Quando você especificar um manipulador personalizado de cookie, definindo o `mode` atributo do `<cookieHandler>` elemento como "Custom", você deve especificar o tipo do manipulador de cookie personalizado, incluindo um `<customCookieHandler>` elemento filho que faz referência ao tipo de manipulador de cookie.</span><span class="sxs-lookup"><span data-stu-id="cd081-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="cd081-128">Esse elemento não pode ser especificado quando o `mode` atributo é definido como "Em partes" ou "Padrão".</span><span class="sxs-lookup"><span data-stu-id="cd081-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="cd081-129">Manipuladores de cookie personalizado devem derivar do <xref:System.IdentityModel.Services.CookieHandler> classe.</span><span class="sxs-lookup"><span data-stu-id="cd081-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="cd081-130">O `<customCookieHandler>` elemento é representado pela <xref:System.IdentityModel.Configuration.CustomTypeElement> classe.</span><span class="sxs-lookup"><span data-stu-id="cd081-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd081-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cd081-131">Example</span></span>  
 <span data-ttu-id="cd081-132">O exemplo a seguir configura o SAM para usar um manipulador personalizado de cookie do tipo `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="cd081-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd081-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="cd081-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>