---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 012590a21ac24b1146c30405c9872355a4b50802
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627246"
---
# <a name="getcustomui"></a>GetCustomUI
Chamado por PresentationHost.exe para obter mensagens de erro e andamento personalizadas do host, se implementado.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `pwzProgressAssemblyName`  
  
 [out] Um ponteiro para o assembly que contém a interface do usuário de andamento fornecida pelo host.  
  
 `pwzProgressClassName`  
  
 [out] O nome da classe que é a interface de usuário de andamento fornecida pelo host, preferencialmente um [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] de arquivos com <xref:System.Windows.Controls.Page> é seu elemento de nível superior. Essa classe reside no assembly especificado por `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Um ponteiro para o assembly que contém a interface do usuário de erro fornecida pelo host.  
  
 `pwzErrorClassName`  
  
 [out] O nome da classe que é o usuário de erro fornecida pelo host interface, de preferência um arquivo XAML com <xref:System.Windows.Controls.Page> é seu elemento de nível superior. Essa classe reside no assembly especificado por `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Valor da propriedade/valor de retorno  
 HRESULT: Ignorado.  
  
## <a name="remarks"></a>Comentários  
 Um aplicativo host pode ter um tema específico com o qual as interfaces do usuário padrão do PresentationHost.exe podem não estar em conformidade. Se esse for o caso, o aplicativo host poderá implementar [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) para retornar as interfaces do usuário de erro e de andamento para PresentationHost.exe. PresentationHost.exe sempre chamará [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) antes de usar suas interfaces do usuário padrão.  
  
 Essa função é chamada uma vez durante a inicialização do PresentationHost.  
  
## <a name="see-also"></a>Consulte também
- [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
