---
title: Copiando e fixando
ms.date: 03/30/2017
helpviewer_keywords:
- pinning, interop marshaling
- copying, interop marshaling
- interop marshaling, copying
- interop marshaling, pinning
ms.assetid: 0059f576-e460-4e70-b257-668870e420b8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42257790b5a6e5005ca142bd5e32d4c6fc545195
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507077"
---
# <a name="copying-and-pinning"></a>Copiando e fixando
Ao realizar marshaling dos dados, o marshaler de interoperabilidade pode copiar ou fixar os dados com marshaling. A cópia dos dados coloca uma cópia dos dados de um local de memória em outro local de memória. A ilustração a seguir mostra as diferenças entre a cópia de um tipo de valor e a cópia de um tipo passado por referência da memória gerenciada para a não gerenciada.  
  
 ![Tipos de valor passados por valor e por referência](./media/interopmarshalcopy.gif "interopmarshalcopy")  
Tipos de valor passados por valor e por referência  
  
 Os argumentos de método passados por valor têm o marshaling realizado para o código não gerenciado como valores na pilha. O processo de cópia é direto. Os argumentos passados por referência são passados como ponteiros na pilha. Tipos de referência também são passados por valor e por referência. Como mostra a ilustração a seguir, os tipos de referência passados por valor são copiados ou fixados.  
  
 ![Interoperabilidade COM](./media/interopmarshalpin.gif "interopmarshalpin")  
Tipos de referência passados por valor e por referência  
  
 A anexação temporária bloqueia os dados em seu local atual de memória, impedindo, portanto, que eles sejam relocados pelo coletor de lixo do Common Language Runtime. O marshaler fixa os dados para reduzir a sobrecarga da cópia e melhorar o desempenho. O tipo dos dados determina se eles são copiados ou fixados durante o processo de marshaling.  A anexação é executada automaticamente durante o marshaling de objetos, como <xref:System.String>. No entanto, também é possível fixar a memória manualmente usando a classe <xref:System.Runtime.InteropServices.GCHandle>.  
  
## <a name="formatted-blittable-classes"></a>Classes blittable formatadas  
 As classes [blittable](blittable-and-non-blittable-types.md) formatadas têm o layout fixo (formatado) e uma representação de dados comum na memória gerenciada e não gerenciada. Quando esses tipos exigem o marshaling, um ponteiro para o objeto no heap é passado diretamente para o receptor. O receptor pode alterar o conteúdo do local de memória que está sendo referenciado pelo ponteiro.  
  
> [!NOTE]
>  O receptor pode alterar o conteúdo da memória se o parâmetro estiver marcado como Saída ou Entrada/Saída. Por outro lado, o receptor deve evitar alterar o conteúdo quando o parâmetro é definido para ter o marshaling realizado como Entrada, que é o padrão para tipos blittable formatados. A modificação de um objeto de Entrada gera problemas quando a mesma classe é exportada para uma biblioteca de tipos e usada para fazer chamadas entre apartments.  
  
## <a name="formatted-non-blittable-classes"></a>Classes não blittable formatadas  
 As classes [não blittable](blittable-and-non-blittable-types.md) formatadas têm o layout fixo (formatado), mas a representação de dados é diferente na memória gerenciada e não gerenciada. Os dados podem exigir transformação nas seguintes condições:  
  
-   Se uma classe não blittable tem o marshaling realizado por valor, o receptor recebe um ponteiro para uma cópia da estrutura de dados.  
  
-   Se uma classe não blittable tem o marshaling realizado por referência, o receptor recebe um ponteiro para um ponteiro para uma cópia da estrutura de dados.  
  
-   Se o atributo <xref:System.Runtime.InteropServices.InAttribute> for definido, essa cópia será sempre inicializada com o estado da instância, com marshaling conforme necessário.  
  
-   Se o atributo <xref:System.Runtime.InteropServices.OutAttribute> for definido, o estado será sempre copiado novamente para a instância após o retorno, com marshaling conforme necessário.  
  
-   Se **InAttribute** e **OutAttribute** forem definidos, ambas as cópias serão necessárias. Se um dos atributos for omitido, o marshaler poderá otimizar com a eliminação da cópia.  
  
## <a name="reference-types"></a>Tipos de referência  
 Tipos de referência podem ser passados por valor ou por referência. Quando eles são passados por valor, um ponteiro para o tipo é passado na pilha. Quando são passados por referência, um ponteiro para um ponteiro para o tipo é passado na pilha.  
  
 Os tipos de referência têm o seguinte comportamento condicional:  
  
-   Se um tipo de referência é passado por valor e tem membros de tipos não blittable, os tipos são convertidos duas vezes:  
  
    -   Quando um argumento é passado para o lado não gerenciado.  
  
    -   Após o retorno da chamada.  
  
     Para evitar a cópia e a conversão desnecessárias, esses tipos têm o marshaling realizado em parâmetros de Entrada. Aplique os atributos **InAttribute** e **OutAttribute** explicitamente a um argumento para que o chamador veja as alterações feitas pelo receptor.  
  
-   Se um tipo de referência é passado por valor e tem somente membros de tipos blittable, ele pode ser fixado durante o marshaling e todas as alterações feitas nos membros do tipo pelo receptor são vistas pelo chamador. Aplique **InAttribute** e **OutAttribute** explicitamente se desejar obter esse comportamento. Sem esses atributos direcionais, o marshaler de interoperabilidade não exporta as informações direcionais para a biblioteca de tipos (ele exporta-as como Entrada, que é o padrão) e isso poderá causar problemas com o marshaling entre apartments do COM.  
  
-   Se um tipo de referência for passado por referência, ele terá o marshaling realizado como Entrada/Saída por padrão.  
  
## <a name="systemstring-and-systemtextstringbuilder"></a>System.String e System.Text.StringBuilder  
 Quando os dados têm o marshaling realizado para um código não gerenciado por valor ou por referência, o marshaler normalmente copia os dados para um buffer secundário (possivelmente, convertendo conjuntos de caracteres durante a cópia) e passa uma referência para o buffer para o receptor. A menos que a referência seja um **BSTR** alocado com **SysAllocString**, a referência é sempre alocada com **CoTaskMemAlloc**.  
  
 Como uma otimização quando um tipo de cadeia de caracteres tem o marshaling realizado por valor (como uma cadeia de caracteres Unicode), o marshaler passa ao receptor um ponteiro direto para cadeias de caracteres gerenciadas no buffer interno do Unicode, em vez de copiá-lo para um novo buffer.  
  
> [!CAUTION]
>  Quando uma cadeia de caracteres é passada por valor, o receptor nunca deve alterar a referência passada pelo marshaler. Isso pode corromper o heap gerenciado.  
  
 Quando um <xref:System.String?displayProperty=nameWithType> é passado por referência, o marshaler copia o conteúdo da cadeia de caracteres para um buffer secundário antes de fazer a chamada. Em seguida, ele copia o conteúdo do buffer para uma nova cadeia de caracteres após o retorno da chamada. Essa técnica garante que a cadeia de caracteres gerenciada imutável permaneça inalterada.  
  
 Quando um <xref:System.Text.StringBuilder?displayProperty=nameWithType> é passado por valor, o marshaler passa uma referência ao buffer interno do **StringBuilder** diretamente para o chamador. O chamador e o receptor devem concordar com o tamanho do buffer. O chamador é responsável pela criação de um **StringBuilder** de tamanho adequado. O receptor deve tomar as precauções necessárias para garantir que o buffer não tenha estouro. **StringBuilder** é uma exceção à regra em que os tipos de referência passados por valor são passados como parâmetros de Entrada por padrão. Ele é sempre passado como Entrada/Saída.  
  
## <a name="see-also"></a>Consulte também
- [Comportamento de marshaling padrão](default-marshaling-behavior.md)
- [Gerenciamento de memória com o empacotador de interoperabilidade](https://msdn.microsoft.com/library/417206ce-ee3e-4619-9529-0c0b686c7bee(v=vs.100))
- [Atributos direcionais](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))
- [Marshaling de interoperabilidade](interop-marshaling.md)
