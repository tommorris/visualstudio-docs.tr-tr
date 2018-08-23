---
title: GetReferenceAssemblyPaths görevi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 178ef49c-5dee-405b-a14b-a37f41dc0609
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 619a533e1bdbdec00e631aac64d6ddf84bf161c6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630666"
---
# <a name="getreferenceassemblypaths-task"></a>GetReferenceAssemblyPaths Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [GetReferenceAssemblyPaths görevi](https://docs.microsoft.com/visualstudio/msbuild/getreferenceassemblypaths-task).  
  
  
Başvuru bütünleştirilmiş kodu yolları çeşitli çerçevesini döndürür.  
  
## <a name="parameters"></a>Parametreler  
 Parametreleri aşağıdaki tabloda açıklanmıştır `GetReferenceAssemblyPaths` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`ReferenceAssemblyPaths`|İsteğe bağlı `String[]` çıkış parametresi.<br /><br /> Temel yolunu döndürür `TargetFrameworkMoniker` parametresi. Varsa `TargetFrameworkMoniker` null veya boş, bu yolu olacak `String.Empty`.|  
|`FullFrameworkReferenceAssemblyPaths`|İsteğe bağlı `String[]` çıkış parametresi.<br /><br /> Temel yolunu döndürür `TargetFrameworkMoniker` ad profili bölümünü dikkate almadan parametresi. Varsa `TargetFrameworkMoniker` null veya boş, bu yolu olacak `String.Empty`.|  
|`TargetFrameworkMoniker`|İsteğe bağlı `String` parametresi.<br /><br /> Başvuru bütünleştirilmiş kodu yolları ile ilişkili olan hedef çerçeve adını belirtir.|  
|`RootPath`|İsteğe bağlı `String` parametresi.<br /><br /> Başvuru bütünleştirilmiş kod yolu oluşturmak için kullanılacak kök yolunu belirtir.|  
|`BypassFrameworkInstallChecks`|İsteğe bağlı [Boolean] (<!-- TODO: review code entity reference <xref:assetId:///Boolean?qualifyHint=False&amp;autoUpgrade=True>  -->) parametre.<br /><br /> Varsa `true`, temel denetimler atlar, `GetReferenceAssemblyPaths` belirli çalışma zamanı çerçeveleri, hedef Framework'ü bağlı olarak yüklendiğinden emin olmak için varsayılan olarak gerçekleştirir.|  
|`TargetFrameworkMonikerDisplayName`|İsteğe bağlı `String` çıkış parametresi.<br /><br /> Hedef Çerçeve adı için görünen adları belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tabloda listelenen parametreleri sahip olmaya ek olarak, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)



