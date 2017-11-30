---
title: '&lt;certificado&gt; do &lt;elemento&gt; clientCertificate'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bef4067d0fa74aa90841040ca5e6b3ea22f1e499
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-of-ltclientcertificategt-element"></a><span data-ttu-id="11424-102">&lt;certificado&gt; do &lt;elemento&gt; clientCertificate</span><span class="sxs-lookup"><span data-stu-id="11424-102">&lt;certificate&gt; of &lt;clientCertificate&gt; Element</span></span>
<span data-ttu-id="11424-103">Especifica um x. 509 certificado usado para assinar e criptografar mensagens.</span><span class="sxs-lookup"><span data-stu-id="11424-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
 <span data-ttu-id="11424-104">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="11424-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="11424-105">\<comportamentos ></span><span class="sxs-lookup"><span data-stu-id="11424-105">\<behaviors></span></span>  
<span data-ttu-id="11424-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="11424-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="11424-107">\<comportamento ></span><span class="sxs-lookup"><span data-stu-id="11424-107">\<behavior></span></span>  
<span data-ttu-id="11424-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="11424-108">\<serviceCredentials></span></span>  
<span data-ttu-id="11424-109">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="11424-109">\<clientCertificate></span></span>  
<span data-ttu-id="11424-110">\<certificado ></span><span class="sxs-lookup"><span data-stu-id="11424-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11424-111">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="11424-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="11424-112">Atributos e elementos</span><span class="sxs-lookup"><span data-stu-id="11424-112">Attributes and Elements</span></span>  
 <span data-ttu-id="11424-113">As seções a seguir descrevem os elementos pai de atributos e elementos filho</span><span class="sxs-lookup"><span data-stu-id="11424-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="11424-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="11424-114">Attributes</span></span>  
  
|<span data-ttu-id="11424-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="11424-115">Attribute</span></span>|<span data-ttu-id="11424-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="11424-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="11424-117">Uma cadeia de caracteres que contém o valor para pesquisar no repositório de certificados x. 509.</span><span class="sxs-lookup"><span data-stu-id="11424-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="11424-118">O tipo contido no atributo deve satisfazer os requisitos do X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="11424-118">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="11424-119">O padrão é uma cadeia de caracteres vazia.</span><span class="sxs-lookup"><span data-stu-id="11424-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="11424-120">Especifica o local do repositório de certificados x. 509 que o cliente usa para validar o certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="11424-120">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="11424-121">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="11424-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="11424-122">-LocalMachine: o repositório de certificados atribuído ao computador local.</span><span class="sxs-lookup"><span data-stu-id="11424-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="11424-123">-CurrentUser: o repositório de certificados atribuído ao usuário atual.</span><span class="sxs-lookup"><span data-stu-id="11424-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="11424-124">O padrão é LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="11424-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="11424-125">Especifica o nome do repositório de certificados X.509 a ser aberto.</span><span class="sxs-lookup"><span data-stu-id="11424-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="11424-126">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="11424-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="11424-127">-Catálogo de endereços: O repositório de certificados para outros usuários.</span><span class="sxs-lookup"><span data-stu-id="11424-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="11424-128">-AuthRoot: Repositório de autoridades de certificação de terceiros (ACS) do certificado.</span><span class="sxs-lookup"><span data-stu-id="11424-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="11424-129">-CertificationAuthority: O repositório de certificados para autoridades de certificação intermediárias (CAs).</span><span class="sxs-lookup"><span data-stu-id="11424-129">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="11424-130">-Proibido: Repositório de certificados revogados de certificados.</span><span class="sxs-lookup"><span data-stu-id="11424-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="11424-131">-My: Repositório de certificados pessoais do certificado.</span><span class="sxs-lookup"><span data-stu-id="11424-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="11424-132">-Raiz: Repositório de certificados (autoridades de certificação de raiz confiável).</span><span class="sxs-lookup"><span data-stu-id="11424-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="11424-133">-TrustedPeople: Repositório de certificados pessoas confiáveis diretamente e recursos.</span><span class="sxs-lookup"><span data-stu-id="11424-133">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="11424-134">-TrustedPublisher: Repositório de certificados para editores diretamente confiáveis.</span><span class="sxs-lookup"><span data-stu-id="11424-134">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="11424-135">O padrão é meu.</span><span class="sxs-lookup"><span data-stu-id="11424-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="11424-136">Define o tipo de pesquisa x. 509 a ser executado.</span><span class="sxs-lookup"><span data-stu-id="11424-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="11424-137">Os valores válidos incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="11424-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="11424-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="11424-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="11424-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="11424-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="11424-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="11424-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="11424-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="11424-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="11424-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="11424-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="11424-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="11424-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="11424-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="11424-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="11424-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="11424-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="11424-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="11424-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="11424-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="11424-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="11424-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="11424-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="11424-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="11424-149">-   FindByExtension</span></span><br /><span data-ttu-id="11424-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="11424-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="11424-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="11424-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="11424-152">O tipo contido o `findValue` atributo deve satisfazer os requisitos do X509FindType especificado.</span><span class="sxs-lookup"><span data-stu-id="11424-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="11424-153">O valor padrão é FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="11424-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="11424-154">Elementos filho</span><span class="sxs-lookup"><span data-stu-id="11424-154">Child Elements</span></span>  
 <span data-ttu-id="11424-155">nenhuma.</span><span class="sxs-lookup"><span data-stu-id="11424-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="11424-156">Elementos pai</span><span class="sxs-lookup"><span data-stu-id="11424-156">Parent Elements</span></span>  
  
|<span data-ttu-id="11424-157">Elemento</span><span class="sxs-lookup"><span data-stu-id="11424-157">Element</span></span>|<span data-ttu-id="11424-158">Descrição</span><span class="sxs-lookup"><span data-stu-id="11424-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="11424-159">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="11424-159">\<clientCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="11424-160">Comentários</span><span class="sxs-lookup"><span data-stu-id="11424-160">Remarks</span></span>  
 <span data-ttu-id="11424-161">O `<certificate>` elemento é usado quando o serviço deve ter o certificado do cliente com antecedência para comunicação segura com o cliente.</span><span class="sxs-lookup"><span data-stu-id="11424-161">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="11424-162">Isso ocorre ao usar o padrão de comunicação duplex.</span><span class="sxs-lookup"><span data-stu-id="11424-162">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="11424-163">No padrão de solicitação/resposta mais comum, o cliente inclui o seu certificado na solicitação, o serviço usa para criptografar e assinar sua resposta ao cliente.</span><span class="sxs-lookup"><span data-stu-id="11424-163">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="11424-164">No padrão de comunicação duplex, no entanto, o serviço não tem uma solicitação do cliente e, portanto, é necessário que o certificado do cliente com antecedência para proteger a mensagem ao cliente.</span><span class="sxs-lookup"><span data-stu-id="11424-164">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="11424-165">Portanto você deve obter o certificado do cliente em uma negociação fora de banda e especificar o certificado usando esse elemento.</span><span class="sxs-lookup"><span data-stu-id="11424-165">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="11424-166">Para obter mais informações sobre serviços de duplex, consulte [como: criar um contrato Duplex](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="11424-166">For more information about duplex services, see [How to: Create a Duplex Contract](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="11424-167">Exemplo</span><span class="sxs-lookup"><span data-stu-id="11424-167">Example</span></span>  
 <span data-ttu-id="11424-168">O código a seguir especifica como encontrar adequados certificado x. 509 e uma validação personalizada digite o `<authentication>` elemento.</span><span class="sxs-lookup"><span data-stu-id="11424-168">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="11424-169">Consulte também</span><span class="sxs-lookup"><span data-stu-id="11424-169">See Also</span></span>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>  
 [<span data-ttu-id="11424-170">Comportamentos de segurança</span><span class="sxs-lookup"><span data-stu-id="11424-170">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="11424-171">Como: criar um serviço que utiliza um validador de certificado personalizado</span><span class="sxs-lookup"><span data-stu-id="11424-171">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="11424-172">Trabalhar com certificados</span><span class="sxs-lookup"><span data-stu-id="11424-172">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)