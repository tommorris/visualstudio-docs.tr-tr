---
title: "Artımlı derlemeler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- msbuild, incremental builds
ms.assetid: 325e28c7-4838-4e3f-b672-4586adc7500c
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: ee1e8a136937b1291950a9df71b93a1e5c90f8c2
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="incremental-builds"></a>Artımlı Derlemeler
Artımlı derlemeler en iyi duruma getirilir ve böylece ilgili giriş dosyalarına göre güncel çıkış dosyalarınız hedefleri yürütülmez derlemeleri ' dir. Hedef öğe hem de sahip olabilir bir `Inputs` hangi hedef öğeler belirten özniteliği giriş olarak bekliyor ve bir `Outputs` hangi üretir çıkış olarak öğeler belirten özniteliği. MSBuild, bu öznitelik değerleri 1-1 eşlemesini bulmaya çalışır. 1-1 eşleme varsa, MSBuild giriş her zaman damgasını öğesine karşılık gelen kendi çıktı öğenin zaman damgasını karşılaştırır. 1-1 eşleme çıkış dosyaları için tüm giriş dosyaları karşılaştırılır. Kendi çıktı dosyasını aynı yaş ise güncel ya da kendi giriş dosya veya dosyalar daha yeni bir öğe olarak kabul edilir.  
  
 Tüm çıktı öğeleri güncel olup olmadığını MSBuild hedef atlar. Bu *Artımlı derleme* hedefi yapı hızı önemli ölçüde artırabilir. Yalnızca bazı dosyaları güncel MSBuild hedef yürütür ancak güncel öğeleri atlar ve dolayısıyla tüm öğeleri güncel getirir. Bu olarak bilinen bir *kısmi Artımlı derleme*.  
  
 1-1 eşlemeleri genellikle öğesi dönüşümleri tarafından oluşturulur. Daha fazla bilgi için bkz: [dönüştüren](../msbuild/msbuild-transforms.md).  
  
 Aşağıdaki hedef göz önünde bulundurun.  
  
```xml  
<Target Name="Backup" Inputs="@(Compile)"   
    Outputs="@(Compile->'$(BackupFolder)%(Identity).bak')">  
    <Copy SourceFiles="@(Compile)" DestinationFiles=  
        "@(Compile->'$(BackupFolder)%(Identity).bak')" />  
</Target>  
```  
  
 Tarafından temsil edilen dosyaları kümesini `Compile` öğesi türü bir yedekleme dizinine kopyalanır. Yedekleme dosyaları .bak dosya adı uzantısına sahiptir. Dosyaları tarafından temsil edilen varsa `Compile` öğesi türü ya da ilgili yedekleme dosyalarının değil silinmiş veya yedekleme hedef çalıştırıldıktan sonra yedekleme hedef sonraki derlemelerde atlanır sonra değiştirildi.  
  
## <a name="output-inference"></a>Çıktı çıkarımı  
 MSBuild karşılaştırır `Inputs` ve `Outputs` hedef yürütmek olup olmadığını belirlemek için bir hedef öznitelikleri. İdeal olarak, ilişkili hedefleri yürütülen olup olmadığına bakılmaksızın bir artımlı yapı tamamlandıktan sonra mevcut dosyaları kümesini aynı kalması gerekir. Özellikleri ve oluşturulan veya görevler tarafından değiştirilmiş öğeleri yapı etkileyebileceğinden, bunları etkiler hedef atlanır olsa bile MSBuild değerlerine Infer gerekir. Bu olarak bilinir *çıkış çıkarım*.  
  
 Üç durum vardır:  
  
-   Hedef bir `Condition` değerlendiren özniteliği `false`. Bu durumda, hedef değil çalıştırın ve yapı üzerinde hiçbir etkisi olmaz.  
  
-   Hedef güncel çıkışları sahiptir ve bunları güncel duruma getirmek için çalıştırın.  
  
-   Hedef güncel çıkış var ve atlanır. MSBuild hedef değerlendirir ve hedef çalıştırmak gibi değişiklikler öğeleri ve özelliklerini yapar.  
  
 Artımlı derleme desteklemek için görevler emin olmanız gerekir `TaskParameter` öznitelik değeri herhangi `Output` öğesi görev giriş parametresi olarak eşittir. Bazı örnekler şunlardır:  
  
```xml  
<CreateProperty Value="123">  
    <Output PropertyName="Easy" TaskParameter="Value" />  
</CreateProperty>  
```  
  
 Bu özellik desteklemediğini hedef yürütülen Atlanan veya değer "123" kolay oluşturur.  
  
```xml  
<CreateItem Include="a.cs;b.cs">  
    <Output ItemName="Simple" TaskParameter="Include" />  
</CreateItem>  
```  
  
 Bu öğe türü hedef yürütülen veya atlandı olsun veya olmasın olan iki öğe, "a.cs" ve "b.cs" Basit oluşturur.  
  
 MSBuild 3. 5'ten başlayarak, çıktı çıkarım, bir hedef öğe ve özellik grupları otomatik olarak gerçekleştirilir. `CreateItem`görevler bir hedef gerekli değildir ve kaçınılmalıdır. Ayrıca, `CreateProperty` görevler yalnızca bir hedef gerçekleştirilip gerçekleştirilmediğini belirlemek için bir hedef olarak kullanılmalıdır.  
  
## <a name="determining-whether-a-target-has-been-run"></a>Bir hedef çalıştırılıp çalıştırılmadığını belirleme  
 Çıktı çıkarım nedeniyle eklemek zorunda bir `CreateProperty` Görev hedef gerçekleştirilip gerçekleştirilmediğini belirleyebilmesi özellikleri ve öğelerini incelemek için bir hedef. Ekleme `CreateProperty` görev için hedef ve şablona bir `Output` öğesi, `TaskParameter` "ValueSetByTask" olan.  
  
```xml  
<CreateProperty Value="true">  
    <Output TaskParameter="ValueSetByTask" PropertyName="CompileRan" />  
</CreateProperty>  
```  
  
 Bu özellik CompileRan oluşturur ve değeri verir `true`, ancak yalnızca hedef yürütülürse. Hedef atladıysanız CompileRan oluşturulmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefler](../msbuild/msbuild-targets.md)