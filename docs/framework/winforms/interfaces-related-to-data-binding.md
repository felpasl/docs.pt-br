---
title: Interfaces relacionadas à associação de dados
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 5a83198a665563c3d283cac042c9fec95c60f8e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547125"
---
# <a name="interfaces-related-to-data-binding"></a>Interfaces relacionadas à associação de dados
Com o [!INCLUDE[vstecado](../../../includes/vstecado-md.md)], você pode criar diversas estruturas de dados para atender às necessidades de associação do seu aplicativo e dos dados com os quais você está trabalhando. Talvez você queira criar suas próprias classes que forneçam ou consumam dados nos Windows Forms. Esses objetos podem oferecer vários níveis de funcionalidade e complexidade, desde a vinculação de dados básica até o fornecimento de suporte em tempo de design, verificação de erros, notificação de alterações ou até mesmo suporte para uma reversão estruturada das alterações feitas nos próprios dados.  
  
## <a name="consumers-of-data-binding-interfaces"></a>Consumidores de interfaces de associação de dados  
 As seções a seguir descrevem dois grupos de objetos de interface. O primeiro grupo lista as interfaces que são implementadas nas fontes de dados por autores de fonte de dados. Essas interfaces são projetadas para serem consumidas pelos consumidores de fonte de dados, que são, na maioria dos casos, controles ou componentes dos Windows Forms. O segundo grupo lista as interfaces projetadas para serem usadas por autores de componente. Os autores de componente usam essas interfaces quando estão criando um componente que dá suporte à vinculação de dados a ser consumida pelo mecanismo de vinculação de dados dos Windows Forms. Você pode implementar essas interfaces nas classes associadas ao seu formulário para habilitar a vinculação de dados. Cada caso apresenta uma classe que implementa uma interface que habilita a interação com os dados. Visual Studio RAD RAD (desenvolvimento) dados design experiência ferramentas já aproveitam essa funcionalidade.  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfaces para implementação por autores de fonte de dados  
 As seguintes interfaces são projetadas para serem consumidas por controles dos Windows Forms:  
  
-   <xref:System.Collections.IList> Interface  
  
     Uma classe que implementa o <xref:System.Collections.IList> interface pode ser um <xref:System.Array>, <xref:System.Collections.ArrayList>, ou <xref:System.Collections.CollectionBase>. Essas são listas indexadas de itens do tipo <xref:System.Object>. Essas listas devem conter tipos homogêneos, porque o primeiro item do índice determina o tipo. <xref:System.Collections.IList> estaria disponível para associação somente em tempo de execução.  
  
    > [!NOTE]
    >  Se você quiser criar uma lista de objetos comerciais para associação com o Windows Forms, você deve considerar usar o <xref:System.ComponentModel.BindingList%601>. O <xref:System.ComponentModel.BindingList%601> é uma classe extensível que implementa as interfaces principais necessárias para vinculação de dados bidirecional do Windows Forms.  
  
-   <xref:System.ComponentModel.IBindingList> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.IBindingList> interface fornece um nível mais alto de funcionalidade de associação de dados. Essa implementação oferece recursos básicos de classificação e notificação de alteração para quando os itens da lista são alterados (por exemplo, o terceiro item em uma lista de clientes tem uma alteração no campo de endereço), bem como quando a própria lista é alterada (por exemplo, o número de itens na lista aumenta ou diminui). A notificação de alteração é importante se você planeja ter vários controles associados aos mesmos dados e deseja que as alterações de dados feitas em um dos controles sejam propagadas para os outros controles associados.  
  
    > [!NOTE]
    >  Notificação de alteração está habilitada para o <xref:System.ComponentModel.IBindingList> por meio da interface de <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> propriedade que, quando `true`, gera um <xref:System.ComponentModel.IBindingList.ListChanged> evento, que indica a lista alterado ou um item na lista alterado.  
  
     O tipo de alteração é descrito pela <xref:System.ComponentModel.ListChangedType> propriedade do <xref:System.ComponentModel.ListChangedEventArgs> parâmetro. Portanto, sempre que o modelo de dados for atualizado, quaisquer exibições dependentes, como outros controles associados à mesma fonte de dados, também serão atualizadas. No entanto, os objetos contidos na lista terão que notificar a lista quando forem alterados para que a lista possa acionar o <xref:System.ComponentModel.IBindingList.ListChanged> eventos.  
  
    > [!NOTE]
    >  O <xref:System.ComponentModel.BindingList%601> fornece uma implementação genérica do <xref:System.ComponentModel.IBindingList> interface.  
  
-   <xref:System.ComponentModel.IBindingListView> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.IBindingListView> interface fornece toda a funcionalidade de uma implementação de <xref:System.ComponentModel.IBindingList>, bem como filtragem e avançada funcionalidade de classificação. Essa implementação oferece filtragem baseada em cadeia de caracteres e classificação de várias colunas com pares de propriedade descritor-direção.  
  
-   <xref:System.ComponentModel.IEditableObject> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.IEditableObject> interface permite que um objeto controlar quando as alterações a esse objeto se tornam permanentes. Essa implementação oferece o <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> métodos, que permitem que você reverta as alterações feitas no objeto. A seguir está uma breve explicação sobre o funcionamento do <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> métodos e como elas funcionam em conjunto com outra para habilitar uma possível reversão das alterações feitas nos dados:  
  
    -   O <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> método sinaliza o início de uma edição em um objeto. Um objeto que implementa essa interface precisará armazenar todas as atualizações após a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chamada de método de tal forma que as atualizações podem ser descartadas se o <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> método é chamado. No Windows Forms de vinculação de dados, você pode chamar <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> várias vezes dentro do escopo de uma única transação Editar (por exemplo, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Implementações de <xref:System.ComponentModel.IEditableObject> deve controlar se <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> já foi chamado e ignorar as chamadas subsequentes para <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Como esse método pode ser chamado várias vezes, é importante que as chamadas subsequentes a ele sejam não destrutivas; ou seja, subsequentes <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chamadas não é possível destruir as atualizações que foram feitas ou alteram os dados que foi salvo no primeiro <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chamar.  
  
    -   O <xref:System.ComponentModel.IEditableObject.EndEdit%2A> método por push as alterações desde <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> foi chamado no objeto subjacente, se o objeto estiver atualmente no modo de edição.  
  
    -   O <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> método descartará as alterações feitas no objeto.  
  
     Para obter mais informações sobre como o <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> métodos funcionam, consulte [salvar os dados no banco de dados](/visualstudio/data-tools/save-data-back-to-the-database).  
  
     Essa noção transacional de funcionalidade de dados é usada pelo <xref:System.Windows.Forms.DataGridView> controle.  
  
-   <xref:System.ComponentModel.ICancelAddNew> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.ICancelAddNew> geralmente implementa uma interface de <xref:System.ComponentModel.IBindingList> interface e permite que você reverta uma adição feita à fonte de dados com o <xref:System.ComponentModel.IBindingList.AddNew%2A> método. Se a fonte de dados implementa a <xref:System.ComponentModel.IBindingList> interface, você também deve ter que implementar o <xref:System.ComponentModel.ICancelAddNew> interface.  
  
-   <xref:System.ComponentModel.IDataErrorInfo> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.IDataErrorInfo> interface permite que os objetos ofereçam informações de erro personalizada para controles associados:  
  
    -   O <xref:System.ComponentModel.IDataErrorInfo.Error%2A> propriedade retorna o texto da mensagem de erro geral (por exemplo, "erro").  
  
    -   O <xref:System.ComponentModel.IDataErrorInfo.Item%2A> propriedade retorna uma cadeia de caracteres com a mensagem de erro da coluna (por exemplo, "o valor no `State` coluna é inválida").  
  
-   <xref:System.Collections.IEnumerable> Interface  
  
     Uma classe que implementa o <xref:System.Collections.IEnumerable> interface geralmente é consumida pelo [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Suporte do Windows Forms para essa interface só está disponível por meio de <xref:System.Windows.Forms.BindingSource> componente.  
  
    > [!NOTE]
    >  O <xref:System.Windows.Forms.BindingSource> componente copia todos os <xref:System.Collections.IEnumerable> itens em uma lista separada para fins de associação.  
  
-   <xref:System.ComponentModel.ITypedList> Interface  
  
     Uma classe de coleções que implementa o <xref:System.ComponentModel.ITypedList> interface fornece a capacidade de controlar a ordem e o conjunto de propriedades expostas ao controle associado.  
  
    > [!NOTE]
    >  Quando você implementa o <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> método e o <xref:System.ComponentModel.PropertyDescriptor> matriz não for nula, a última entrada na matriz será o descritor de propriedade que descreve a propriedade de lista que é outra lista de itens.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.ICustomTypeDescriptor> interface fornece informações dinâmicas sobre si mesmo. Essa interface é semelhante ao <xref:System.ComponentModel.ITypedList> , mas é usado para objetos em vez de listas. Essa interface é usada por <xref:System.Data.DataRowView> para projetar o esquema das linhas subjacentes. Uma implementação simples da <xref:System.ComponentModel.ICustomTypeDescriptor> é fornecido pelo <xref:System.ComponentModel.CustomTypeDescriptor> classe.  
  
    > [!NOTE]
    >  Para dar suporte à associação de tempo de design para tipos que implementam <xref:System.ComponentModel.ICustomTypeDescriptor>, o tipo deve implementar também <xref:System.ComponentModel.IComponent> e existir como uma instância do formulário.  
  
-   <xref:System.ComponentModel.IListSource> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.IListSource> interface permite que a associação baseada em lista de objetos fora da lista. O <xref:System.ComponentModel.IListSource.GetList%2A> método de <xref:System.ComponentModel.IListSource> é usado para retornar uma lista vinculável de um objeto que não herda de <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> é usado pelo <xref:System.Data.DataSet> classe.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents> Interface  
  
     Uma classe que implementa o <xref:System.ComponentModel.IRaiseItemChangedEvents> interface é uma lista associável que também implementa o <xref:System.ComponentModel.IBindingList> interface. Essa interface é usada para indicar se o tipo aciona <xref:System.ComponentModel.IBindingList.ListChanged> eventos do tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> por meio de seu <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> propriedade.  
  
    > [!NOTE]
    >  Você deve implementar o <xref:System.ComponentModel.IRaiseItemChangedEvents> se sua fonte de dados fornece a propriedade para listar a conversão do evento descrito anteriormente e está interagindo com o <xref:System.Windows.Forms.BindingSource> componente. Caso contrário, o <xref:System.Windows.Forms.BindingSource> também realizará a propriedade para listar a conversão do evento resultando em desempenho mais lento.  
  
-   <xref:System.ComponentModel.ISupportInitialize> Interface  
  
     Um componente que implementa o <xref:System.ComponentModel.ISupportInitialize> interface se beneficia das otimizações de lote para definir propriedades e inicializar propriedades codependentes. O <xref:System.ComponentModel.ISupportInitialize> contém dois métodos:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> sinaliza que a inicialização do objeto está sendo iniciada.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> sinaliza que a inicialização do objeto está sendo finalizada.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification> Interface  
  
     Um componente que implementa o <xref:System.ComponentModel.ISupportInitializeNotification> interface também implementa o <xref:System.ComponentModel.ISupportInitialize> interface. Essa interface permite notificar outros <xref:System.ComponentModel.ISupportInitialize> componentes que a inicialização for concluída. O <xref:System.ComponentModel.ISupportInitializeNotification> interface contém dois membros:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> Retorna um `boolean` valor que indica se o componente é inicializado.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> ocorre quando <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> é chamado.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged> Interface  
  
     Uma classe que implementa essa interface é um tipo que aciona um evento quando qualquer um dos seus valores de propriedade são alterados. Essa interface foi projetada para substituir o padrão de ter um evento de alteração para cada propriedade de um controle. Quando usado em uma <xref:System.ComponentModel.BindingList%601>, um objeto comercial deve implementar a <xref:System.ComponentModel.INotifyPropertyChanged> interface e a BindingList\`1 converterá <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventos a serem <xref:System.ComponentModel.BindingList%601.ListChanged> eventos do tipo <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  Para alterar notificação ocorra em uma associação entre um cliente associado e dados de um tipo de fonte de sua fonte de dados associado deve implementar o <xref:System.ComponentModel.INotifyPropertyChanged> interface (preferido) ou você pode fornecer *propertyName* `Changed` eventos para o tipo associado, mas você não devem fazer ambos.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>Interfaces para implementação por autores de componentes  
 As seguintes interfaces são projetadas para consumo pelo mecanismo de associação de dados dos Windows Forms:  
  
-   <xref:System.Windows.Forms.IBindableComponent> Interface  
  
     Uma classe que implementa essa interface é um componente de não controle que dá suporte à vinculação de dados. Essa classe retorna as associações de dados e o contexto de associação do componente através do <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> e <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> propriedades dessa interface.  
  
    > [!NOTE]
    >  Se seu componente herda <xref:System.Windows.Forms.Control>, você não precisa implementar o <xref:System.Windows.Forms.IBindableComponent> interface.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider> Interface  
  
     Uma classe que implementa o <xref:System.Windows.Forms.ICurrencyManagerProvider> interface é um componente que fornece sua própria <xref:System.Windows.Forms.CurrencyManager> para gerenciar as associações relacionadas a esse componente específico. Acesso a personalizado <xref:System.Windows.Forms.CurrencyManager> é fornecido pelo <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> propriedade.  
  
    > [!NOTE]
    >  Uma classe que herda de <xref:System.Windows.Forms.Control> gerencia automaticamente por meio de associações seus <xref:System.Windows.Forms.Control.BindingContext%2A> propriedade, portanto, casos em que você precisa implementar o <xref:System.Windows.Forms.ICurrencyManagerProvider> são relativamente raros.  
  
## <a name="see-also"></a>Consulte também
- [Vinculação de dados e os Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
- [Como: Criar um controle associado simples em um formulário do Windows](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Associação de dados do Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
