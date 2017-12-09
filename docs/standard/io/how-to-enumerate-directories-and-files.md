---
title: "Como enumerar diretórios e arquivos"
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
helpviewer_keywords: I/O [.NET Framework], enumerating directories and files
ms.assetid: 86b69a08-3bfa-4e5f-b4e1-3b7cb8478215
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: caf9bdec017a5466269ff7fe97be4d0243035b4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enumerate-directories-and-files"></a><span data-ttu-id="44405-102">Como enumerar diretórios e arquivos</span><span class="sxs-lookup"><span data-stu-id="44405-102">How to: Enumerate Directories and Files</span></span>
<span data-ttu-id="44405-103">Você pode enumerar diretórios e arquivos usando métodos que retornam uma coleção enumerável de cadeias de caracteres de seus nomes.</span><span class="sxs-lookup"><span data-stu-id="44405-103">You can enumerate directories and files by using methods that return an enumerable collection of strings of their names.</span></span> <span data-ttu-id="44405-104">Você também pode usar os métodos que retornam uma coleção enumerável de <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, ou <xref:System.IO.FileSystemInfo> objetos.</span><span class="sxs-lookup"><span data-stu-id="44405-104">You can also use methods that return an enumerable collection of <xref:System.IO.DirectoryInfo>, <xref:System.IO.FileInfo>, or <xref:System.IO.FileSystemInfo> objects.</span></span> <span data-ttu-id="44405-105">Coleções enumeráveis fornecem desempenho melhor que matrizes ao trabalhar com grandes coleções de arquivos e diretórios.</span><span class="sxs-lookup"><span data-stu-id="44405-105">Enumerable collections provide better performance than arrays when you work with large collections of directories and files.</span></span>  
  
 <span data-ttu-id="44405-106">Você também pode usar coleções enumeráveis obtidas desses métodos para fornecer a <xref:System.Collections.Generic.IEnumerable%601> parâmetro para construtores de coleção de classes, como o <xref:System.Collections.Generic.List%601> classe.</span><span class="sxs-lookup"><span data-stu-id="44405-106">You can also use enumerable collections obtained from these methods to supply the <xref:System.Collections.Generic.IEnumerable%601> parameter for constructors of collection classes such as the <xref:System.Collections.Generic.List%601> class.</span></span>  
  
 <span data-ttu-id="44405-107">Se você quiser obter somente os nomes de arquivos ou diretórios, use os métodos de enumeração do <xref:System.IO.Directory> classe.</span><span class="sxs-lookup"><span data-stu-id="44405-107">If you want to obtain only the names of directories or files, use the enumeration methods of the <xref:System.IO.Directory> class.</span></span> <span data-ttu-id="44405-108">Se você quiser obter outras propriedades de arquivos ou diretórios, use o <xref:System.IO.DirectoryInfo> e <xref:System.IO.FileSystemInfo> classes.</span><span class="sxs-lookup"><span data-stu-id="44405-108">If you want to obtain other properties of directories or files, use the <xref:System.IO.DirectoryInfo> and <xref:System.IO.FileSystemInfo> classes.</span></span>  
  
 <span data-ttu-id="44405-109">A tabela a seguir fornece um guia para os métodos que retornam coleções enumeráveis.</span><span class="sxs-lookup"><span data-stu-id="44405-109">The following table provides a guide to the methods that return enumerable collections.</span></span>  
  
|<span data-ttu-id="44405-110">Para enumerar</span><span class="sxs-lookup"><span data-stu-id="44405-110">To enumerate</span></span>|<span data-ttu-id="44405-111">Coleção enumerável para retornar</span><span class="sxs-lookup"><span data-stu-id="44405-111">Enumerable collection to return</span></span>|<span data-ttu-id="44405-112">Método a ser usado</span><span class="sxs-lookup"><span data-stu-id="44405-112">Method to use</span></span>|  
|------------------|-------------------------------------|-------------------|  
|<span data-ttu-id="44405-113">Diretórios</span><span class="sxs-lookup"><span data-stu-id="44405-113">Directories</span></span>|<span data-ttu-id="44405-114">Nomes de diretório</span><span class="sxs-lookup"><span data-stu-id="44405-114">Directory names</span></span>|<xref:System.IO.Directory.EnumerateDirectories%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="44405-115">Informações de diretório (<xref:System.IO.DirectoryInfo>)</span><span class="sxs-lookup"><span data-stu-id="44405-115">Directory information (<xref:System.IO.DirectoryInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44405-116">Arquivos</span><span class="sxs-lookup"><span data-stu-id="44405-116">Files</span></span>|<span data-ttu-id="44405-117">Nomes de arquivo</span><span class="sxs-lookup"><span data-stu-id="44405-117">File names</span></span>|<xref:System.IO.Directory.EnumerateFiles%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="44405-118">Arquivo de informações (<xref:System.IO.FileInfo>)</span><span class="sxs-lookup"><span data-stu-id="44405-118">File information (<xref:System.IO.FileInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="44405-119">Informações do sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="44405-119">File system information</span></span>|<span data-ttu-id="44405-120">Entradas do arquivo de sistema</span><span class="sxs-lookup"><span data-stu-id="44405-120">File system entries</span></span>|<xref:System.IO.Directory.EnumerateFileSystemEntries%2A?displayProperty=nameWithType>|  
||<span data-ttu-id="44405-121">Informações do sistema de arquivos (<xref:System.IO.FileSystemInfo>)</span><span class="sxs-lookup"><span data-stu-id="44405-121">File system information (<xref:System.IO.FileSystemInfo>)</span></span>|<xref:System.IO.DirectoryInfo.EnumerateFileSystemInfos%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="44405-122">Embora você pode enumerar imediatamente todos os arquivos nos subdiretórios de um diretório pai usando o <xref:System.IO.SearchOption.AllDirectories> pesquisar opção fornecida pelo <xref:System.IO.SearchOption> enumeração, as exceções de acesso não autorizado (<xref:System.UnauthorizedAccessException>) pode fazer com que a enumeração de pode estar incompleta.</span><span class="sxs-lookup"><span data-stu-id="44405-122">Although you can immediately enumerate all the files in the subdirectories of a parent directory by using the <xref:System.IO.SearchOption.AllDirectories> search option provided by the <xref:System.IO.SearchOption> enumeration, unauthorized access exceptions (<xref:System.UnauthorizedAccessException>) may cause the enumeration to be incomplete.</span></span> <span data-ttu-id="44405-123">Se essas exceções são possíveis, você pode capturá-los e continuar primeiro enumerando diretórios e, em seguida, enumera arquivos.</span><span class="sxs-lookup"><span data-stu-id="44405-123">If these exceptions are possible, you can catch them and continue by first enumerating directories and then enumerating files.</span></span>  
  
### <a name="to-enumerate-directory-names"></a><span data-ttu-id="44405-124">Para enumerar os nomes de diretório</span><span class="sxs-lookup"><span data-stu-id="44405-124">To enumerate directory names</span></span>  
  
-   <span data-ttu-id="44405-125">Use o <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> método para obter uma lista dos nomes de diretório de nível superior em um caminho especificado.</span><span class="sxs-lookup"><span data-stu-id="44405-125">Use the <xref:System.IO.Directory.EnumerateDirectories%28System.String%29?displayProperty=nameWithType> method to obtain a list of the top-level directory names in a specified path.</span></span>  
  
     [!code-csharp[System.IO.EnumDirs1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.enumdirs1/cs/program.cs#1)]
     [!code-vb[System.IO.EnumDirs1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.enumdirs1/vb/program.vb#1)]  
  
### <a name="to-enumerate-file-names-in-a-directory-and-subdirectories"></a><span data-ttu-id="44405-126">Para enumerar os nomes de arquivo em um diretório e subdiretórios</span><span class="sxs-lookup"><span data-stu-id="44405-126">To enumerate file names in a directory and subdirectories</span></span>  
  
-   <span data-ttu-id="44405-127">Use o <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> método para pesquisar um diretório e (opcionalmente) seus subdiretórios e para obter uma lista de nomes de arquivos que correspondem a um padrão de pesquisa especificados.</span><span class="sxs-lookup"><span data-stu-id="44405-127">Use the <xref:System.IO.Directory.EnumerateFiles%28System.String%2CSystem.String%2CSystem.IO.SearchOption%29?displayProperty=nameWithType> method to search a directory and (optionally) its subdirectories, and to obtain a list of file names that match a specified search pattern.</span></span>  
  
     [!code-csharp[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/cs/program.cs#1)]
     [!code-vb[System.IO.Directory.EnumerateFiles#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directory.enumeratefiles/vb/program.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-directoryinfo-objects"></a><span data-ttu-id="44405-128">Para enumerar uma coleção de objetos DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="44405-128">To enumerate a collection of DirectoryInfo objects</span></span>  
  
-   <span data-ttu-id="44405-129">Use o <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> método para obter uma coleção de pastas de nível superior.</span><span class="sxs-lookup"><span data-stu-id="44405-129">Use the <xref:System.IO.DirectoryInfo.EnumerateDirectories%2A?displayProperty=nameWithType> method to obtain a collection of top-level directories.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumDirs#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumdirs/vb/module1.vb#1)]  
  
### <a name="to-enumerate-a-collection-of-fileinfo-objects-in-all-directories"></a><span data-ttu-id="44405-130">Para enumerar uma coleção de objetos FileInfo em todos os diretórios</span><span class="sxs-lookup"><span data-stu-id="44405-130">To enumerate a collection of FileInfo objects in all directories</span></span>  
  
-   <span data-ttu-id="44405-131">Use o <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> método para obter uma coleção de arquivos que correspondem a um padrão de pesquisa especificada em todos os diretórios.</span><span class="sxs-lookup"><span data-stu-id="44405-131">Use the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A?displayProperty=nameWithType> method to obtain a collection of files that match a specified search pattern in all directories.</span></span> <span data-ttu-id="44405-132">Este exemplo enumera primeiro as pastas de nível superior para capturar exceções de acesso não autorizado possíveis e, em seguida, enumera os arquivos.</span><span class="sxs-lookup"><span data-stu-id="44405-132">This example first enumerates the top-level directories to catch possible unauthorized access exceptions, and then enumerates the files.</span></span>  
  
     [!code-csharp[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/cs/program.cs#1)]
     [!code-vb[System.IO.DirectoryInfo.EnumerateDirectories#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.directoryinfo.enumeratedirectories/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="44405-133">Consulte também</span><span class="sxs-lookup"><span data-stu-id="44405-133">See Also</span></span>  
 [<span data-ttu-id="44405-134">E/S de arquivo e de fluxo</span><span class="sxs-lookup"><span data-stu-id="44405-134">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)