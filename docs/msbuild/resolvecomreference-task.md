---
title: "ResolveComReference görevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#ResolveComReference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveCOMReference task
- ResolveCOMReference task [MSBuild]
ms.assetid: c9bf5fcf-6453-40ea-b50f-a212adc3e9b5
caps.latest.revision: "26"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: bb95d43af71a7860f239c56ab3db46a2e3c5e238
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="resolvecomreference-task"></a>ResolveComReference Görevi
Bir veya daha fazla tür kitaplığı adları ya da .tlb dosyaları listesini alır ve bu tür kitaplıklarının disk üzerindeki konumlara giderir.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `ResolveCOMReference` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`DelaySign`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, ortak anahtar derlemede yerleştirir. Varsa `false`, derleme tam olarak imzalar.|  
|`EnvironmentVariables`|İsteğe bağlı `String[]` parametresi.<br /><br /> Ortam değişkenleri, eşittir işaretiyle ayırarak çiftleri dizisi. Bu değişkenleri oluşturulan tlbimp.exe ve ek olarak aximp.exe geçirilir veya seçmeli olarak geçersiz kılma, normal ortamı engelle...|  
|`ExecuteAsTool`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, uygun hedef framework çıkış gerekli sarmalayıcı derlemeleri oluşturmak için işlem dışı tlbimp.exe ve aximp.exe çalışır. Bu parametre, çoklu sürüm desteği sağlar.|  
|`IncludeVersionInInteropName`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, kapsayıcı adlarında typelib sürümüne eklenecektir. Varsayılan, `false` değeridir.|  
|`KeyContainer`|İsteğe bağlı `String` parametresi.<br /><br /> Ortak/özel tutan kapsayıcı belirtir<br /><br /> anahtar çifti.|  
|`KeyFile`|İsteğe bağlı `String` parametresi.<br /><br /> Ortak/özel içeren bir öğeyi belirtir<br /><br /> anahtar çifti.|  
|`NoClassMembers`|İsteğe bağlı `Boolean`parametresi.|  
|`ResolvedAssemblyReferences`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Çözümlenen derleme başvurularını belirtir.|  
|`ResolvedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Bu görev için giriş olarak sağlanan tür kitaplıklarının fiziksel konumlara karşılık gelen tam disk dosyalarda belirtir.|  
|`ResolvedModules`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]`parametresi.|  
|`SdkToolsPath`|İsteğe bağlı <xref:System.String?displayProperty=fullName> parametresi.<br /><br /> Varsa `ExecuteAsTool` olan `true`, bu parametre, hedeflenen framework sürümü için SDK Araçları yola ayarlamanız gerekir.|  
|`StateFile`|İsteğe bağlı `String` parametresi.<br /><br /> COM bileşeni tarih damgası önbellek dosyası belirtir. Yoksa, her çalıştırma tüm sarmalayıcıları yeniden oluşturur.|  
|`TargetFrameworkVersion`|İsteğe bağlı `String` parametresi.<br /><br /> Proje hedef framework sürümünü belirtir.<br /><br /> Varsayılan, `String.Empty` değeridir. hangi hiçbir hedef framework temel alınarak bir başvuru filtreleme anlamına gelir.|  
|`TargetProcessorArchitecture`|İsteğe bağlı `String` parametresi.<br /><br /> Tercih edilen hedef işlemci mimarisini belirtir. Tlbimp.exe /machine bayrak sonra çeviri geçirildi.<br /><br /> Parametre değerinde bir üyesi olmalıdır <xref:Microsoft.Build.Utilities.ProcessorArchitecture>.|  
|`TypeLibFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> COM başvuruları için tür kitaplığı dosya yolunu belirtir. Bu parametrede dahil öğeler öğe meta verileri içerebilir. Daha fazla bilgi için "TypeLibFiles öğe meta verileri" aşağıdaki bölümüne bakın.|  
|`TypeLibNames`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Tür kitaplığı adları çözümlemek için belirtir. Bu parametrede dahil öğeleri bazı öğe meta verileri içermelidir. Daha fazla bilgi için "TypeLibNames öğe meta verileri" aşağıdaki bölümüne bakın.|  
|`WrapperOutputDirectory`|İsteğe bağlı `String` parametresi.<br /><br /> Oluşturulan birlikte çalışma derleme yerleştirildiği konum disk üzerinde. Bu öğe meta verisi belirtilmezse, görev proje dosyasının bulunduğu dizininin mutlak yolu kullanır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="typelibnames-item-metadata"></a>TypeLibNames öğe meta verileri  
 Geçirilen öğeler için kullanılabilir öğe meta verileri aşağıdaki tabloda açıklanmaktadır `TypeLibNames` parametresi.  
  
|Meta Veriler|Açıklama|  
|--------------|-----------------|  
|`GUID`|Gerekli öğe meta verileri.<br /><br /> Tür kitaplığı için GUID. Bu öğe meta verisi belirtilmezse, görev başarısız olur.|  
|`VersionMajor`|Gerekli öğe meta verileri.<br /><br /> Tür kitaplığı ana sürümü. Bu öğe meta verisi belirtilmezse, görev başarısız olur.|  
|`VersionMinor`|Gerekli öğe meta verileri.<br /><br /> Tür kitaplığı küçük sürümü. Bu öğe meta verisi belirtilmezse, görev başarısız olur.|  
|`LocaleIdentifier`|İsteğe bağlı öğe meta verileri.<br /><br /> Yerel ayar tanımlayıcısı (veya LCID) için tür kitaplığı. Bu, bir kullanıcı, bölge veya uygulama tarafından tercih edilen İnsan dil tanımlayan 32 bitlik bir değer olarak belirtilir. Bu öğe meta verisi belirtilmezse, görevin varsayılan yerel ayar tanıtıcısını "0" kullanır.|  
|`WrapperTool`|İsteğe bağlı öğe meta verileri.<br /><br /> Bu tür kitaplığını derleme sarmalayıcı oluşturmak için kullanılan sarmalayıcı aracı belirtir. Bu öğe meta verisi belirtilmezse, görev bir varsayılan sarmalayıcı aracı "tlbimp" kullanır. TypeLib kullanılabilir, büyük küçük harfe duyarlı seçenekler şunlardır:<br /><br /> -   `Primary`: COM bileşeni için önceden oluşturulmuş bir birincil birlikte çalışma derlemesi kullanmak istediğinizde bu sarmalayıcı aracı kullanın. Bu sarmalayıcı aracını kullandığınızda, görev başarısız olmasına neden olacağından bir sarmalayıcı çıktı dizini belirtmeyin.<br />-   `TLBImp`: COM birlikte çalışma bir derlemesini oluşturmak istediğinizde bu sarmalayıcı aracı kullanın.<br />-   `AXImp`: Bir ActiveX denetimi için birlikte çalışma derlemeyi oluşturmak istediğinizde bu sarmalayıcı aracı kullanın.|  
  
## <a name="typelibfiles-item-metadata"></a>TypeLibFiles öğe meta verileri  
 Geçirilen öğeler için kullanılabilir öğe meta verileri aşağıdaki tabloda açıklanmaktadır `TypeLibFiles` parametresi.  
  
|Meta Veriler|Açıklama|  
|--------------|-----------------|  
|`WrapperTool`|İsteğe bağlı öğe meta verileri.<br /><br /> Bu tür kitaplığını derleme sarmalayıcı oluşturmak için kullanılan sarmalayıcı aracı belirtir. Bu öğe meta verisi belirtilmezse, görev bir varsayılan sarmalayıcı aracı "tlbimp" kullanır. TypeLib kullanılabilir, büyük küçük harfe duyarlı seçenekler şunlardır:<br /><br /> -   `Primary`: COM bileşeni için önceden oluşturulmuş bir birincil birlikte çalışma derlemesi kullanmak istediğinizde bu sarmalayıcı aracı kullanın. Bu sarmalayıcı aracını kullandığınızda, görev başarısız olmasına neden olacağından bir sarmalayıcı çıktı dizini belirtmeyin.<br />-   `TLBImp`: COM birlikte çalışma bir derlemesini oluşturmak istediğinizde bu sarmalayıcı aracı kullanın.<br />-   `AXImp`: Bir ActiveX denetimi için birlikte çalışma derlemeyi oluşturmak istediğinizde bu sarmalayıcı aracı kullanın.|  
  
> [!NOTE]
>  Görev diskteki doğru dosyaya çözümleyecek olasılığı daha büyük bir tür kitaplığı benzersiz şekilde tanımlamak için sağladığınız daha fazla bilgi.  
  
## <a name="remarks"></a>Açıklamalar  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [görev taban sınıfı](../msbuild/task-base-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)