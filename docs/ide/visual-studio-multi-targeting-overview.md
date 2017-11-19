---
title: "Visual Studio çoklu sürüm desteğine genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework version [Visual Studio]
- versions [Visual Studio], targeting .NET Framework version
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
ms.assetid: b1702c33-0672-4ebc-b779-2b324d6ea880
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ad2917a1cf0a620f2e228828a152d91ec8948734
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="visual-studio-multi-targeting-overview"></a>Visual Studio Çoklu Sürüm Desteğine Genel Bakış
Bu sürümünde [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], sürümünü belirtin [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] uygulamanız için gerekli olmasıdır. Bu nedenle, bu sürümü kullanmak istiyorsanız, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] önceki bir sürümde başlatılan bir proje geliştirmek devam etmek için çerçevesi hedefi değiştirmek zorunda değildir. Framework'ün bu hedef farklı sürümlerini projeleri içeren bir çözüm de oluşturabilirsiniz. Framework'ü hedefleme Ayrıca uygulama framework'ün belirtilen sürümde kullanılabilir olan işlevsellik kullanır garanti yardımcı olur.  
  
> [!TIP]
>  Ayrıca, farklı platformlar için uygulama hedefleyebilirsiniz. Daha fazla bilgi için bkz: [çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)  
  
## <a name="framework-targeting-features"></a>Framework hedefleme özellikleri  
 Framework'ü hedefleme aşağıdaki özellikleri içerir:  
  
-   Önceki bir sürümünü hedefleyen bir projeyi açtığınızda [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] otomatik olarak onu yükseltebilir veya hedef olduğu gibi bırakın.  
  
-   Bir proje oluşturduğunuzda sürümü belirtebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hedeflemek istediğiniz.  
  
-   Sürümü değiştirebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] var olan proje hedefler.  
  
-   Farklı bir sürümünü hedefleyebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] her birinde aynı çözümde birkaç proje.  
  
-   Sürümü değiştirdiğinizde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , Proje hedefleri [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] başvuruları ve yapılandırma dosyaları için gerekli tüm değişiklikleri yapar.  
  
 Önceki bir sürümünü hedefleyen bir proje üzerinde çalışırken [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], Visual Studio dinamik olarak geliştirme ortamı aşağıdaki gibi değişir:  
  
-   Öğeleri filtreler **yeni proje** iletişim kutusu, **Yeni Öğe Ekle** iletişim kutusu, **Yeni Başvuru Ekle** iletişim kutusu ve **hizmetBaşvurusuEkle** iletişim kutusu hedeflenen bir sürümde kullanılamayan seçenekleri atlayın.  
  
-   Özel denetimlerde filtreler **araç** hedeflenen bir sürümde kullanılamayan olanlar kaldırmak ve yalnızca göstermek için birden çok denetim kullanılabilir olduğunda en güncel kontrol eder.  
  
-   Hedeflenen sürümde kullanılabilir olmayan dil özellikleri atlamak için IntelliSense filtreler.  
  
-   Özelliklerinde filtreler **özellikleri** penceresi hedeflenen bir sürümde kullanılamayan olanlar atlayın.  
  
-   Hedeflenen sürümde kullanılabilir olmayan seçenekleri atlamak için menü seçeneklerini filtreler.  
  
-   Derlemeler için derleyici ve hedeflenen sürümü için uygun derleyici seçenekleri sürümünü kullanır.  
  
> [!NOTE]
>  Framework'ü hedefleme uygulamanız doğru bir şekilde çalışacağını garanti etmez. Hedeflenen sürüm karşı çalışacağından emin olmak için uygulamanızı test etmeniz gerekir. .NET Framework 2. 0 ' önceki framework sürümlerini hedefleyemez.  
  
## <a name="selecting-a-target-framework-version"></a>Bir hedef Framework sürümü seçme  
 Bir proje oluşturduğunuzda, hedef seçin [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümünde **yeni proje** iletişim kutusu. Kullanılabilir proje şablonları seçime göre filtrelenir. Varolan bir projede hedef değiştirebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Proje Özellikleri iletişim kutusunda sürümü. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
> [!NOTE]
>  Visual Studio Express sürümleri, hedef Framework'ü ayarla olamaz **yeni proje** iletişim kutusu.  
  
## <a name="resolving-system-and-user-assembly-references"></a>Sistem ve kullanıcı derleme başvurularını çözümleme  
 .NET Framework sürümünü hedeflemek için önce uygun derleme başvurularını yüklemeniz gerekir. .NET Framework sürüm 2.0, 3.0 ve 3.5 için derleme başvurularını indirebileceğiniz .NET Framework 3.5 SP1 bulunmaktadır [Microsoft Download Center, Microsoft Visual Studio](http://go.microsoft.com/fwlink/?LinkId=227602) Web sitesi. .NET Framework 3.5 istemci profili, .NET Framework 4, .NET Framework 4 istemci profili ve Silverlight için derleme başvurularını kullanılabilir de [Visual Studio indirmeleri](http://go.microsoft.com/fwlink/?LinkId=179687) Web sitesi.  
  
> [!NOTE]
>  .NET Framework istemci profili sınırlı sayıda kitaplıkları ve özellikleri sağlar .NET Framework'ün bir alt kümesidir. İstemci profilleri hakkında daha fazla bilgi için bkz: [.NET Framework istemci profili](/dotnet/framework/deployment/client-profile).  
  
 **Başvuru Ekle** iletişim kutusunda, hedef ilgilidir değil Sistem derlemeleri devre dışı bırakır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürüm böylece bunlar yanlışlıkla projeye eklenemez. (Sistem derlemeler içinde yer alan bir .dll dosyaları olan bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümü.) Hedeflenen sürümden daha sonraki bir framework sürümüne ait başvuruları çözümlenmiyor ve bu tür bir referans olarak bağımlı denetimleri eklenemiyor. Böyle bir başvuru etkinleştirmek istiyorsanız, sıfırlama [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hedef projesine bir başvuru içeriyor.  Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  
  
 Derleme başvurularını hakkında daha fazla bilgi için bkz: [tasarım zamanında derlemeleri çözme](../msbuild/resolving-assemblies-at-design-time.md).  
  
## <a name="enabling-linq"></a>LINQ etkinleştirme  
 .NET Framework 3.5 veya sonrasını, System.Core başvuru ve bir proje düzeyi içeri aktarma (yalnızca Visual Basic'te) System.Linq için hedeflediğinizde eklendiğinde otomatik olarak. LINQ özellikleri kullanmak istiyorsanız, ayrıca Option Infer (Visual Basic'te yalnızca) açmanız gerekir. Bir önceki .NET Framework sürümü için hedef değiştirirseniz başvuru ve içe aktarma otomatik olarak kaldırılır. Daha fazla bilgi için bkz: [LINQ ile çalışma](/dotnet/csharp/tutorials/working-with-linq).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)   
 [Platform uyumluluğu ve sistem gereksinimleri](http://www.microsoft.com/visualstudio/eng/products/compatibility)