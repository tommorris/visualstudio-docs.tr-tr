---
title: Derleme Sayfası, Proje Tasarımcısı (C#)
ms.date: 06/20/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuild
helpviewer_keywords:
- Build options [C#]
- Project Designer, Build page
ms.assetid: 77ff1bfc-d633-4634-ba29-9afdb6d7e362
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b003b3f965ab4f3857e2a532ae715d99533aa8e7
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="build-page-project-designer-c"></a>Derleme Sayfası, Proje Tasarımcısı (C#)
Kullanım **yapı** sayfasında **Proje Tasarımcısı** projenin yapı yapılandırma özelliklerini belirtmek için. Bu sayfayı uygulandığı [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] yalnızca projeleri.

Erişim için **yapı** sayfası, proje düğümüne seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **Görünüm**, **özellik sayfaları** menüsünde. Proje Tasarımcısı belirdiğinde seçin **yapı** sekmesi.

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]

## <a name="configuration-and-platform"></a>Yapılandırması ve platformu
Aşağıdaki seçenekler yapılandırma ve görüntülemek veya değiştirmek için platform seçmenizi sağlar.

> [!NOTE]
> Basitleştirilmiş derleme yapılandırmalarını, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. Bu nedenle, bu seçenekleri görüntülenmiyor. Daha fazla bilgi için bkz: [nasıl yapılır: ayarlama hata ayıklama ve yayın yapılandırmaları](../../debugger/how-to-set-debug-and-release-configurations.md).

**Yapılandırma** görüntülemek veya değiştirmek için hangi yapılandırma ayarlarını belirtir. Ayarları **etkin (hata ayıklama)** (varsayılan değer budur), **hata ayıklama**, **sürüm**, veya **tüm yapılandırmaları**.

**Platform** görüntülemek veya değiştirmek için hangi platform ayarlarını belirtir. Varsayılan ayar **etkin (herhangi bir CPU)**. Etkin platformu kullanarak değiştirebilirsiniz **Configuration Manager**. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../../ide/how-to-create-and-edit-configurations.md).

## <a name="general"></a>Genel
Aşağıdaki seçenekler birkaç C# Derleyici ayarları yapılandırmanıza olanak sağlar.

**Koşullu derleme simgeleri** koşullu derleme gerçekleştirileceği simgeleri belirtir. Simgeler noktalı virgülle ayırın (";"). Daha fazla bilgi için bkz: [/ define (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).

**Hata ayıklama sabiti tanımlamak** dosyaları uygulamanızda hata ayıklama tanımlayan tüm kaynak kodda bir simge olarak. Bu seçeneğin seçilmesi eşdeğerdir kullanmaya `/define:DEBUG` komut satırı seçeneği.

**İzleme sabiti tanımlamak** tanımlayan izleme tüm kaynak kodda bir simge olarak uygulamanızda dosyaları. Bu seçeneğin seçilmesi eşdeğerdir kullanmaya `/define:TRACE` komut satırı seçeneği.

**Platform hedefi** çıktı dosyası tarafından hedeflenecek işlemci belirtir. Seçin **x86** herhangi 32-bit Intel dönük olarak uyumlu işlemci seçin **x64** herhangi 64-bit Intel dönük olarak uyumlu işlemci seçin **ARM** ARM işlemcileri için veya seçin **Tüm CPU** tüm işlemci kabul edilebilir olduğunu belirtmek için. **Tüm CPU** çok çeşitli donanım üzerinde çalıştırmak uygulama izin verdiğinden projeleri için varsayılan değerdir.

Daha fazla bilgi için bkz: [/Platform (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).

**32-bit tercih** varsa **Prefer32 bit** onay kutusu seçiliyse, uygulama bir 32 bit uygulama olarak, Windows'un 32 bit ve 64 bit sürümlerinde çalışır. Onay kutusu işaretli değilse, uygulama bir 32 bit uygulama olarak 32 bit sürümleri, Windows ve Windows 64 bit sürümlerinde 64-bit uygulama olarak çalışır.

64-bit uygulama, işaretçi boyutu iki katına çıkar bir uygulamayı çalıştırmak ve yalnızca 32-bit diğer kitaplıklarla birlikte uyumluluk sorunları ortaya çıkabilir. Yalnızca 4 GB'den fazla bellek gerekiyor veya bir önemli performans iyileştirme 64-bit yönergelerinizi bir 64-bit uygulamayı çalıştırmak kullanışlıdır.

Bu onay kutusu, yalnızca aşağıdaki koşulların tümü doğruysa, kullanılabilir:

-   Üzerinde **yapı sayfasını**, **Platform hedefi** listesinin **herhangi bir CPU**.

-   Üzerinde **uygulama sayfası**, **çıktı türü** listesi, projenin bir uygulaması olduğunu belirtir.

-   Üzerinde **uygulama sayfası**, **hedef framework** listesi, .NET Framework 4.5 belirtir.


**Güvenli olmayan kod izin** kullanan verir kodu [güvensiz](/dotnet/csharp/language-reference/keywords/unsafe) derlemek için anahtar sözcüğü. Daha fazla bilgi için bkz: [/ unsafe (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).

**Kodu en iyi duruma** etkinleştirmek veya devre dışı çıkış dosyanızın daha küçük, daha hızlı ve daha verimli olmak için derleyici tarafından gerçekleştirilen en iyi duruma getirme. Daha fazla bilgi için bkz: [/ optimize (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).

## <a name="errors-and-warnings"></a>Hatalar ve uyarılar
Aşağıdaki ayarlar, hata ve uyarı seçeneklerini oluşturma işlemi için yapılandırmak için kullanılır.

**Uyarı düzeyi** derleyici uyarıları görüntülemek için düzeyini belirtir. Daha fazla bilgi için bkz: [/ warn (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).

**Uyarıları bastırma** derleyicinin bir veya daha fazla uyarı oluşturma becerisini engeller. Birden çok uyarı rakam, virgül veya noktalı virgül ile ayırın. Daha fazla bilgi için bkz: [/nowarn (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).

## <a name="treat-warnings-as-errors"></a>Uyarıları hata ele
Aşağıdaki ayarlar, hangi uyarıları hata olarak kabul edilir belirtmek için kullanılır. Derleme bir uyarı karşılaştığında hatayla geri dönmek için hangi koşullarda belirtmek için aşağıdaki seçeneklerden birini seçin. Daha fazla bilgi için bkz: [/warnaserror (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).

**Hiçbiri** hiçbir uyarıları hata olarak kabul eder.

**Belirli uyarıları** belirtilen uyarıları hata olarak kabul eder. Birden çok uyarı rakam, virgül veya noktalı virgül ile ayırın.

**Tüm** tüm uyarıları hata olarak kabul eder.

## <a name="output"></a>Çıkış
Aşağıdaki ayarlar, yapılandırma işlemi çıktı seçeneklerini yapılandırmak için kullanılır.

**Çıkış yolu** bu projenin yapılandırması için çıkış dosyalarının konumunu belirtir. Bu kutuya yapı çıktı yolunu girin veya seçin **Gözat** düğmesine bir yol belirtin. Yolun göreli olduğunu unutmayın; mutlak bir yol girin, göreli olarak kaydedilir. Varsayılan yolun bin\Debug veya bin\Release olduğundan\\.

Basitleştirilmiş derleme yapılandırmalarını, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. **Yapı** komutunu **hata ayıklama** menü (F5) bağımsız olarak, hata ayıklama konumda yapı koyacaktır **çıkış yolu** , belirtin. Ancak, **yapı** komutunu **yapı** menüsü, belirttiğiniz konuma yerleştirir. Daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../../ide/understanding-build-configurations.md).

**XML belge dosyası** hangi belgeleri açıklamaları işlenmeyecek bir dosya adını belirtir. Daha fazla bilgi için bkz: [/doc (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).

**COM birlikte çalışma için kayıt** , yönetilen uygulamanızın, yönetilen uygulamanızın ile etkileşim kurmak bir COM nesnesi izin veren COM nesnesi (bir COM aranabilir sarmalayıcısı) açığa çıkarır gösterir. **Çıktı türü** özelliğinde [uygulama sayfası](../../ide/reference/application-page-project-designer-visual-basic.md) , **Proje Tasarımcısı** bu uygulama ayarlanmalıdır için **sınıf kitaplığı** içinde için sipariş **kaydetmek için COM birlikte çalışma** özelliği kullanılabilir. Dahil ve örnek bir sınıf için [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] bkz: uygulama ve bir COM nesnesi olarak açığa [örnek COM sınıfı](/dotnet/csharp/programming-guide/interop/example-com-class).

**Seri hale getirme derlemesi oluşturmak** derleyici XML serileştirme derlemelerini oluşturmak için XML seri hale getirici Oluşturma Aracı (Sgen.exe) kullanıp kullanmayacağını belirtir. Serileştirme derlemelerini başlatma performansını geliştirebilir <xref:System.Xml.Serialization.XmlSerializer> kodunuzda türleri serileştirmek için o sınıfın kullandıysanız. Varsayılan olarak, bu seçeneği ayarlanmış **otomatik**, belirten yalnızca kullandıysanız, serileştirme derlemelerini oluşturulması <xref:System.Xml.Serialization.XmlSerializer> kodunuzda XML türleri kodlamak için. **Kapalı** serileştirme derlemelerini hiçbir zaman, kodunuzu kullanıp kullanmadığını bağımsız olarak oluşturulmasını belirtir <xref:System.Xml.Serialization.XmlSerializer>. **Üzerinde** serileştirme derlemelerini her zaman oluşturulması gerektiğini belirtir. Serileştirme derlemelerini adlı `TypeName`. XmlSerializers.dll. Daha fazla bilgi için bkz: [XML seri hale getirici Oluşturma Aracı (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).

**Gelişmiş** görüntülemek için tıklatın [Gelişmiş derleme Ayarları iletişim kutusu (C#)](../../ide/reference/advanced-build-settings-dialog-box-csharp.md) iletişim kutusu.

## <a name="see-also"></a>Ayrıca Bkz.

- [Proje Özellikleri Başvurusu](../../ide/reference/project-properties-reference.md)
- [C# Derleyici Seçenekleri](/dotnet/csharp/language-reference/compiler-options/index)