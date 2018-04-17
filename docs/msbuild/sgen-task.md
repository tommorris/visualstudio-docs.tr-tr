---
title: SGen görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#SGen
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SGen task [MSBuild]
- MSBuild, SGen task
ms.assetid: 22c5ade4-4159-4667-b891-0c1aa06f4df5
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6e12f27eac0bdbf4a556db7292427d1487d4128
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="sgen-task"></a>SGen Görevi
XML serileştirme bütünleştirilmiş türleri için belirtilen derlemedeki oluşturur. Bu görev XML seri hale getirici Oluşturma Aracı (Sgen.exe) sarmalar. Daha fazla bilgi için bkz: [XML seri hale getirici Oluşturma Aracı (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `SGen` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`BuildAssemblyName`|Gerekli `String` parametresi.<br /><br /> Seri hale getirme kodunu oluşturmak için derleme.|  
|`BuildAssemblyPath`|Gerekli `String` parametresi.<br /><br /> Seri hale getirme kodunu oluşturmak için derleme yolu.|  
|`DelaySign`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, tam imzalı bir derleme istediğinizi belirtir. Varsa `false`, yalnızca ortak anahtar derlemede yerleştirmek istediğinizi belirtir.<br /><br /> Bu parametre ile birlikte kullanılan sürece herhangi bir etkisi olmaz `KeyFile` veya `KeyContainer` parametresi.|  
|`KeyContainer`|İsteğe bağlı `String` parametresi.<br /><br /> Anahtar çifti içeren bir kapsayıcıyı belirtir. Derleme bildirimi bir ortak anahtar ekleyerek bu derlemeyi imzalar. Görev, sonra son derlemeyi özel anahtarla imzalar.|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Bir anahtar çifti ya da bir ortak anahtar derlemeyi imzalamak için kullanılacağını belirtir. Derleyici ortak anahtarı derleme bildirimine ekler ve ardından son derlemeyi özel anahtarla imzalar.|  
|`Platform`|İsteğe bağlı `String` parametresi.<br /><br /> Alır veya çıkış derlemesi oluşturmak için kullanılan derleyici Platform ayarlar. Bu parametre değerini olabilir `x86`, `x64`, veya `anycpu`. Varsayılan değer `anycpu`.|  
|`References`|İsteğe bağlı `String[]` parametresi.<br /><br /> XML serileştirme gerektiren türleri tarafından başvurulan bir derleme belirtir.|  
|`SdkToolsPath`|İsteğe bağlı `String` parametresi.<br /><br /> Resgen.exe gibi SDK Araçları yolunu belirtir.|  
|`SerializationAssembly`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Oluşturulan seri hale getirme derlemesi içerir.|  
|`SerializationAssemblyName`|İsteğe bağlı `String` parametresi.<br /><br /> Oluşturulan serileştirme bütünleştirilmiş kodun adını belirtir.|  
|`ShouldGenerateSerializer`|Gerekli `Boolean` parametresi.<br /><br /> Varsa `true`, SGen görevi seri hale getirme derlemesi oluşturmak.|  
|`Timeout`|İsteğe bağlı `Int32` parametresi.<br /><br /> Süresini, daha sonra çalıştırılabilir görev sonlandırıldığından milisaniye cinsinden belirtir. Varsayılan değer `Int.MaxValue`, hiçbir zaman aşımı süresi olduğunu gösterir.|  
|`ToolPath`|İsteğe bağlı `String` parametresi.<br /><br /> Görev temel yürütülebilir dosya (sgen.exe) burada yükler konumdaki belirtir. Bu parametre belirtilmezse, görevin çalıştığı framework sürümüne karşılık gelen SDK yükleme yolunu kullanır [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)].|  
|`Types`|İsteğe bağlı `String[]` parametresi.<br /><br /> Alır veya seri hale getirme kodunu oluşturmak için belirli türlerinin bir listesini ayarlar. SGen yalnızca bu türleri için seri hale getirme kodu oluşturur.|  
|`UseProxyTypes`|Gerekli `Boolean` parametresi.<br /><br /> Varsa `true`, SGen görevi yalnızca XML Web hizmeti proxy türleri için seri hale getirme kod oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.ToolTaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.ToolTask> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [ToolTaskExtension taban sınıfı](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Görevler](../msbuild/msbuild-tasks.md)   
 [MSBuild Kavramları](../msbuild/msbuild-concepts.md)