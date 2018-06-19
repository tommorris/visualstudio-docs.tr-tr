---
title: Hedef Visual Studio'da .NET Framework'ü
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: cba93b86d6ecebf249e11d18bd6e4b6b86e59fda
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32425095"
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

- Öğeleri filtreler **Yeni Öğe Ekle** iletişim kutusu, **Yeni Başvuru Ekle** iletişim kutusu ve **hizmet Başvurusu Ekle** kullanılamayan seçenekleri atlamak için iletişim kutusu hedeflenen sürümü.

- Özel denetimlerde filtreler **araç** hedeflenen bir sürümde kullanılamayan olanlar kaldırmak ve yalnızca göstermek için birden çok denetim kullanılabilir olduğunda en güncel kontrol eder.

- Bu filtreler **IntelliSense** hedeflenen bir sürümde kullanılamayan dil özellikleri atlanacak.

- Özelliklerinde filtreler **özellikleri** penceresi hedeflenen bir sürümde kullanılamayan olanlar atlayın.

- Hedeflenen sürümde kullanılabilir olmayan seçenekleri atlamak için menü seçeneklerini filtreler.

- Derlemeler için derleyici ve hedeflenen sürümü için uygun derleyici seçenekleri sürümünü kullanır.

> [!NOTE]
> Framework'ü hedefleme uygulamanız doğru bir şekilde çalışacağını garanti etmez. Hedeflenen sürüm karşı çalışacağından emin olmak için uygulamanızı test etmeniz gerekir. .NET Framework 2. 0 ' önceki framework sürümlerini hedefleyemez.

## <a name="select-a-target-framework-version"></a>Bir hedef framework sürümü seçin

Bir proje oluşturduğunuzda hedef .NET Framework sürümünü seçin **yeni proje** iletişim kutusu. Kullanılabilir çerçeveleri listesini seçili şablon türü için geçerli olan yüklü framework sürümlerini içerir. .NET Framework, .NET Core şablonlar, gerektirmeyen şablon türleri için **Framework** aşağı açılan liste gizlenir.

![Framework açılan yeni proje iletişim kutusuna](media/vside-newproject-framework.png)

Varolan bir projede hedef değiştirebilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Proje Özellikleri iletişim kutusunda sürümü. Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

## <a name="resolve-system-and-user-assembly-references"></a>Sistem ve kullanıcı derleme başvuruları çözümlenemedi

.NET Framework sürümünü hedeflemek için önce uygun derleme başvurularını yüklemeniz gerekir. Üzerinde Geliştirici paketleri için .NET Framework'ün farklı sürümlerini indirebilirsiniz [.NET indirmeleri](https://www.microsoft.com/net/download/windows) sayfası.

**Başvuru Ekle** iletişim kutusunda, hedef ilgilidir değil Sistem derlemeleri devre dışı bırakır [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürüm böylece bunlar yanlışlıkla projeye eklenemez. (Sistem derlemelerin *.dll* içinde yer alan dosyaları bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümü.) Hedeflenen sürümden daha sonraki bir framework sürümüne ait başvuruları çözümlenmiyor ve bu tür bir referans olarak bağımlı denetimleri eklenemiyor. Böyle bir başvuru etkinleştirmek istiyorsanız, sıfırlama [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] hedef projesine bir başvuru içeriyor.  Daha fazla bilgi için bkz: [nasıl yapılır: .NET Framework sürümü hedef](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

Derleme başvurularını hakkında daha fazla bilgi için bkz: [tasarım zamanında derlemeleri gidermek](../msbuild/resolving-assemblies-at-design-time.md).

## <a name="enable-linq"></a>LINQ etkinleştir

.NET Framework 3.5 veya daha sonra bir başvuru hedeflediğinizde **System.Core** ve proje düzeyi alma için <xref:System.Linq> (Visual Basic'te yalnızca) otomatik olarak eklenir. LINQ özellikleri kullanmak istiyorsanız, ayrıca etkinleştirmelisiniz `Option Infer` üzerinde (yalnızca Visual Basic'te). Bir önceki .NET Framework sürümü için hedef değiştirirseniz başvuru ve içe aktarma otomatik olarak kaldırılır. Daha fazla bilgi için bkz: [iş LINQ ile](/dotnet/csharp/tutorials/working-with-linq).

## <a name="see-also"></a>Ayrıca bkz.

- [Çoklu sürüm desteği (MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [Nasıl yapılır: hedef framework ve platform araç takımı (C++) değiştirme](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)