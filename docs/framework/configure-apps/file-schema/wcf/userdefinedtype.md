---
title: <userDefinedType>
ms.date: 03/30/2017
ms.assetid: 0f70ec06-8249-4f0c-9f49-b4df59985fb8
ms.openlocfilehash: a69571f5d34c2f844662f3d70ca67a2fb8ed0291
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284681"
---
# <a name="userdefinedtype"></a>\<userDefinedType>
Representa um tipo definido pelo usuário (UDT) que deve ser incluído no contrato de serviço.  
  
 \<system.ServiceModel>  
\<comContracts>  
\<comContract>  
\<userDefinedTypes>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<comContracts>
  <comContract>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descrição|  
|---------------|-----------------|  
|`name`|Um atributo opcional que contém uma cadeia de caracteres que fornece o nome de tipo legível. Isso não é usado pelo tempo de execução, mas ajuda a distinguir os tipos de um leitor.|  
|`TypeDefID`|Uma cadeia de caracteres GUID que identifica o tipo UDT específico dentro da biblioteca de tipos registrada.|  
|`TypeLibID`|Uma cadeia de caracteres GUID que identifica a biblioteca de tipos registrada que define o tipo.|  
|`TypeLibVersion`|Uma cadeia de caracteres que identifica a versão da biblioteca de tipo que define o tipo.|  
  
### <a name="child-elements"></a>Elementos filho  
 nenhuma.  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|`userDefinedTypes`|Uma coleção de elementos `userDefinedType`.|  
  
## <a name="remarks"></a>Comentários  
 O tempo de execução de integração COM+ cria serviços inspecionando a biblioteca de tipos. Quando um componente COM+ contém métodos que passam uma VARIANTE, o sistema não pode determinar os tipos reais a serem passados antes do tempo de execução. Portanto, quando você tentar passar um usuário definido pelo tipo (UDT) dentro de uma VARIANTE, ele falhará porque não é um tipo conhecido para serialização.  
  
 Para contornar esse problema, você pode adicionar os UDTs ao arquivo de configuração para que eles possam ser incluídos como tipos conhecidos no contrato de serviço apropriado. Para fazer isso, você precisa que identificar exclusivamente o UDT e o contrato (s), ou seja, as interfaces COM original usam-o.  
  
 O exemplo a seguir demonstra como adicionar dois UDTs específicos para o <`userDefinedTypes`> seção do arquivo de configuração para essa finalidade.  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <userDefinedTypes>
      <userDefinedType name="CustomerType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{D129765C-F211-434e-825A-9A63198C41F2}">
      </userDefinedType>
      <userDefinedType name="AddressType"
                       typeLibID="{91DC728C-4F1A-45de-A9B6-B538E209CEA6}"
                       typeLibVersion="1.0"
                       typeDefID="{4616AE0D-687A-43B7-BC63-141AE3DFD099}">
      </userDefinedType>
    </userDefinedTypes>
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 Quando o serviço é inicializado, o integration runtime procura os tipos especificados e os adiciona à coleção de tipos conhecidos para os contratos especificados.  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Configuration.ComContractElement.UserDefinedTypes%2A>
- <xref:System.ServiceModel.Configuration.ComUdtElementCollection>
- <xref:System.ServiceModel.Configuration.ComUdtElement>
- [\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [Integração de aplicativos COM+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [Como: Definir as configurações de serviço COM+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
