---
title: Hedef derleme sırası | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, build order
ms.assetid: f4a26339-9f9a-497a-9aa6-0797183d450d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 30bd83819dcbfd4423c399c42aeb518a1d11e6e9
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844189"
---
# <a name="target-build-order"></a>Hedef Derleme Sırası
Bir hedef girdisi başka bir hedef Çıkışta bağımlıysa hedefleri sıralanmalıdır. Bu öznitelikler hedefleri çalıştığı sırayı belirtmek için kullanabilirsiniz:  
  
-   `InitialTargets`. Bu `Project` özniteliği belirtir önce çalışacak hedefleri hedefleri komut satırında veya belirtilmese bile `DefaultTargets` özniteliği.  
  
-   `DefaultTargets`. Bu `Project` atttribute belirtir hangi hedefleri çalıştıran bir hedef komut satırında açıkça belirtilmediği takdirde.  
  
-   `DependsOnTargets`. Bu `Target` özniteliği, bu hedef çalıştırmadan önce çalıştırmanız gereken hedefleri belirtir.  
  
-   `BeforeTargets` ve `AfterTargets`. Bunlar `Target` öznitelikleri belirtin Bu hedef önce veya sonra belirtilen hedefleri (MSBuild 4.0) çalıştırmalısınız.  
  
 Bir sonraki hedef derlemede bağımlı olsa bile bir hedef hiçbir zaman bir derleme sırasında iki kez çalıştırılır. Bir hedef çalıştırdığınızda, yapı katkısı tamamlanır.  
  
 Hedefleri olabilir bir `Condition` özniteliği. Belirtilen koşulu değerlendirilirse `false`, hedef yürütülen değil ve yapı üzerinde hiçbir etkisi olmaz. Koşullar hakkında daha fazla bilgi için bkz: [koşullar](../msbuild/msbuild-conditions.md).  
  
## <a name="initial-targets"></a>Başlangıç Hedefleri  
 `InitialTargets` Özniteliği [proje](../msbuild/project-element-msbuild.md) öğesi belirttiğinden önce çalışacak hedefleri hedefleri komut satırında veya belirtilmese bile `DefaultTargets` özniteliği. İlk hedefleri genellikle hata denetimi için kullanılır.  
  
 Değeri `InitialTargets` özniteliği noktalı virgülle ayrılmış, sıralı listesini hedefleri olabilir. Aşağıdaki örnek belirleyen `Warm` hedef çalıştığında ve ardından `Eject` hedef çalıştırır.  
  
```xml  
<Project InitialTargets="Warm;Eject" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
```  
  
 İçeri aktarılan projeleri olabilir, kendi `InitialTargets` öznitelikleri. Tüm ilk hedefleri birlikte toplanır ve sıra ile çalışır.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: belirtin, hedef yapı ilk](../msbuild/how-to-specify-which-target-to-build-first.md).  
  
## <a name="default-targets"></a>Varsayılan Hedefler  
 `DefaultTargets` Özniteliği [proje](../msbuild/project-element-msbuild.md) öğesi belirttiğinden hangi hedef veya hedefleri yerleşik bir hedef komut satırında açıkça belirtilmezse.  
  
 Değeri `DefaultTargets` özniteliği varsayılan hedefler noktalı virgülle ayrılmış, sıralı bir listesi olabilir. Aşağıdaki örnek belirleyen `Clean` hedef çalıştığında ve ardından `Build` hedef çalıştırır.  
  
```xml  
<Project DefaultTargets="Clean;Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
```  
  
 Kullanarak varsayılan hedefler kılabilirsiniz **/target** komut satırında geçin. Aşağıdaki örnek belirleyen `Build` hedef çalıştığında ve ardından `Report` hedef çalıştırır. Bu şekilde hedefleri belirttiğinizde, tüm varsayılan hedefleri göz ardı edilir.  
  
 `msbuild /target:Build;Report`  
  
 İlk hedefleri ve varsayılan hedefleri belirttiyseniz ve komut satırı hedefi belirtildiyse MSBuild ilk hedefleri ilk çalıştırır ve ardından varsayılan hedefler çalıştırır.  
  
 İçeri aktarılan projeleri olabilir, kendi `DefaultTargets` öznitelikleri. İlk `DefaultTargets` karşılaştı özniteliği hedefleri çalışacağı hangi varsayılan belirler.  
  
 Daha fazla bilgi için bkz: [nasıl yapılır: belirtin, hedef yapı ilk](../msbuild/how-to-specify-which-target-to-build-first.md).  
  
## <a name="first-target"></a>İlk Hedef  
 Varsa hiçbir ilk hedefler, varsayılan hedefler ya da komut satırı hedefleri ilk hedef MSBuild çalışır proje dosyası veya alınan tüm proje dosyalarını karşılaşır.  
  
## <a name="target-dependencies"></a>Hedef Bağımlılıklar  
 Hedefleri birbirleriyle bağımlılık ilişkiler tanımlayabilirsiniz. `DependsOnTargets` Öznitelik, bir hedef diğer hedeflerine bağlı olduğunu gösterir. Örneğin,  
  
```xml  
<Target Name="Serve" DependsOnTargets="Chop;Cook" />  
```  
  
 MSBuild söyler `Serve` hedef bağımlı `Chop` hedef ve `Cook` hedef. MSBuild çalıştıran `Chop` hedef ve çalıştırmalarını `Cook` çalıştırılmadan önce hedef `Serve` hedef.  
  
## <a name="beforetargets-and-after-targets"></a>BeforeTargets sonra hedefleri  
 MSBuild 4. 0'da, kullanarak hedef sırası belirtebilirsiniz `BeforeTargets` ve `AfterTargets` öznitelikleri.  
  
 Aşağıdaki komut dosyası düşünün.  
  
```xml  
<Project DefaultTargets="Compile;Link" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="Compile">  
        <Message Text="Compiling" />  
    </Target>  
    <Target Name="Link">  
        <Message Text="Linking" />  
    </Target>  
</Project>  
```  
  
 Bir ara hedef oluşturmak için `Optimize` sonra çalışan `Compile` , ancak önce hedef `Link` hedeflemek için aşağıdaki hedef herhangi bir yere ekleyin `Project` öğesi.  
  
```xml  
<Target Name="Optimize"   
    AfterTargets="Compile" BeforeTargets="Link">  
    <Message Text="Optimizing" />  
</Target>  
```  
  
## <a name="determining-the-target-build-order"></a>Hedef Derleme Sırasını Belirleme  
 MSBuild hedef derleme sırası şu şekilde belirler:  
  
1.  `InitialTargets` hedefleri çalıştırılır.  
  
2.  Komut satırı tarafından belirtilen hedefleri **/target** anahtar çalıştırılır. Komut satırında hedef belirtirseniz, sonra `DefaultTargets` hedefleri çalıştırılır. Hiçbiri mevcut değilse karşılaştı ilk hedef çalıştırılır.  
  
3.  `Condition` Özniteliği hedef değerlendirildiği. Varsa `Condition` özniteliği var ve değerlendiren `false`, hedef yürütülen değil ve daha fazla yapı etkisi yoktur.

    Koşullu hedef listesinde hedefleri `BeforeTargets` veya `AfterTargets` belirlenen sırada çalıştırmaya devam
  
4.  Bir hedef yürütülmeden önce kendi `DependsOnTargets` hedefleri çalıştırılır.  
  
5.  Bir hedef yürütülen veya atlandı, içinde listeler hedef önce bir `BeforeTargets` özniteliği çalıştırılır.  
  
6.  Bir hedef yürütülmeden önce kendi `Inputs` özniteliği ve `Outputs` özniteliği karşılaştırılır. MSBuild belirlerse çıkış dosyalarla ilgili girdi dosyası veya dosyaları göre eski sonra MSBuild hedef yürütür. Aksi takdirde, MSBuild hedef atlar.  
  
7.  Bir hedef yürütülen veya atlandı, içinde listeler hedef sonra bir `AfterTargets` özniteliği çalıştırılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefler](../msbuild/msbuild-targets.md)
