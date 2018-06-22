---
title: UWP uygulamalar için uygulama özellik sayfası
ms.date: 01/23/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- AppPackage.Properties.Application
helpviewer_keywords:
- Application page [UWP project]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 6d1d57dc8c0eb07b90da79de3fee5d42678e7a22
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36279992"
---
# <a name="application-property-page-uwp-projects"></a>Uygulama özellik sayfası (UWP projeleri)

Kullanım **uygulama** özellik sayfası Evrensel Windows Platformu (UWP) projenin derleme ve paket bilgilerini ve hedef Windows 10 sürümü belirtin.

![Uygulama özellik sayfası](media/application-page-uwp.png)

Erişim için **uygulama** sayfası, proje düğümünde seçin **Çözüm Gezgini**. Ardından **proje** > **özellikleri** menü çubuğunda. Özellik sayfaları açmak **uygulama** sekmesi.

## <a name="general-section"></a>Genel bölümü

**Derleme adı**&mdash;derleme bildirimi barındıracak çıkış dosyasının adını belirtir.

Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

**Varsayılan ad alanı**&mdash;projeye eklenen dosyalar için temel ad alanını belirtir. Ad alanları hakkında daha fazla bilgi için bkz: [ad alanları (C# programlama Kılavuzu)](/dotnet/csharp/programming-guide/namespaces/), [ad alanları (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/namespaces), veya [ad alanları (C++)](/cpp/cpp/namespaces-cpp).

Bu özellik programlı olarak erişmek için bkz: <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

**Derleme bilgilerini**&mdash;bu düğme görüntüler seçme [derleme bilgileri iletişim kutusu](../../ide/reference/assembly-information-dialog-box.md).

**Paket bildirimi**&mdash;bu düğmesini seçerek bildirim Tasarımcısı'nı açar. Bildirim Tasarımcısı'nı seçerek de erişilebilir _Package.appxmanifest_ dosyasını **Çözüm Gezgini**. Daha fazla bilgi için bkz: [bir paket bildirim Tasarımcısı ile yapılandırma](/windows/uwp/packaging/packaging-uwp-apps#configure-an-app-package).

## <a name="targeting-section"></a>Bölüm hedefleme

Bu bölümdeki açılan listeleri kullanarak, uygulamanız için en düşük sürümü Windows 10 ve hedef sürüm ayarlayabilirsiniz. Windows 10, en son sürümünü hedef önerilir ve en düşük sürümün çok destekleyen bir kuruluş uygulama geliştiriyorsanız. Seçmek için hangi Windows 10 sürümü hakkında daha fazla bilgi için bkz: [UWP sürümünü seçin](/windows/uwp/updates-and-versions/choose-a-uwp-version).

Visual Studio 2017 içinde hedefleme platform hakkında bilgi için bkz [Platform Desteği](/visualstudio/productinfo/vs2017-compatibility-vs#a-iddevelopwindows-avisual-studio-2017-support-for-windows-development).

## <a name="see-also"></a>Ayrıca bkz.

- [İlk UWP uygulamanızı oluşturma](/windows/uwp/get-started/your-first-app)
- [Bir UWP sürüm seçin](/windows/uwp/updates-and-versions/choose-a-uwp-version)