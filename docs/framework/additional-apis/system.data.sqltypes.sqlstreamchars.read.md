---
title: Método SqlStreamChars.Read (Char [], Int32, Int32) (SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 87bff6dd78743ae08a5a3db8a783b56a0b7c3f24
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152529"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="ca181-102">Método SqlStreamChars.Read (Char [], Int32, Int32)</span><span class="sxs-lookup"><span data-stu-id="ca181-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="ca181-103">Quando substituído em uma classe derivada, lê o próximo conjunto de caracteres do fluxo de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca181-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="ca181-104">O assembly que contém este método tem uma relação de amigo com SQLAccess.dll.</span><span class="sxs-lookup"><span data-stu-id="ca181-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="ca181-105">Ele é destinado a uso pelo SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca181-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="ca181-106">Para outros bancos de dados, use o mecanismo de hospedagem fornecido pelo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ca181-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="ca181-107">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ca181-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="ca181-108">Uma matriz de char para ler.</span><span class="sxs-lookup"><span data-stu-id="ca181-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="ca181-109">Um deslocamento relativo à origem.</span><span class="sxs-lookup"><span data-stu-id="ca181-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="ca181-110">O número de caracteres a serem lidos do fluxo atual.</span><span class="sxs-lookup"><span data-stu-id="ca181-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="ca181-111">Retorna</span><span class="sxs-lookup"><span data-stu-id="ca181-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="ca181-112">O número total de caracteres lidos no buffer.</span><span class="sxs-lookup"><span data-stu-id="ca181-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="ca181-113">Comentários</span><span class="sxs-lookup"><span data-stu-id="ca181-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="ca181-114">O `SqlStreamChars.Read` método é privado e não se destina a ser usado diretamente em seu código.</span><span class="sxs-lookup"><span data-stu-id="ca181-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ca181-115">Microsoft não suporta o uso deste campo em um aplicativo de produção sob nenhuma circunstância.</span><span class="sxs-lookup"><span data-stu-id="ca181-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca181-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca181-116">Requirements</span></span>

<span data-ttu-id="ca181-117">**Namespace:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="ca181-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="ca181-118">**Assembly:** System. Data (em dll)</span><span class="sxs-lookup"><span data-stu-id="ca181-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="ca181-119">**Versões do .NET framework:** Disponível desde o 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca181-119">**.NET Framework versions:** Available since 2.0.</span></span>