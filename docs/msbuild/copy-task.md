---
title: Kopyalama görevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Copy
- MSBuild.Copy.SourceFileNotFound
- MSBuild.Copy.Retrying
- MSBuild.Copy.ExceededRetries
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, Copy task
- Copy task [MSBuild]
ms.assetid: a46ba9da-3e4e-4890-b4ea-09a099b6bc40
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1cd3f7e6c5075ad024e227c847ff05f186f7b016
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="copy-task"></a>Kopyalama Görevi
Dosyaları, dosya sisteminde yeni bir konuma kopyalar.  
  
## <a name="parameters"></a>Parametreler  
 Aşağıdaki tabloda parametrelerinin açıklanmaktadır `Copy` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`CopiedFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` çıkış parametresi.<br /><br /> Başarılıyla kopyalanan öğeleri içerir.|  
|`DestinationFiles`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Kaynak dosyaların kopyalanacağı dosyaların listesini belirtir. Bu listenin, `SourceFiles` parametresinde belirtilen liste ile bire bir eşlenir olması beklenir. Yani, `SourceFiles` içinde belirtilen ilk dosya `DestinationFiles` içinde belirtilen ilk konuma kopyalanır ve böyle devam eder.|  
|`DestinationFolder`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Dosyaları kopyalamak istediğiniz dizini belirtir. Bu, bir dosya değil, bir dizin olmalıdır. Eğer dizin yoksa otomatik olarak oluşturulur.|  
|`OverwriteReadOnlyFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Salt okunur dosyalar olarak işaretlenmiş olsa bile dosyaların üzerine yaz|  
|`Retries`|İsteğe bağlı `Int32` parametresi.<br /><br /> Eğer önceki tüm denemeler başarısız olursa, kopyalamanın kaç kere deneneceğini belirtir. Varsayılan olarak sıfırdır.<br /><br /> **Not:** yeniden deneme kullanımını yapı işleminizin bir eşitleme sorun maskeleyebilirsiniz.|  
|`RetryDelayMilliseconds`|İsteğe bağlı `Int32` parametresi.<br /><br /> Gerekli yeniden denemeler arasındaki gecikmeyi belirtir. Varsayılan olarak, CopyTask oluşturucusuna geçirilen RetryDelayMillisecondsDefault değerini kullanır.|  
|`SkipUnchangedFiles`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Eğer `true` ise, kaynak ve hedef arasında değişmeyen dosyaların kopyalanmasını atlar. `Copy` görevi, dosyalar aynı boyuta ve aynı son değiştirme tarihine sahipse bu dosyaları değişmemiş kabul eder. **Not:** bu parametreyi ayarlarsanız verilen `true`, yalnızca görev varsa çalıştığından, Bağımlılık çözümlemesini içeren hedef sunucuda kullanmamalısınız son değiştirilen kaynak dosyalarını sürelerinin son değiştirilen yeni sürelerinin hedef dosyalar.|  
|`SourceFiles`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem>`[]` parametresi.<br /><br /> Kopyalanacak dosyaları belirtir.|  
|`UseHardlinksIfPossible`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Eğer `true` ise, dosyaları kopyalamak yerine kopyalanan dosyalar için Sabit Bağlantılar oluşturur.|  
  
## <a name="warnings"></a>Uyarılar  
 Uyarılar dahil olmak üzere kaydedilir:  
  
-   `Copy.DestinationIsDirectory`  
  
-   `Copy.SourceIsDirectory`  
  
-   `Copy.SourceFileNotFound`  
  
-   `Copy.CreatesDirectory`  
  
-   `Copy.HardLinkComment`  
  
-   `Copy.RetryingAsFileCopy`  
  
-   `Copy.FileComment`  
  
-   `Copy.RemovingReadOnlyAttribute`  
  
## <a name="remarks"></a>Açıklamalar  
 `DestinationFolder` veya `DestinationFiles` parametresinin belirtilmesi gerekir, ancak ikisi birden belirtilmemelidir. Eğer her ikisi de belirtilirse görev başarısız olur ve bir hata günlüğe kaydedilir.  
  
 Yukarıda listelenen parametreleri ek olarak, bu görev parametrelerinden devralır <xref:Microsoft.Build.Tasks.TaskExtension> sınıfı, kendisi <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametreler ve açıklamalarının listesi için bkz: [TaskExtension taban sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, `MySourceFiles` öğe koleksiyonundaki öğeleri c:\MyProject\Destination klasörüne kopyalar.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceFiles Include="a.cs;b.cs;c.cs"/>  
    </ItemGroup>  
  
    <Target Name="CopyFiles">  
        <Copy  
            SourceFiles="@(MySourceFiles)"  
            DestinationFolder="c:\MyProject\Destination"  
        />  
    </Target>  
  
</Project>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, yinelemeli bir kopyalamanın nasıl gerçekleştirileceğini gösterir. Bu proje, dizin yapısını koruyarak c:\MySourceTree içindeki tüm dosyaları yinelemeli bir şekilde c:\MyDestinationTree içine kopyalar.  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MySourceFiles Include="c:\MySourceTree\**\*.*"/>  
    </ItemGroup>  
  
    <Target Name="CopyFiles">  
        <Copy  
            SourceFiles="@(MySourceFiles)"  
            DestinationFiles="@(MySourceFiles->'c:\MyDestinationTree\%(RecursiveDir)%(Filename)%(Extension)')"  
        />  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevler](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)