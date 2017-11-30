---
title: "Como extrair o dia da semana de uma data específica"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- DateTime.DayOfWeek property
- DateTime.ToString method
- dates [.NET Framework], retrieving week information
- DateTimeOffset.DayOfWeek property
- dates [.NET Framework], day of week
- Weekday function
- day of week [.NET Framework]
- extracting day of week
- weekday names
- WeekdayName function
- numbers [.NET Framework], day of week
- formatting [.NET Framework], time
- DateTimeOffset.ToString method
- full weekday names
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3accb01eb8c5edb8b3e245020b43c5a94a8bb4cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="1499a-102">Como extrair o dia da semana de uma data específica</span><span class="sxs-lookup"><span data-stu-id="1499a-102">How to: Extract the Day of the Week from a Specific Date</span></span>
<span data-ttu-id="1499a-103">O .NET Framework facilita a verificação da posição numérica do dia da semana em uma determinada data e a exibição do nome do dia localizado em uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="1499a-103">The .NET Framework makes it easy to determine the ordinal day of the week for a particular date, and to display the localized weekday name for a particular date.</span></span> <span data-ttu-id="1499a-104">O valor enumerado que indica o dia da semana correspondente a uma determinada data está disponível na propriedade <xref:System.DateTime.DayOfWeek%2A> ou <xref:System.DateTimeOffset.DayOfWeek%2A>.</span><span class="sxs-lookup"><span data-stu-id="1499a-104">An enumerated value that indicates the day of the week corresponding to a particular date is available from the <xref:System.DateTime.DayOfWeek%2A> or <xref:System.DateTimeOffset.DayOfWeek%2A> property.</span></span> <span data-ttu-id="1499a-105">Em contrapartida, para recuperar o nome do dia da semana é necessário realizar uma operação de formatação que pode ser executada com a chamada de um método de formatação, como o método `ToString` ou <xref:System.String.Format%2A?displayProperty=nameWithType> de valor de data e hora.</span><span class="sxs-lookup"><span data-stu-id="1499a-105">In contrast, retrieving the weekday name is a formatting operation that can be performed by calling a formatting method, such as a date and time value's `ToString` method or the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1499a-106">Este tópico mostra como executar essas operações de formatação.</span><span class="sxs-lookup"><span data-stu-id="1499a-106">This topic shows how to perform these formatting operations.</span></span>  
  
### <a name="to-extract-a-number-indicating-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="1499a-107">Para extrair um número que indique o dia da semana em uma determinada data</span><span class="sxs-lookup"><span data-stu-id="1499a-107">To extract a number indicating the day of the week from a specific date</span></span>  
  
1.  <span data-ttu-id="1499a-108">Se você estiver trabalhando na representação da cadeia de caracteres de uma data, converta-a para um valor <xref:System.DateTime> ou <xref:System.DateTimeOffset> usando a estatística <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> ou o método <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1499a-108">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="1499a-109">Use a propriedade <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> ou <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> para recuperar um valor de <xref:System.DayOfWeek> que indica o dia da semana.</span><span class="sxs-lookup"><span data-stu-id="1499a-109">Use the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve a <xref:System.DayOfWeek> value that indicates the day of the week.</span></span>  
  
3.  <span data-ttu-id="1499a-110">Se necessário, execute coerção (no C#) ou converta (no Visual Basic) o valor de <xref:System.DayOfWeek> para um número inteiro.</span><span class="sxs-lookup"><span data-stu-id="1499a-110">If necessary, cast (in C#) or convert (in Visual Basic) the <xref:System.DayOfWeek> value to an integer.</span></span>  
  
 <span data-ttu-id="1499a-111">O exemplo a seguir mostra um inteiro que representa o dia da semana de uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="1499a-111">The following example displays an integer that represents the day of the week of a specific date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
### <a name="to-extract-the-abbreviated-weekday-name-from-a-specific-date"></a><span data-ttu-id="1499a-112">Para extrair o nome do dia da semana abreviado de uma determinada data</span><span class="sxs-lookup"><span data-stu-id="1499a-112">To extract the abbreviated weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="1499a-113">Se você estiver trabalhando na representação da cadeia de caracteres de uma data, converta-a para um valor <xref:System.DateTime> ou <xref:System.DateTimeOffset> usando a estatística <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> ou o método <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1499a-113">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="1499a-114">Você pode extrair o nome de dia da semana abreviado da cultura atual ou de uma cultura específica:</span><span class="sxs-lookup"><span data-stu-id="1499a-114">You can extract the abbreviated weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="1499a-115">Para extrair o nome de dia da semana abreviado da cultura atual, chame o método de instância <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> ou <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> do valor de data e hora e informe a cadeia de caracteres "ddd" como o parâmetro `format`.</span><span class="sxs-lookup"><span data-stu-id="1499a-115">To extract the abbreviated weekday name for the current culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="1499a-116">O exemplo a seguir ilustra a chamada do método <xref:System.DateTime.ToString%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="1499a-116">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2.  <span data-ttu-id="1499a-117">Para extrair o nome de dia da semana abreviado de uma cultura específica, chame o método de instância <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> ou <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> do valor de data e hora.</span><span class="sxs-lookup"><span data-stu-id="1499a-117">To extract the abbreviated weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="1499a-118">Informe a cadeia de caracteres "ddd" como o parâmetro `format`.</span><span class="sxs-lookup"><span data-stu-id="1499a-118">Pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="1499a-119">Apresente um objeto <xref:System.Globalization.CultureInfo> ou <xref:System.Globalization.DateTimeFormatInfo> que representa a cultura cujo nome de dia da semana deve ser recuperado como parâmetro `provider`.</span><span class="sxs-lookup"><span data-stu-id="1499a-119">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="1499a-120">O código a seguir mostra um chamada ao método <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> usando um objeto <xref:System.Globalization.CultureInfo> que representa a cultura fr-FR.</span><span class="sxs-lookup"><span data-stu-id="1499a-120">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the fr-FR culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
### <a name="to-extract-the-full-weekday-name-from-a-specific-date"></a><span data-ttu-id="1499a-121">Para extrair o nome completo do dia da semana de uma determinada data</span><span class="sxs-lookup"><span data-stu-id="1499a-121">To extract the full weekday name from a specific date</span></span>  
  
1.  <span data-ttu-id="1499a-122">Se você estiver trabalhando na representação da cadeia de caracteres de uma data, converta-a para um valor <xref:System.DateTime> ou <xref:System.DateTimeOffset> usando a estatística <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> ou o método <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1499a-122">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="1499a-123">Você pode extrair o nome completo de dia da semana da cultura atual ou de uma cultura específica:</span><span class="sxs-lookup"><span data-stu-id="1499a-123">You can extract the full weekday name of the current culture or of a specific culture:</span></span>  
  
    1.  <span data-ttu-id="1499a-124">Para extrair o nome completo de dia da semana da cultura atual, chame o método de instância <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> ou <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> do valor de data e hora e informe a cadeia de caracteres "dddd" como o parâmetro `format`.</span><span class="sxs-lookup"><span data-stu-id="1499a-124">To extract the weekday name for the current culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="1499a-125">O exemplo a seguir ilustra a chamada do método <xref:System.DateTime.ToString%28System.String%29>.</span><span class="sxs-lookup"><span data-stu-id="1499a-125">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2.  <span data-ttu-id="1499a-126">Para extrair o nome completo de dia da semana de uma cultura específica, chame o método de instância <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> ou <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> do valor de data e hora.</span><span class="sxs-lookup"><span data-stu-id="1499a-126">To extract the weekday name for a specific culture, call the date and time value’s <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="1499a-127">Informe a cadeia de caracteres "dddd" como o parâmetro `format`.</span><span class="sxs-lookup"><span data-stu-id="1499a-127">Pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="1499a-128">Apresente um objeto <xref:System.Globalization.CultureInfo> ou <xref:System.Globalization.DateTimeFormatInfo> que representa a cultura cujo nome de dia da semana deve ser recuperado como parâmetro `provider`.</span><span class="sxs-lookup"><span data-stu-id="1499a-128">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="1499a-129">O código a seguir mostra um chamada ao método <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> usando um objeto <xref:System.Globalization.CultureInfo> que representa a cultura es-ES.</span><span class="sxs-lookup"><span data-stu-id="1499a-129">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the es-ES culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="1499a-130">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1499a-130">Example</span></span>  
 <span data-ttu-id="1499a-131">O exemplo ilustra chamadas às propriedades <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> e<xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> e aos métodos <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> e <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> para recuperar o número que representa o dia da semana, o nome de dia da semana abreviado e o nome completo de dia da semana para uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="1499a-131">The example illustrates calls to the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> properties and the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> methods to retrieve the number that represents the day of the week, the abbreviated weekday name, and the full weekday name for a particular date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 <span data-ttu-id="1499a-132">Cada linguagem pode contar com funcionalidades que duplicam ou complementam a funcionalidade de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1499a-132">Individual languages may provide functionality that duplicates or supplements the functionality provided by the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="1499a-133">Por exemplo, o Visual Basic tem duas funções desse tipo:</span><span class="sxs-lookup"><span data-stu-id="1499a-133">For example, Visual Basic includes two such functions:</span></span>  
  
-   <span data-ttu-id="1499a-134">`Weekday`, que retorna um número que indica o dia da semana de uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="1499a-134">`Weekday`, which returns a number that indicates the day of the week of a particular date.</span></span> <span data-ttu-id="1499a-135">Ele leva em consideração que o primeiro dia da semana tem valor ordinal um, enquanto a propriedade <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> considera o valor ordinal desse dia como zero.</span><span class="sxs-lookup"><span data-stu-id="1499a-135">It considers the ordinal value of the first day of the week to be one, whereas the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property considers it to be zero.</span></span>  
  
-   <span data-ttu-id="1499a-136">`WeekdayName`, que retorna o nome da semana na cultura atual e que corresponde ao número de um determinado dia da semana.</span><span class="sxs-lookup"><span data-stu-id="1499a-136">`WeekdayName`, which returns the name of the week in the current culture that corresponds to a particular weekday number.</span></span>  
  
 <span data-ttu-id="1499a-137">O exemplo a seguir ilustra o uso das funções `Weekday` e `WeekdayName` do Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="1499a-137">The following example illustrates the use of the Visual Basic `Weekday` and `WeekdayName` functions.</span></span>  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 <span data-ttu-id="1499a-138">Você também pode usar o valor retornado pela propriedade <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> para recuperar o nome de dia da semana de uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="1499a-138">You can also use the value returned by the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve the weekday name of a particular date.</span></span> <span data-ttu-id="1499a-139">Isso requer apenas uma chamada ao método <xref:System.Enum.ToString%2A> no valor <xref:System.DayOfWeek> retornado pela propriedade.</span><span class="sxs-lookup"><span data-stu-id="1499a-139">This requires only a call to the <xref:System.Enum.ToString%2A> method on the <xref:System.DayOfWeek> value returned by the property.</span></span> <span data-ttu-id="1499a-140">No entanto, essa técnica não gera um nome de dia da semana localizado para a cultura atual, como mostra o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="1499a-140">However, this technique does not produce a localized weekday name for the current culture, as the following example illustrates.</span></span>  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="1499a-141">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1499a-141">See Also</span></span>  
 [<span data-ttu-id="1499a-142">Executando operações de formatação</span><span class="sxs-lookup"><span data-stu-id="1499a-142">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="1499a-143">Cadeias de caracteres de formato de data e hora padrão</span><span class="sxs-lookup"><span data-stu-id="1499a-143">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [<span data-ttu-id="1499a-144">Cadeias de caracteres de formato de data e hora personalizado</span><span class="sxs-lookup"><span data-stu-id="1499a-144">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)