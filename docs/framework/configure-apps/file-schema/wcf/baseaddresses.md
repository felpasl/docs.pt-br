---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: dc4b31e729f9037da101bdf3e6cde28e91b1a070
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277011"
---
# <a name="baseaddresses"></a>\<baseAddresses>
Representa uma coleção de `baseAddress` elementos, que são os endereços base para um host de serviço em um ambiente auto-hospedado. Se um endereço base estiver presente, os pontos de extremidade podem ser configurados com endereços em relação ao endereço base.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
\<host>  
\<baseAddresses>  
  
## <a name="syntax"></a>Sintaxe  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a>Tipo  
 `Type`  
  
## <a name="attributes-and-elements"></a>Atributos e elementos  
 As seções a seguir descrevem atributos, elementos filho e elementos pai.  
  
### <a name="attributes"></a>Atributos  
 nenhuma.  
  
### <a name="child-elements"></a>Elementos filho  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|Um elemento de configuração que especifica os endereços base usados pelo host de serviço.|  
  
### <a name="parent-elements"></a>Elementos pai  
  
|Elemento|Descrição|  
|-------------|-----------------|  
|[\<host>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Um elemento de configuração que especifica as configurações para um host de serviço.|  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [Hospedagem](../../../../../docs/framework/wcf/feature-details/hosting.md)
