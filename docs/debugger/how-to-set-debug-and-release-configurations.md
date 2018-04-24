---
title: 'Nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları | Microsoft Docs'
ms.custom: H1HackMay2017
ms.date: 04/10/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
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
ms.openlocfilehash: 8e2eb30d50be7348802518b7cc1b945aa88a26bd
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-set-debug-and-release-configurations-in-visual-studio"></a>Nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları Visual Studio'da
Visual Studio projeleri ayrı sürümü ve hata ayıklama yapılandırmaları programınızın. Adları kapsıyor gibi hata ayıklama için hata ayıklama sürümü ve yayın sürümü son sürüm dağıtım oluşturun.  
  
Hata ayıklama yapılandırmasını programınızın tam simgesel hata ayıklama bilgileri ve iyileştirme ile derlenir. Kaynak kodu ve oluşturulan yönergeleri arasındaki ilişkiyi daha karmaşık olduğu için en iyi duruma getirme hata ayıklama, karmaşık hale getirir.  
  
Yayın yapılandırma programınızın hiçbir simgesel hata ayıklama bilgisi içeriyor ve getirilmiştir. Hata ayıklama bilgileri .pdb dosyaları oluşturulabilir [derleyici seçeneklere bağlı olarak](#BKMK_symbols_release) kullanılan. .Pdb dosyaları oluşturma daha sonra yayın sürümü hata ayıklamak varsa çok kullanışlı olabilir.  
  
Derleme yapılandırmaları hakkında daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
Derleme yapılandırmasını değiştirebilirsiniz **yapı** menüsünde, araç çubuğundan veya proje özellik sayfalarını. Proje özelliği sayfaları dile özgü. Aşağıdaki yordam, menü ve araç derleme yapılandırmasını değiştirmek gösterilmiştir. Farklı dillerde projelerinde derleme yapılandırmasını değiştirme hakkında daha fazla bilgi için Ayrıca bakınız bölümüne bakın.  
  
## <a name="change-the-build-configuration"></a>Yapı yapılandırmasını değiştirme  
  
1.  Gelen **yapı** menüsünde, select **Configuration Manager**seçeneğini belirleyip **hata ayıklama** veya **sürüm**.  
  
2.  Araç çubuğunda seçin **hata ayıklama** veya **sürüm** gelen **çözüm yapılandırmaları** liste kutusu.  
  
     ![araç çubuğu yapı yapılandırması](../debugger/media/toolbarbuildconfiguration.png "ToolbarBuildConfiguration")  
  
     Bu araç Express sürümlerinde kullanılabilir değil. Kullanabileceğiniz **yapı çözümü F6** ve **hata ayıklamayı Başlat F5'e** menü öğeleri yapılandırmayı seçin.

## <a name="BKMK_symbols_release"></a>Simge (.pbd) dosyaları bir yapı için oluşturma

Çoğu proje türleri için .pdb dosyaları hem hata ayıklama için varsayılan olarak oluşturulan ve yayın derlemeleri, ancak varsayılan ayarlar, belirli bir proje türü ve Visual Studio sürümüne bağlı olarak farklı olur. Yapılandırabileceğiniz olup .pdb dosyaları derleyici oluşturur ve ne tür bir hata ayıklama bilgilerini içerir.

> [!IMPORTANT] 
> Hata ayıklayıcı, yalnızca yürütülebilir dosya oluşturulduğunda, oluşturulan .pdb dosyasıyla tam olarak eşleşen bir yürütülebilir dosya için bir .pdb dosyasını yükler (yani, .pdb özgün olmalı veya özgün .pdb'nin kopyasını olmalıdır). Daha fazla bilgi için bkz: [neden Visual Studio gerektiriyor hata ayıklayıcı simge dosyaları tam olarak eşleşen ile oluşturulan ikili dosyalar?](https://blogs.msdn.microsoft.com/jimgries/2007/07/06/why-does-visual-studio-require-debugger-symbol-files-to-exactly-match-the-binary-files-that-they-were-built-with/)

Her proje türü bu seçenekleri ayarlama, farklı bir şekilde olabilir.

### <a name="generate-symbol-files-for-a-c-aspnet-or-visual-basic-project"></a>Simge dosyaları bir C#, ASP.NET veya Visual Basic proje oluştur

C# hata ayıklama yapılandırması proje ayarları hakkında ayrıntılı bilgi için bkz: [proje C# hata ayıklama yapılandırması için ayarları](../debugger/project-settings-for-csharp-debug-configurations.md). Visual Basic for bkz [bu konuda](../debugger/project-settings-for-a-visual-basic-debug-configuration.md).

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **özellikleri**.

2. Seçin bir **sürüm** veya **hata ayıklama** gelen derleme **yapılandırma** listesi.

2. Seçin **yapı** ayarlar ve ardından **Gelişmiş** düğmesi.

    Visual Basic'te, seçtiğiniz **derleme** ayarları ve **Gelişmiş derleme seçenekleri** yerine düğmesine tıklayın.

3. Seçin **tam**, **taşınabilir**, veya **pdb_only** içinde **hata ayıklama bilgisi** liste kutusu (**Generate hata ayıklama bilgileri** Visual Basic'te).

    Taşınabilir biçimi en son .NET Core platformlar arası biçimidir. Seçenekler hakkında daha fazla bilgi için bkz: [Gelişmiş derleme Ayarları iletişim kutusu (C#)](../ide/reference/advanced-build-settings-dialog-box-csharp.md).

    ![C# derlemeleri için pdb üret](../debugger/media/dbg_project_properties_pdb_csharp.png "GeneratePDBsForCSharp")

4. Projenizi yapılandırın.

    Simge dosyaları aynı klasörde yürütülebilir dosya veya ana çıktı dosyası oluşturuluyor.

### <a name="generate-symbol-files-for-a-c-project"></a>C++ projesi için simge dosyaları oluştur

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **özellikleri**.

2. Seçin bir **sürüm** veya **hata ayıklama** gelen derleme **yapılandırma** listesi.

2. Altında **bağlayıcı > hata ayıklama**, select istenen seçeneklerini **hata ayıklama bilgisi üret**.

    C++ hata ayıklama yapılandırması proje ayarları hakkında ayrıntılı bilgi için bkz: [proje C++ hata ayıklama yapılandırması için ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md).

4. Program veritabanı dosyaları oluşturmak için seçenekleri yapılandırın

    Çoğu C++ projelerinde, varsayılan değer: `$(OutDir)$(TargetName).pdb`, çıkış klasörüne .pdb dosyaları oluşturur.

    ![C++'ta yapılar için pdb oluşturmak](../debugger/media/dbg_project_properties_pdb_cplusplus.png "GeneratePDBsforCPlusPlus") 

5. Projenizi yapılandırın.

    Simge dosyaları aynı klasörde yürütülebilir dosya veya ana çıktı dosyası oluşturuluyor.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visua Studio hata ayıklayıcısında simge (.pdb) dosyaları ve kaynak dosyaları belirtin](../debugger/debugger-settings-and-preparation.md)  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [C++ hata ayıklama yapılandırması proje ayarları](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Proje ayarları için C# hata ayıklama yapılandırmaları](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Nasıl Yapılır: Yapılandırmaları Oluşturma ve Düzenleme](../ide/how-to-create-and-edit-configurations.md)