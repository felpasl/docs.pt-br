---
title: Método ISymUnmanagedWriter::DefineDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineDocument
helpviewer_keywords:
- ISymUnmanagedWriter::DefineDocument method [.NET Framework debugging]
- DefineDocument method [.NET Framework debugging]
ms.assetid: c3bf15b0-3250-4bbe-b9b5-c5d695289b6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d1c214918b4a41ac989a3804c9146c4a54c5909f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738203"
---
# <a name="isymunmanagedwriterdefinedocument-method"></a>Método ISymUnmanagedWriter::DefineDocument
Define um documento de origem. GUIDs são fornecidos para linguagens mais conhecidas, fornecedores e tipos de documento.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT DefineDocument(  
    [in]  const WCHAR  *url,  
    [in]  const GUID   *language,  
    [in]  const GUID   *languageVendor,  
    [in]  const GUID   *documentType,  
    [out, retval] ISymUnmanagedDocumentWriter**  pRetVal);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `url`  
 [in] Um ponteiro para um `WCHAR` que define o localizador recursos uniforme (URL) que identifica o documento.  
  
 `language`  
 [in] Um ponteiro para um GUID que define o idioma do documento.  
  
 `languageVendor`  
 [in] Um ponteiro para um GUID que define a identidade do fornecedor para o idioma do documento.  
  
 `documentType`  
 [in] Um ponteiro para um GUID que define o tipo do documento.  
  
 `pRetVal`  
 [out] Um ponteiro para retornado [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.  
  
## <a name="return-value"></a>Valor de retorno  
 S_OK se o método for bem-sucedido; Caso contrário, E_FAIL ou algum outro código de erro.  
  
## <a name="requirements"></a>Requisitos  
 **Cabeçalho:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Consulte também
- [Interface ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
