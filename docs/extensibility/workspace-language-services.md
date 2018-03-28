---
title: Çalışma alanları ve Visual Studio dil Hizmetleri | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8631ffea-83c8-4fd4-a01e-c59772e89c84
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: 59cf2936311bb94c2db1ada6a7a3d5ccf994f027
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="workspaces-and-language-services"></a>Çalışma alanları ve dil Hizmetleri

Dil hizmetleri sağlayabilir [Klasör Aç](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) kullanıcılar aynı zengin dil özellikleri oldukları için kullanılan çözümler ve projeler ile çalışırken. Bir dil hizmeti Self etkinleştirmek bu "gevşek dosya" dil hizmeti sözdizimi vurgulama için sınırlı olsa dosya uzantısı veya açık bir belge içeriğini göre. Kaynak kodu düzenleme/gözden geçirirken daha zengin bir deneyim sağlamak için ek bilgiler gerekiyor. Her bir dil hizmet başlatma için kendi API bir belge için fazladan bağlamsal bu verilerle sahiptir. Bu, genellikle hem dil hizmetine ve yapı sistem sıkı şekilde bağlı bir proje sistemi tarafından yönetilir.

## <a name="initialization"></a>Başlatma

İçinde bir [çalışma](workspaces.md), dil Hizmetleri tarafından başlatılmış bir <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> yalnızca o dil hizmetinde uzmanlaşmış ve yapı yazma hiçbir şey bilmez uzantı noktası. Bu şekilde, bir dil hizmeti sahip tek bir açık uzantısı kaç desenleri bağımsız olarak mevcut bir yapı (örneğin MSBuild, derleme görevleri dosyaları, vb.) sırasında kendi derleyici çalıştırmak için dosya ve klasörleri içinde klasör koruyabilirsiniz. Disk üzerinde değişen bir dosya bağlam oluşturulduğu dosyaları ve dosya bağlam yenilenir, dil hizmet sağlayıcısı dosya bağlamları güncelleştirilmiş kümesi bildirilir. Dil hizmet sağlayıcısı, model sonra güncelleştirebilirsiniz.

Bir belge Düzenleyicisi'nde açıldığında, Visual Studio yalnızca eşleşen bir dosya bağlam sağlayıcısına bulunabilir dosya bağlam türleri gerektiren hizmet sağlayıcıları dil dikkate alır. Bunu daha sonra dosya bağlamı eşleşen sağlayıcı(lar) seçilen dil hizmet sağlayıcısı aracılığıyla geçirir `ILangaugeServiceProvider.InitializeAsync`. Dil hizmet sağlayıcısı ile bir uygulama ayrıntılarını dil hizmet sağlayıcısının dosya bağlam verileri eksik, ancak beklenen kullanıcı deneyimi, daha zengin bir dil hizmeti eksik yaptığı belge açılır.

## <a name="using-ilanguageserviceprovider"></a>ILanguageServiceProvider kullanma

Bir dosya bağlam oluşturulduğunda dil hizmeti bildirilecek bir `ContextType` birine eşleşen `SupportedContextTypes` dil sunucunun değerlerini vermek özniteliği.

Bir dil hizmetini desteklemek için uzantı gerekir:

- Benzersiz bir `Guid`. Bunun için kullanılacak `SupportedContextTypes` öznitelik bağımsız değişkenleri ve bir `FileContext` nesnesi.
- Dil dosyası içeriği
  - Sağlayıcı fabrikası
    - `ExportFileContextProviderAttribute` Yukarıdaki özniteliğiyle benzersiz olarak oluşturulan `Guid` içinde `SupportedContextTypes`
    - Uygular `IWorkspaceProviderFactory<IFileContextProvider>`
  - Sağlayıcı uygulaması `IFileContextProvider.GetContextsForFileAsync`
    - Yeni bir oluşturmak `FileContext` ile `contextType` oluşturucu bağımsız değişkeni olarak benzersiz olarak oluşturulan `Guid`
    - Kullanım `Context` özelliği `FileContext` ek verileri vermek için `ILanguageServiceProvider`
- Dil hizmeti
  - Sağlayıcı fabrikası
    - `ExportLanguageServiceProvider` Yukarıdaki özniteliğiyle benzersiz olarak oluşturulan `Guid` içinde `SupportedContextTypes`
    - Uygular `IWorkspaceProviderFactory<ILanguageServiceProvider>`
  - Sağlayıcı
    - Uygular `ILanguageServiceProvider`
    - Kullanım `ILanguageServiceProvider.InitializeAsync` bir dosya açıldığında sağlanan bağımsız değişkenler için dil hizmetlerini etkinleştirmek için
    - Kullanım `ILanguageServiceProvider.UninitializeAsync` bir dosyayı kapattığınızda sağlanan bağımsız değişkenler için dil hizmetleri devre dışı bırakmak için

>[!WARNING]
>`ILanguageServiceProvider` Yöntemleri çalışma alanı ana iş parçacığı tarafından çağrılabilir. UI gecikmesi yaşanır önlemek için farklı bir iş parçacığında iş planlama göz önünde bulundurun.

## <a name="language-server-protocol"></a>Dil sunucusu Protokolü

`Microsoft.VisualStudio.Workspace.*` API'leri dil hizmetinizi Açık klasörde etkinleştirmek için tek yolu değil. Başka bir seçenek Dil sunucusu kullanmaktır. Hakkında daha fazla bilgi için okuma [dil sunucusu Protokolü](language-server-protocol.md).

## <a name="related-interfaces"></a>İlgili arabirimler

- <xref:Microsoft.VisualStudio.Workspace.Intellisense.ILanguageServiceProvider> dosya türlerini eşleşen bir dosya açıldığında veya kapalı düzenlemesi için çağrılır.

## <a name="next-steps"></a>Sonraki adımlar

* [Çalışma alanı yapı](workspace-build.md) -Klasör Aç destekleyen sistemleri MSBuild ve derleme görevleri dosyaları gibi yapı. 