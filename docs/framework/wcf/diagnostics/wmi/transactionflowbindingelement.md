---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: d0311837ebb8112d9492fb548492bcd3e10230e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54514563"
---
# <a name="transactionflowbindingelement"></a>TransactionFlowBindingElement
TransactionFlowBindingElement  
  
## <a name="syntax"></a>Sintaxe  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a>Métodos  
 A classe TransactionFlowBindingElement não define quaisquer métodos.  
  
## <a name="properties"></a>Propriedades  
 A classe TransactionFlowBindingElement tem as seguintes propriedades:  
  
### <a name="issuedtokens"></a>IssuedTokens  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 Especifica o requisito para um cabeçalho de tokens de segurança emitido (IssuedTokens do WS-Trust).  
  
### <a name="transactionprotocol"></a>TransactionProtocol  
 Tipo de dados: cadeia de caracteres  
  
 Tipo de acesso: Somente leitura  
  
 O protocolo de transações usado pelo serviço para transações de fluxo.  
  
### <a name="transactions"></a>Transações  
 Tipo de dados: boolean  
  
 Tipo de acesso: Somente leitura  
  
 Indica se a transação de entrada tem suporte.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Declarado em Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definido no root\ServiceModel|  
  
## <a name="see-also"></a>Consulte também
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
