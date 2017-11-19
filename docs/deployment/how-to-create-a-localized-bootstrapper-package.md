---
title: "Nasıl yapılır: yerelleştirilmiş önyükleyici paketi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
caps.latest.revision: "15"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: f19ec03dda8666eea39b50af40a44ab2c68694ce
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>Nasıl yapılır: Yerelleştirilmiş Önyükleyici Paketi Oluşturma
Önyükleyici paketi oluşturduktan sonra her yerel ayar için iki dosya daha oluşturarak yerelleştirilmiş önyükleyici paketi sürümleri oluşturabilirsiniz: (örneğin, bir eula.rtf) dosyası ve bir paket bildirimi (package.xml) yazılım lisans koşulları.  
  
 Varsayılan olarak, yalnızca .NET Framework 4, .NET Framework 4 istemci profili, F # çalışma zamanı 2.0 ve F # çalışma zamanı 4.0 için Visual Studio 2010 yerelleştirilmiş önyükleyici paketleri içerir. Üç adımları izleyerek diğer önyükleyiciler için yerelleştirilmiş paketler oluşturabilirsiniz.  
  
1.  \Program SDKs\Windows\v7.0A\Bootstrapper\Packages yerel ayar adı sonra adlı bir klasör oluşturun\\*BootstrapperPackageName*.  
  
2.  Önyükleyici paketini yazılım lisans koşulları içeren bir dosya oluşturun ve yeni klasörün içine koyun.  
  
3.  Package.xml adlı bir paket bildirimi oluşturma dizeleri ve kültürü güncelleştirin ve dosya yeni klasörün içine koyun. Hedef dilde bir önyükleyici Visual Studio'nun zaten oluşturduysanız, Visual Studio package.xml dosyasını kopyalayın ve bu adımda değiştirin.  
  
> [!NOTE]
>  Uygulamaları dağıtmak için bir kurulum projesi kullanıyorsanız, uygulamanızı değiştirerek yerelleştirebilirsiniz **yerelleştirme** özelliği.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>Yerelleştirilmiş önyükleyici paketi oluşturmak için  
  
1.  Yerel ayar adından sonra adlı bir klasör oluşturun.  
  
     32-bit bilgisayarlarda, klasör \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages oluşturun\\*BootstrapperPackageName*\ klasör.  
  
     64-bit bilgisayarlarda, klasörü içinde \Program dosyaları (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages oluşturmak\\*BootstrapperPackageName*\ klasör.  
  
     Aşağıdaki tabloda bir yerel ayarı eşlemek için kullanabileceğiniz klasör adlarını gösterir.  
  
    |Yerel Ayar|Klasör adı|  
    |------------|-----------------|  
    |ve|zh-atanır|  
    |seçenekleri yerine|zh-Hant|  
    |Çekçe|cs|  
    |Almanca|Gizle|  
    |İngilizce|tr|  
    |İspanyolca|ES|  
    |Fransızca|FR|  
    |İtalyanca|Bunu|  
    |Korece|Ko|  
    |Japonca|ja|  
    |Lehçe|PL|  
    |Portekizce (Brezilya)|pt-BR|  
    |Rusça|RU|  
    |Türkçe|tr|  
  
2.  Önyükleyici paketini yazılım lisans koşulları içeren bir dosya oluşturun ve yeni klasörün içine koyun.  
  
3.  Package.xml adlı bir paket bildirimi oluşturun ve yeni klasörün içine koyun. Daha fazla bilgi için bkz: [nasıl yapılır: bir paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md).  
  
4.  Güncelleştirme `<Strings>` paket bölümünü bildiriminin yerel ayar için doğru dilde dizelerdir.  
  
5.  Değişiklik `<String Name="Culture">` klasör adı eşleşecek değer.  
  
6.  Package.xml dosyasını kaydedin.  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>.NET Framework 3.5 Service Pack 1'de Fransızca yerelleştirilmiş önyükleyici paketi oluşturmak için  
  
1.  Fr adlı bir klasör oluşturun. Klasör adı yerel ayar adı eşleşmelidir.  
  
     32-bit bilgisayarlarda, klasörü \Program SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\ klasöründe oluşturun.  
  
     64-bit bilgisayarlarda, klasör \Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\ klasöründe oluşturun.  
  
2.  Yazılım Lisans Koşulları'nı yerelleştirilmiş sürümünü fr klasörüne koyun.  
  
3.  \Program dosyaları (x86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\en\package.xml dosyasını fr klasörüne kopyalayın ve dosyayı XML Tasarımcısı'nda açın.  
  
4.  Güncelleştirme `<Strings>` paket bölümünü bildiriminin Fransızca hata dizelerdir.  
  
5.  Değişiklik `<String Name="Culture">` değerini fr.  
  
6.  Package.xml dosyasını kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Önyükleyici paketleri oluşturma](../deployment/creating-bootstrapper-packages.md)   
 [Uygulama dağıtımının önkoşulları](../deployment/application-deployment-prerequisites.md)   
 [Nasıl yapılır: Paket bildirimi oluşturma](../deployment/how-to-create-a-package-manifest.md)