---
title: Função GetObjectText (referência de API não gerenciada)
description: A função GetObjectText retorna um processamento textual de um objeto na sintaxe MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3a7d606f64dfe1a1abfd3da930fd00957da90a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583570"
---
# <a name="getobjecttext-function"></a>Função GetObjectText
Retorna um processamento textual do objeto na sintaxe do formato MOF (Managed Object).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Parâmetros

`vFunc`  
[in] Esse parâmetro é usado.

`ptr`  
[in] Um ponteiro para um [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instância.

`lFlags`  
[in] Normalmente 0. Se `WBEM_FLAG_NO_FLAVORS` (ou 0x1) for especificado, qualificadores são incluídos sem propagação ou o tipo de informações.

`pstrObjectText`   
[out] Um ponteiro para um `null` na entrada. No retorno, alocadas recentemente `BSTR` que contém uma renderização de sintaxe MOF do objeto.  

## <a name="return-value"></a>Valor retornado

Os seguintes valores retornados por essa função são definidos na *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:

|Constante  |Valor  |Descrição  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Houve uma falha geral. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Um parâmetro não é válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Não há memória disponível suficiente para concluir a operação. |
|`WBEM_S_NO_ERROR` | 0 | A chamada de função foi bem-sucedida.  |
  
## <a name="remarks"></a>Comentários

Essa função encapsula uma chamada para o [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) método.

O texto MOF retornado contém todas as informações sobre o objeto, mas apenas informações suficientes para que o compilador MOF ser capaz de recriar o objeto original. Por exemplo, nenhum qualificadores propagadas ou propriedades da classe pai são incluídas.

O seguinte algoritmo é usado para reconstruir o texto dos parâmetros de um método:

1. O colocado no parâmetros são sequência na ordem de seus valores de identificador seguintes novamente.
1. Parâmetros que são especificados como `[in]` e `[out]` são combinados em um único parâmetro.
 
`pstrObjectText` deve ser um ponteiro para um `null` quando a função é chamada; ele não deve apontar para uma cadeia de caracteres que é válida antes da chamada de método, porque o ponteiro não será desalocado.

## <a name="requirements"></a>Requisitos  
**Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** WMINet_Utils.idl  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte também
- [WMI e contadores de desempenho (referência de API não gerenciada)](index.md)
