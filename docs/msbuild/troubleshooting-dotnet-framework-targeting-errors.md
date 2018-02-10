---
title: ".NET Framework hedefleme hatalarının sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.FrameworkTargetingErrors
- MSBuild.ResolveAssemblyReference.FailedToResolveReferenceBecausePrimaryAssemblyInExclusionList
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], .NET Framework Client Profile
- multi-targeting
- multitargeting
- .NET Framework Client Profile
ms.assetid: 830e3e45-9a93-4279-a249-75b84599aefb
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: e22020797d14c74c744276df3fafef6a9d799f2f
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="troubleshooting-net-framework-targeting-errors"></a>.NET Framework Hedefleme Hatalarının Sorunlarını Giderme
Bu konu, başvuru nedeniyle ortaya çıkabilir MSBuild hataları açıklar sorunlar ve bu hataların nasıl çözebilirsiniz.  
  
## <a name="you-have-referenced-a-project-or-assembly-that-targets-a-different-version-of-the-net-framework"></a>Bir proje veya farklı bir .NET Framework sürümünü hedefler derleme başvurulan  
 Projeleri veya farklı sürümlerini hedefleyen derlemeleri başvuruda bulunan uygulamaları oluşturabilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Örneğin, istemci profilini hedefleyen bir uygulama oluşturabilir [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] ancak .NET Framework 2.0 hedefleyen bir derlemeye başvurur. Ancak, önceki bir sürümünü hedefleyen bir proje oluşturduğunuzda, [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], bu proje bir proje veya istemci profilini hedefler derleme için bir başvuru ayarlanamıyor [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] veya [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] kendisi. Hatayı gidermek için uygulamanızın bir profil ya da projeleri veya derlemeleri tarafından uygulamanızı başvuran hedeflenen profili ile uyumlu olan profilleri hedefler emin olun.  
  
## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework"></a>Proje .NET Framework'ün farklı bir sürüme yeniden hedeflenen  
 Hedef sürümü değiştirirseniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] uygulamanız için Visual Studio başvuruları bazıları değişir, ancak bazı başvuruları el ile güncelleştirmeniz gerekebilir. Hedef alınacak bir uygulama değiştirirseniz, örneğin, yukarıda açıklanan hatalardan biri gerçekleşebilir [!INCLUDE[net_v35SP1_long](../msbuild/includes/net_v35sp1_long_md.md)] ve uygulama kaynaklar veya istemci profilini Bel ayarları olduğunu [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)].  
  
 Uygulama ayarları olarak çözmek için açık **Çözüm Gezgini**, seçin **tüm dosyaları göster**ve ardından Visual Studio XML düzenleyicisinde app.config dosyasını düzenleyin. .NET Framework'ün uygun sürümüne eşleşen ayarlarını sürümünde değiştirin. Örneğin, 4.0.0.0 2.0.0.0 için sürüm ayarını değiştirebilirsiniz. Benzer şekilde, uygulamanın her zaman kaynakları ekledi açmak **Çözüm Gezgini**, seçin **tüm dosyaları göster** düğmesini tıklatın, **My proje** (Visual Basic) veya **Özellikleri** (C#) ve Visual Studio XML düzenleyicisinde Resources.resx dosyasını düzenleyin. Sürüm ayarını 4.0.0.0 2.0.0.0 için değiştirin.  
  
 Uygulamanız, bit eşlemler veya simgeler gibi kaynakları veya veri bağlantı dizelerini gibi ayarları varsa, size ayrıca hata tüm öğeler üzerinde kaldırarak çözebilirsiniz **ayarları** sayfasında **Proje Tasarımcısı**ve gerekli ayarları yeniden ekleniyor.  
  
## <a name="you-have-re-targeted-a-project-to-a-different-version-of-the-net-framework-and-references-do-not-resolve"></a>Proje .NET Framework'ün farklı bir sürüme yeniden hedeflenmiş ve başvurular çözümlenmiyor  
 Farklı bir sürümü için bir proje yeniden hedefleyin varsa [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], başvurular düzgün bazı durumlarda çözülebilir değildir. Derlemeler açık tam başvurular genellikle bu soruna neden ancak çözümlenmiyor başvuruları kaldırma ve bunları projeye ekleyerek çözülebilir. Alternatif olarak, proje dosyası başvuruları değiştirin düzenleyebilirsiniz. İlk olarak, aşağıdaki biçimde başvuruları kaldırın:  
  
```xml  
<Reference Include="System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089, processorArchitecture=MSIL" />  
```  
  
 Ardından, bunları basit form ile değiştirin:  
  
```xml  
<Reference Include="System.ServiceModel" />  
```  
  
> [!NOTE]
>  Projenizi kapatıp sonra aynı zamanda tüm başvurular düzgün çözümlenmesini sağlamak için yeniden oluşturmalısınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md)   
 [.NET framework istemci profili](/dotnet/framework/deployment/client-profile)   
 [Belirli bir .NET Framework sürümünü hedefleme](../ide/targeting-a-specific-dotnet-framework-version.md)   
 [Çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)