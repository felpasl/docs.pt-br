---
title: Membros protegidos
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: KrzysztofCwalina
ms.openlocfilehash: 7d940f10799df2efc6c6d031781e1ef7cf777dd6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559328"
---
# <a name="protected-members"></a>Membros protegidos
Membros protegidos por si só não fornecem todos extensibilidade, mas eles podem tornar mais poderosa extensibilidade por meio de subclasse. Eles podem ser usados para expor as opções avançadas de personalização sem complicar desnecessariamente a principal interface pública.  
  
 Designers do Framework precisam ter cuidado com membros protegidos porque o nome "protegido" pode fornecer uma falsa sensação de segurança. Qualquer pessoa é capaz de subclasse de uma classe não lacrada e membros protegido de acesso e, então todos os mesmos defensivas práticas de codificação usadas para os membros públicos se aplicam a membros protegidos.  
  
 **✓ CONSIDER** usando membros para a personalização avançada protegidos.  
  
 **✓ DO** tratar membros protegidos em classes não lacradas como public para fins de análise de segurança, documentação e compatibilidade.  
  
 Qualquer pessoa pode herdar de uma classe e acessar os membros protegidos.  
  
 *Portions © 2005, 2009 Microsoft Corporation. Todos os direitos reservados.*  
  
 *Reimpresso com permissão da Pearson Education, Inc. de [as diretrizes de Design do Framework: As convenções, linguagens e padrões para bibliotecas do .NET reutilizável, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) por Krzysztof Cwalina e Brad Abrams, publicados 22 de outubro de 2008 pela Addison-Wesley Professional, como parte da série de desenvolvimento do Microsoft Windows.*  
  
## <a name="see-also"></a>Consulte também

- [Diretrizes de design do Framework](../../../docs/standard/design-guidelines/index.md)
- [Designer voltado para extensibilidade](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
