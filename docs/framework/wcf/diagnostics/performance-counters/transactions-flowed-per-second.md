---
title: Fluxo de transações por segundo
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501298"
---
# <a name="transactions-flowed-per-second"></a>Fluxo de transações por segundo
Nome do contador: Fluxo de transações por segundo  
  
## <a name="description"></a>Descrição  
 Número de transações flui para essa operação em um segundo. Esse contador é incrementado sempre que uma ID de transação está presente em uma mensagem que é enviada para a operação.  
  
 Esse contador é do tipo de contador de desempenho [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), cujo valor é calculado usando a fórmula a seguir.  
  
 (N 1 - N 0) / ((1!D 1 - D 0) / F)
