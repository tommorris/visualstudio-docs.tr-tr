---
title: "Visual Studio'da .NET Framework'ü hedefleme | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: e4b68e5d7b7e63e76a2291eba6d81eb581756845
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="visual-studio-multi-targeting-overview"></a>Visual Studio çoklu sürüm desteğine genel bakış

Visual Studio'da sürümünü veya profilini hedeflemek için projenizi istediğiniz .NET Framework'ün belirtebilirsiniz. Bir uygulamayı başka bir bilgisayardaki uygulama hedef bilgisayarda yüklü Framework sürümü ile uyumlu olmalıdır Framework sürümü çalıştırmak için.

Framework'ün bu hedef farklı sürümlerini projeleri içeren bir çözüm de oluşturabilirsiniz. Framework'ü hedefleme uygulama framework'ün belirtilen sürümde kullanılabilir olan işlevsellik kullanır garanti yardımcı olur.

> [!TIP]
> Ayrıca, farklı platformlar için uygulama hedefleyebilirsiniz. Daha fazla bilgi için bkz: [çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md).

## <a name="framework-targeting-features"></a>Framework özellikleri hedefleme

Framework'ü hedefleme aşağıdaki özellikleri içerir:

- Önceki bir sürümünü hedefleyen bir projeyi açtığınızda [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], Visual Studio, otomatik olarak yükseltmek veya hedef olarak bırakın-değil.

- Bir proje oluşturduğunuzda sürümü belirtebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hedeflemek istediğiniz.

- Sürümü değiştirebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] var olan proje hedefler.

- Farklı bir sürümünü hedefleyebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] her birinde aynı çözümde birkaç proje.

- Sürümü değiştirdiğinizde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , Proje hedefleri [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] başvuruları ve yapılandırma dosyaları için gerekli tüm değişiklikleri yapar.

Önceki bir sürümünü hedefleyen bir proje üzerinde çalışırken [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], Visual Studio dinamik olarak geliştirme ortamı aşağıdaki gibi değişir:

- Öğeleri filtreler **yeni proje** iletişim kutusu, **Yeni Öğe Ekle** iletişim kutusu, **Yeni Başvuru Ekle** iletişim kutusu ve **hizmetBaşvurusuEkle** iletişim kutusu hedeflenen bir sürümde kullanılamayan seçenekleri atlayın.

- Özel denetimlerde filtreler **araç** hedeflenen bir sürümde kullanılamayan olanlar kaldırmak ve yalnızca göstermek için birden çok denetim kullanılabilir olduğunda en güncel kontrol eder.

- Hedeflenen sürümde kullanılabilir olmayan dil özellikleri atlamak için IntelliSense filtreler.

- Özelliklerinde filtreler **özellikleri** penceresi hedeflenen bir sürümde kullanılamayan olanlar atlayın.

- Hedeflenen sürümde kullanılabilir olmayan seçenekleri atlamak için menü seçeneklerini filtreler.

- Derlemeler için derleyici ve hedeflenen sürümü için uygun derleyici seçenekleri sürümünü kullanır.

> [!NOTE]
> Framework'ü hedefleme uygulamanız doğru bir şekilde çalışacağını garanti etmez. Hedeflenen sürüm karşı çalışacağından emin olmak için uygulamanızı test etmeniz gerekir. .NET Framework 2. 0 ' önceki framework sürümlerini hedefleyemez.

## <a name="selecting-a-target-framework-version"></a>Bir hedef framework sürümü seçme

Bir proje oluşturduğunuzda, hedef seçin [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümünde **yeni proje** iletişim kutusu. Kullanılabilir proje şablonları seçime göre filtrelenir. Varolan bir projede hedef değiştirebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Proje Özellikleri iletişim kutusunda sürümü. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

## <a name="resolving-system-and-user-assembly-references"></a>Sistem ve kullanıcı derleme başvurularını çözme

.NET Framework sürümünü hedeflemek için önce uygun derleme başvurularını yüklemeniz gerekir. Üzerinde Geliştirici paketleri için .NET Framework'ün farklı sürümlerini indirebilirsiniz [.NET indirmeleri](https://www.microsoft.com/net/download/windows) sayfası.

**Başvuru Ekle** iletişim kutusunda, hedef ilgilidir değil Sistem derlemeleri devre dışı bırakır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürüm böylece bunlar yanlışlıkla projeye eklenemez. (Sistem derlemeler içinde yer alan bir .dll dosyaları olan bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümü.) Hedeflenen sürümden daha sonraki bir framework sürümüne ait başvuruları çözümlenmiyor ve bu tür bir referans olarak bağımlı denetimleri eklenemiyor. Böyle bir başvuru etkinleştirmek istiyorsanız, sıfırlama [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hedef projesine bir başvuru içeriyor.  Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

Derleme başvurularını hakkında daha fazla bilgi için bkz: [tasarım zamanında derlemeleri çözme](../msbuild/resolving-assemblies-at-design-time.md).

## <a name="enabling-linq"></a>LINQ etkinleştirme

.NET Framework 3.5 veya sonrasını, System.Core başvuru ve bir proje düzeyi içeri aktarma (yalnızca Visual Basic'te) System.Linq için hedeflediğinizde eklendiğinde otomatik olarak. LINQ özellikleri kullanmak istiyorsanız, ayrıca Option Infer (Visual Basic'te yalnızca) açmanız gerekir. Bir önceki .NET Framework sürümü için hedef değiştirirseniz başvuru ve içe aktarma otomatik olarak kaldırılır. Daha fazla bilgi için bkz: [LINQ ile çalışma](/dotnet/csharp/tutorials/working-with-linq).

## <a name="see-also"></a>Ayrıca bkz.

[Çoklu sürüm desteği (MSBuild)](../msbuild/msbuild-multitargeting-overview.md)  
[Nasıl yapılır: hedef Framework ve Platform araç takımı (C++) değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)  
[Platform uyumluluğu ve sistem gereksinimleri](http://www.microsoft.com/visualstudio/eng/products/compatibility)
