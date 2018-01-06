---
title: "Yalıtılmış Kabuk öğeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: f8d68c3d-9134-4a8f-b566-485956cd321e
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 82379a840010ebae434f8ad1a03c12793fe10ec5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="elements-of-the-isolated-shell"></a>Yalıtılmış Kabuk öğeleri
Kayıt defteri ayarları, çalışma zamanı ayarları ve uygulama giriş noktası yalıtılmış Kabuk uygulamanızı ve kendi .vsct, .pkgdef, and.pkgundef dosyaları değiştirebilirsiniz.  
  
## <a name="registry-settings"></a>Kayıt defteri ayarları  
 .pkgdef ve .pkgundef dosyaları yalıtılmış Kabuk uygulama kayıt defteri ayarlarını değiştirin. Uygulamayı çalıştırdığınızda, kayıt defteri ayarlarını aşağıdaki sırayla tanımlanmıştır:  
  
 Uygulamayı çalıştırdığınızda, kayıt defteri ayarlarını aşağıdaki sırayla tanımlanmıştır:  
  
1.  Uygulama için kayıt defteri anahtarı oluşturulur.  
  
2.  Kayıt defterinde belirtilen anahtarları ve girişleri tanımlayarak uygulama .pkgdef dosyasından güncelleştirilir.  
  
3.  Uygulamanızın parçası olan her paket için paket .pkgdef dosyasından kayıt defteri güncelleştirilir. Her paket uygulama .pkgdef dosyasında $RootKey$ \Packages tarafından tanımlanan\\{*vsPackageGuid*} paketi için anahtar.  
  
4.  Kayıt defteri AppEnvConfig.pkgdef ve BaseConfig.pkgdef içinde güncelleştirilir *Visual Studio SDK yükleme yolu*\Common7\IDE\ShellExtensions\Platform dizini. Bu, Visual Studio bir parçası ve Visual Studio Kabuğu (yalıtılmış mod) yeniden dağıtılabilir paketi parçası dosyalarıdır.  
  
5.  Kayıt defterinde belirtilen anahtarları ve girişleri kaldırarak uygulama .pkgundef dosyasından güncelleştirilir.  
  
## <a name="run-time-settings"></a>Çalışma zamanı ayarları  
 Bir kullanıcı yalıtılmış Kabuk uygulama başladığında Visual Studio Kabuğu'nu başlangıç giriş noktasını çağırır. Uygulama ayarları uygulamanız başladığında, aşağıdaki gibi tanımlanmıştır:  
  
1.  Visual Studio Kabuğu'nu belirli anahtarlar için uygulama kayıt defteri denetler. Bir anahtar ayarını başlangıç giriş noktası çağrısında belirtilirse, bu değeri kayıt defterindeki değeri geçersiz kılar.  
  
2.  Kayıt defteri ne giriş noktası parametresi bir ayarın değerini belirtir, sonra ayar için varsayılan değer kullanılır.  
  
 Bir kullanıcı, uygulamanızın komut satırından başlatıldığında tüm komut satırı anahtarları Devenv yapan aynı şekilde davranır Visual Studio Kabuğu geçirilir. Devenv anahtarları hakkında daha fazla bilgi için bkz: [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md) ve [VSPackage geliştirme için Devenv komut satırı anahtarları](../devenv-command-line-switches-for-vspackage-development.md). Bir paket için komut satırı anahtarları nasıl kaydeder hakkında daha fazla bilgi için bkz: [ekleme komut satırı anahtarları](../adding-command-line-switches.md).  
  
## <a name="the-start-entry-point"></a>Başlangıç giriş noktası  
 Appenvstub.dll dosya yalıtılmış Kabuk erişimi için giriş noktaları içerir. Uygulama başlatıldığında, başlangıç giriş noktası Appenvstub.dll çağırır.  
  
 Başlangıç için giriş noktası geçirilen son parametresinin değerini değiştirerek uygulamanın davranışı değiştirebilirsiniz. Daha fazla bilgi için bkz: [yalıtılmış Kabuk giriş noktası parametreleri (C++)](isolated-shell-entry-point-parameters-cpp.md).  
  
## <a name="the-vsct-file"></a>. Vsct dosyası  
 .Vsct dosya standart hangi Visual Studio kullanıcı Arabirimi öğeleri uygulamada bulunan belirtmenize olanak sağlar. Daha fazla bilgi için bkz: [. Vsct dosyaları](modifying-the-isolated-shell-by-using-the-dot-vsct-file.md).  
  
## <a name="the-pkgundef-file"></a>. Pkgundef dosyası  
 Uygulama, Visual Studio'nun zaten yüklü olduğu bir bilgisayara yüklendiğinde, bir Visual Studio kayıt defteri girdileri için uygulama kopyası oluşturulur. Varsayılan olarak, uygulama bilgisayarda yüklü olan VSPackages kullanır. .Pkgundef dosya uygulamadan Visual Studio Kabuğu veya uzantılar belirli öğeleri kaldırmak için kayıt defteri girdileri dışlamanıza olanak sağlar. Daha fazla bilgi için bkz: [. Pkgundef dosyaları](modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md).  
  
 .Pkgundef dosya uygulamadan Visual Studio Kabuğu veya uzantılar belirli öğeleri kaldırmak için kayıt defteri girdileri dışlamanıza olanak sağlar. Daha fazla bilgi için bkz: [. Pkgundef dosyaları](modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md).  
  
 Paket hariç tutabilirsiniz GUID'ler kümesi içinde listelenen [paketi GUID, Visual Studio özellikleri](package-guids-of-visual-studio-features.md).  
  
## <a name="the-pkgdef-file"></a>. Pkgdef dosyası  
 .Pkgdef dosya, uygulama için uygulama yüklendiğinde, ayarladığınız kayıt defteri girişleri tanımlamanıza olanak sağlar. .Pkgdef dosyasının açıklaması ve Visual Studio Kabuğu'nu kullanır kayıt defteri girdileri listesi için bkz: [. Pkgdef dosyaları](modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md).  
  
## <a name="substitution-strings"></a>Değiştirme dizeleri  
 .Pkgdef ve .pkgundef dosyalarında kullanılan değiştirme dizelerini listelenen [değiştirme dizeleri kullanılır. Pkgdef ve. Pkgundef dosyaları](substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md).  
  
## <a name="other-settings"></a>Diğer ayarları  
 Yalıtılmış Kabuk uygulamanızın üzerinde Microsoft.VisualStudio.GraphModel.dll bağımlı olması durumunda, yalıtılmış Kabuk uygulamanızın .config dosyasına aşağıdaki bağlama yeniden yönlendirme eklemeniz gerekir:  
  
```  
<dependentAssembly>  
    <assemblyIdentity name="Microsoft.VisualStudio.GraphModel" publicKeyToken="b03f5f7f11d50a3a" culture="neutral" />  
    <bindingRedirect oldVersion="11.0.0.0" newVersion="12.0.0.0"/>  
</dependentAssembly>  
  
```