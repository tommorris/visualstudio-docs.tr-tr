---
title: Ayarlama hata ayıklama ve dağıtım yapılandırmalarını | Microsoft Docs
ms.custom: ''
ms.date: 04/10/2017
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.builds
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- configurations, release
- build configurations, release
- projects [Visual Studio], release configurations
- debugging [Visual Studio], release configurations
- release builds, changing settings
- debug builds
- debug builds, switching to release build
- debug builds, changing configuration settings
- debugging [Visual Studio], debug configurations
- projects [Visual Studio], debug configurations
- build configurations, debug
- debug configurations
- release builds, switching to debug build
- Visual Basic projects, debug and release builds
ms.assetid: 57b6bbb7-f2af-48f7-8773-127d75034ed2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ea27fdccaadc70f22d9c9c02d75ddef98a11be13
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39153104"
---
# <a name="set-debug-and-release-configurations-in-visual-studio"></a>Hata ayıklama ayarlayabilir ve yayın yapılandırmaları Visual Studio'da
Visual Studio projeleri ayrı sürümü ve hata ayıklama yapılandırması, programınız için. Adların da ifade ettiği şekilde, hata ayıklama sürümünün hata ayıklama ve yayın sürümünü son sürüm dağıtımı oluşturun.  
  
Programınızın hata ayıklama yapılandırması tam sembolik hata ayıklama bilgileri ve en iyileştirme olmadan derlenir. Kaynak kodu ve oluşturulan yönergeler arasındaki ilişki daha karmaşık olacağından en iyileştirme hata ayıklama, karmaşık hale getirir.  
  
Programınızın sürüm yapılandırması hiçbir sembolik hata ayıklama bilgisi içermez ve tamamen en iyileştirilmiştir. Hata ayıklama bilgisi .pdb dosyaları oluşturulabilir [derleyici seçeneklerine bağlı olarak](#BKMK_symbols_release) kullanılan. .Pdb dosyaları oluşturmak, daha sonra yayım sürümünüzde hata ayıklama gerekirse çok kullanışlı olabilir.  
  
Derleme yapılandırmaları hakkında daha fazla bilgi için bkz. [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
Derleme yapılandırmasını değiştirebilirsiniz **derleme** menüsünde, araç çubuğundan veya projenin özellik sayfalarındaki. Dile özgü proje özellik sayfaları. Aşağıdaki yordam, menü ve araç, yapı yapılandırmasını değiştirme işlemi gösterilmektedir. Farklı dillerde projelerde derleme yapılandırmasını değiştirme hakkında daha fazla bilgi için Ayrıca bakınız bölümüne bakın.  
  
## <a name="change-the-build-configuration"></a>Derleme yapılandırmasını değiştirin  
  
1.  Gelen **derleme** menüsünde **Configuration Manager**, ardından **hata ayıklama** veya **yayın**.  
  
2.  Ya da araç çubuğunda **hata ayıklama** veya **yayın** gelen **çözüm yapılandırmaları** liste kutusu.  
  
     ![araç derleme Yapılandırması](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")  
  
     Bu araç, Express sürümlerinde kullanılamaz. Kullanabileceğiniz **Çözümü Derle F6** ve **hata ayıklamayı Başlat F5** menü öğelerinin yapılandırmayı seçin.

## <a name="BKMK_symbols_release"></a>Bir derleme için Sembol (.pdb) dosyalarını oluştur

Çoğu proje türleri için .pdb dosyaları hem hata ayıklama için varsayılan olarak oluşturulan ve yayın derlemeleri, ancak varsayılan ayarlar, belirli bir proje türü ve Visual Studio sürümüne bağlı olarak farklılık gösterir. Yapılandırabileceğiniz olup derleyici .pdb dosyaları oluşturur ve hata ayıklama bilgilerini dahil etmek için ne tür.

> [!IMPORTANT] 
> Hata ayıklayıcı, yalnızca yürütülebilir dosya oluşturulduğunda, oluşturulan .pdb dosyasıyla tam olarak eşleşen bir yürütülebilir dosya için bir .pdb dosyasını yükler (yani, .pdb özgün olmalı veya özgün .pdb'nin kopyasını olmalıdır). Daha fazla bilgi için [neden Visual Studio gerektiriyor hata ayıklayıcı sembol birlikte oluşturuldukları ikili dosyalarla tam olarak eşleşen dosyaları?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)

Her proje türü, bu seçenekleri ayarlamak için farklı bir yol olabilir.

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>Bir C#, ASP.NET veya Visual Basic projesi için Sembol dosyaları oluştur

C# hata ayıklama yapılandırmaları için proje ayarları hakkında ayrıntılı bilgi için bkz: [proje için bir C# hata ayıklama yapılandırma ayarlarını](../debugger/project-settings-for-csharp-debug-configurations.md). Visual Basic için bkz: [bu konuda](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).

1. Çözüm Gezgini'nde projeye sağ tıklayıp seçin **özellikleri**.

2. Seçin bir **yayın** veya **hata ayıklama** yapıdan **yapılandırma** listesi.

2. Seçin **derleme** ayarlar ve ardından **Gelişmiş** düğmesi.

    Visual Basic'te, seçtiğiniz **derleme** ayarları ve **Gelişmiş derleme seçenekleri** yerine düğme.

3. Seçin **tam**, **taşınabilir**, veya **pdb_only** içinde **hata ayıklama bilgileri** liste kutusu (**Oluştur hata ayıklama bilgileri** Visual Basic'te).

    Taşınabilir en son platformlar arası .NET Core için biçimdir. Seçenekler hakkında daha fazla bilgi için bkz. [Gelişmiş derleme Ayarları iletişim kutusu (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md).

    ![C# derlemeleri için pdb oluşturma](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

4. Projenizi yapılandırın.

    Sembol dosyalarının yürütülebilir dosyası ya da ana çıkış dosyası olarak aynı klasörde oluşturulacak.

### <a name="generate-symbol-files-for-a-c-project"></a>Sembol dosyaları için bir C++ projesi oluşturma

1. Çözüm Gezgini'nde projeye sağ tıklayıp seçin **özellikleri**.

2. Seçin bir **yayın** veya **hata ayıklama** yapıdan **yapılandırma** listesi.

2. Altında **bağlayıcı > hata ayıklama**, seçme seçeneklerini istenen **hata ayıklama bilgisi Oluştur**.

    C++ hata ayıklama yapılandırmaları için proje ayarları hakkında ayrıntılı bilgi için bkz: [ayarları C++ hata ayıklama yapılandırması proje](../debugger/project-settings-for-a-cpp-debug-configuration.md).

4. Program veritabanı dosyaları oluşturmak için seçenekleri yapılandırın

    Çoğu C++ projelerinde varsayılan değerdir `$(OutDir)$(TargetName).pdb`, çıktı klasöründe .pdb dosyaları oluşturur.

    ![C++'ta yapılar için pdb oluşturma](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus") 

5. Projenizi yapılandırın.

    Sembol dosyalarının yürütülebilir dosyası ya da ana çıkış dosyası olarak aynı klasörde oluşturulacak.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ide'nizde Studio hata ayıklayıcısında simge (.pdb) dosyalarını ve kaynak dosyaları belirtin](../debugger/debugger-settings-and-preparation.md)  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Hata ayıklama yapılandırması proje ayarları C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Nasıl Yapılır: Yapılandırmaları Oluşturma ve Düzenleme](../ide/how-to-create-and-edit-configurations.md)
