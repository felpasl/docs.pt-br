---
title: Método IMetaDataImport::GetCustomAttributeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4619d5a1444d42c6f3ac43306fbd979a6a70f12b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54672169"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>Método IMetaDataImport::GetCustomAttributeProps
Obtém o valor do atributo personalizado, dado seu token de metadados.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `cv`  
 [in] Um token de metadados que representa o atributo personalizado a ser recuperado.  
  
 `ptkObj`  
 [out, opcional] Um token de metadados que representa o objeto que modifica o atributo personalizado. Esse valor pode ser qualquer tipo de token de metadados, exceto `mdCustomAttribute`.  
  
 `ptkType`  
 [out, opcional] Uma `mdMethodDef` ou `mdMemberRef` metadados token representando o <xref:System.Type> do atributo personalizado retornado.  
  
 `ppBlob`  
 [out, opcional] Um ponteiro para uma matriz de dados que é o valor do atributo personalizado.  
  
 `pcbSize`  
 [out, opcional] O tamanho em bytes dos dados retornados em *`ppBlob`.  
  
## <a name="remarks"></a>Comentários  
 Um atributo personalizado é armazenado como uma matriz de dados, o formato que é compreendido pelo mecanismo de metadados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** Cor.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Interface IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interface IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
