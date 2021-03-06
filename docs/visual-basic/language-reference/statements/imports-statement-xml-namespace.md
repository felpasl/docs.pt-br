---
title: Importar instrução - Namespace XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: e137b27ae5128e54eca466632cadad9908232045
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655979"
---
# <a name="imports-statement-xml-namespace"></a>Instrução Imports (namespace XML)
Importa os prefixos de namespace XML para uso em literais XML e propriedades de eixo XML.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a>Partes  
 `xmlNamespacePrefix`  
 Opcional. A cadeia de caracteres pela qual XML elementos e atributos podem se referir ao `xmlNamespaceName`. Se nenhum `xmlNamespacePrefix` é fornecido, o namespace XML importado é o namespace XML padrão. Deve ser um identificador XML válido. Para obter mais informações, consulte [nomes de declarado elementos e atributos XML](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).  
  
 `xmlNamespaceName`  
 Necessário. A cadeia de caracteres que identifica o namespace XML que está sendo importado.  
  
## <a name="remarks"></a>Comentários  
 Você pode usar o `Imports` instrução para definir os namespaces XML globais que você pode usar com literais XML e propriedades de eixo XML, ou como parâmetros passados para o `GetXmlNamespace` operador. (Para obter informações sobre como usar o `Imports` instrução para importar um alias que pode ser usado onde os nomes de tipo são usados em seu código, consulte [instrução Imports (tipo e Namespace .NET)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) A sintaxe para declarar um namespace de XML usando o `Imports` instrução é idêntica à sintaxe usada em XML. Portanto, você pode copiar uma declaração de namespace de um arquivo XML e usá-lo em um `Imports` instrução.  
  
 Prefixos de namespace XML são úteis quando você deseja criar repetidamente elementos XML que são do mesmo namespace. O prefixo de namespace XML declarado com o `Imports` instrução é global no sentido de que ele esteja disponível para todo o código no arquivo. Você pode usá-lo quando você cria literais de elemento XML e acessar propriedades do eixo XML. Para obter mais informações, consulte [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) e [propriedades do eixo XML](../../../visual-basic/language-reference/xml-axis/index.md).  
  
 Se você definir um namespace XML global sem um prefixo de namespace (por exemplo, `Imports <xmlns="http://SomeNameSpace>"`), esse namespace é considerado o namespace XML padrão. O namespace XML padrão é usado para qualquer literais de elemento XML ou propriedades de eixo de atributo XML que não especificam explicitamente um namespace. O namespace padrão também é usado se o namespace especificado for o namespace vazio (ou seja, `xmlns=""`). O namespace XML padrão não se aplica aos atributos XML em literais XML ou propriedades de eixo de atributo XML que não têm um namespace.  
  
 Namespaces XML são definidos em um literal XML, que são chamados *local namespaces XML*, têm precedência sobre namespaces XML que são definidos pelo `Imports` instrução como global. Namespaces XML que são definidos pelo `Imports` instrução têm precedência sobre namespaces XML importados para um projeto do Visual Basic. Se um literal XML define um namespace XML, esse namespace local não se aplica a expressões inseridas.  
  
 Namespaces XML globais seguem as mesmas regras de escopo e definição de namespaces do .NET Framework. Como resultado, você pode incluir um `Imports` instrução para definir um namespace XML global em qualquer lugar, você pode importar um namespace do .NET Framework. Isso inclui arquivos de código e namespaces importados no nível do projeto. Para obter informações sobre namespaces importados no nível de projeto, consulte [página referências, Designer de projeto (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).  
  
 Cada arquivo de origem pode conter qualquer número de `Imports` instruções. Eles devem seguir declarações de opção, como o `Option Strict` instrução e eles devem preceder declarações de elemento de programação, como `Module` ou `Class` instruções.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir importa um namespace XML padrão e um namespace XML identificado com o prefixo `ns`. Depois, ele cria literais XML que usam os dois namespaces.  
  
 [!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]  
  
 Esse código exibe o texto a seguir:  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir importa o prefixo de namespace XML `ns`. Depois, ele cria um literal XML que usa o prefixo de namespace e exibe o formulário final do elemento.  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]  
  
 Esse código exibe o texto a seguir:  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 Observe que o compilador converteu o prefixo de namespace XML de um prefixo global para uma definição de prefixo local.  
  
## <a name="example"></a>Exemplo  
 O exemplo a seguir importa o prefixo de namespace XML `ns`. Ele usa o prefixo de namespace para criar um literal XML e acessar o primeiro nó filho com o nome qualificado `ns:name`.  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]  
  
 Esse código exibe o texto a seguir:  
  
 `Patrick Hines`  
  
## <a name="see-also"></a>Consulte também
- [Literal do Elemento XML](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Propriedades do Eixo XML](../../../visual-basic/language-reference/xml-axis/index.md)
- [Nomes de Elementos e Atributos XML Declarados](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [Operador GetXmlNamespace](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
