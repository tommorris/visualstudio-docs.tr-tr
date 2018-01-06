---
title: "Derleme sayfası, Proje Tasarımcısı (C#) | Microsoft Docs"
ms.custom: 
ms.date: 06/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cs.ProjectPropertiesBuild
helpviewer_keywords:
- Build options [C#]
- Project Designer, Build page
ms.assetid: 77ff1bfc-d633-4634-ba29-9afdb6d7e362
caps.latest.revision: "43"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: bc470eb36e700f136fec57e208c5bd920ea5e073
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="build-page-project-designer-c"></a>Derleme Sayfası, Proje Tasarımcısı (C#)
Kullanım **yapı** sayfasında **Proje Tasarımcısı** projenin yapı yapılandırma özelliklerini belirtmek için. Bu sayfayı uygulandığı [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] yalnızca projeleri.  

Erişim için **yapı** sayfası, proje düğümüne seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **Görünüm**, **özellik sayfaları** menüsünde. Proje Tasarımcısı belirdiğinde seçin **yapı** sekmesi.  

[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  

## <a name="configuration-and-platform"></a>Yapılandırması ve platformu  
Aşağıdaki seçenekler yapılandırma ve görüntülemek veya değiştirmek için platform seçmenizi sağlar.  

> [!NOTE]
>  Basitleştirilmiş derleme yapılandırmalarını, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. Bu nedenle, bu seçenekleri görüntülenmiyor. Daha fazla bilgi için bkz: [hata ayıklama ve yayın proje yapılandırmaları](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  

**Yapılandırma**  
Görüntülemek veya değiştirmek için hangi yapılandırma ayarlarını belirtir. Ayarları **etkin (hata ayıklama)** (varsayılan değer budur), **hata ayıklama**, **sürüm**, veya **tüm yapılandırmaları**.  

**Platform**  
Görüntülemek veya değiştirmek için hangi platform ayarlarını belirtir. Varsayılan ayar **etkin (herhangi bir CPU)**. Etkin platformu kullanarak değiştirebilirsiniz **Configuration Manager**. Daha fazla bilgi için bkz: [nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../../ide/how-to-create-and-edit-configurations.md).  

## <a name="general"></a>Genel  
Aşağıdaki seçenekler birkaç C# Derleyici ayarları yapılandırmanıza olanak sağlar.  

**Koşullu derleme simgeleri**  
Koşullu derleme gerçekleştirileceği simgeleri belirtir. Simgeler noktalı virgülle ayırın (";"). Daha fazla bilgi için bkz: [/ define (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/define-compiler-option).  

**Hata ayıklama sabiti tanımlayın**  
Tüm kaynak kodu dosyaları, uygulamanızda sembol olarak hata ayıklama tanımlar. Bu seçeneğin seçilmesi eşdeğerdir kullanmaya `/define:DEBUG` komut satırı seçeneği.  

**İzleme sabiti tanımlayın**  
Tüm kaynak kodu dosyaları, uygulamanızda sembol olarak izleme tanımlar. Bu seçeneğin seçilmesi eşdeğerdir kullanmaya `/define:TRACE` komut satırı seçeneği.  

**Platform hedefi**  
Çıkış dosyası tarafından hedeflenecek işlemci belirtir. Seçin **x86** herhangi 32-bit Intel dönük olarak uyumlu işlemci seçin **x64** herhangi 64-bit Intel dönük olarak uyumlu işlemci seçin **ARM** ARM işlemcileri için veya seçin **Tüm CPU** tüm işlemci kabul edilebilir olduğunu belirtmek için. **Tüm CPU** çok çeşitli donanım üzerinde çalıştırmak uygulama izin verdiğinden projeleri için varsayılan değerdir.  

Daha fazla bilgi için bkz: [/Platform (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/platform-compiler-option).  

**32-bit tercih**  
Varsa **Prefer32 bit** onay kutusu seçiliyse, uygulama bir 32 bit uygulama olarak, Windows'un 32 bit ve 64 bit sürümlerinde çalışır. Onay kutusu işaretli değilse, uygulama bir 32 bit uygulama olarak 32 bit sürümleri, Windows ve Windows 64 bit sürümlerinde 64-bit uygulama olarak çalışır.  

64-bit uygulama, işaretçi boyutu iki katına çıkar bir uygulamayı çalıştırmak ve yalnızca 32-bit diğer kitaplıklarla birlikte uyumluluk sorunları ortaya çıkabilir. Yalnızca 4 GB'den fazla bellek gerekiyor veya bir önemli performans iyileştirme 64-bit yönergelerinizi bir 64-bit uygulamayı çalıştırmak kullanışlıdır.  

Bu onay kutusu, yalnızca aşağıdaki koşulların tümü doğruysa, kullanılabilir:  

-   Üzerinde **yapı sayfasını**, **Platform hedefi** listesinin **herhangi bir CPU**.  

-   Üzerinde **uygulama sayfası**, **çıktı türü** listesi, projenin bir uygulaması olduğunu belirtir.  

-   Üzerinde **uygulama sayfası**, **hedef framework** listesi, .NET Framework 4.5 belirtir.  


**Güvenli olmayan kod izin ver**  
Kullanan kodu sağlar [güvensiz](/dotnet/csharp/language-reference/keywords/unsafe) derlemek için anahtar sözcüğü. Daha fazla bilgi için bkz: [/ unsafe (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/unsafe-compiler-option).  

**Kod en iyi duruma getirme**  
Etkinleştirmek veya devre dışı çıkış dosyanızın daha küçük, daha hızlı ve daha verimli olmak için derleyici tarafından gerçekleştirilen en iyi duruma getirme. Daha fazla bilgi için bkz: [/ optimize (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/optimize-compiler-option).  

## <a name="errors-and-warnings"></a>Hatalar ve uyarılar  
Aşağıdaki ayarlar, hata ve uyarı seçeneklerini oluşturma işlemi için yapılandırmak için kullanılır.  

**Uyarı düzeyi**  
Derleyici uyarılarını görüntülemek için düzeyini belirtir. Daha fazla bilgi için bkz: [/ warn (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warn-compiler-option).  

**Uyarıları bastırma**  
Derleyicinin bir veya daha fazla uyarı oluşturma becerisini engeller. Birden çok uyarı rakam, virgül veya noktalı virgül ile ayırın. Daha fazla bilgi için bkz: [/nowarn (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/nowarn-compiler-option).  

## <a name="treat-warnings-as-errors"></a>Uyarıları hata ele  
Aşağıdaki ayarlar, hangi uyarıları hata olarak kabul edilir belirtmek için kullanılır. Derleme bir uyarı karşılaştığında hatayla geri dönmek için hangi koşullarda belirtmek için aşağıdaki seçeneklerden birini seçin. Daha fazla bilgi için bkz: [/warnaserror (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/warnaserror-compiler-option).  

**Yok**  
Hiçbir uyarıları hata olarak değerlendirir.  

**Belirli uyarıları**  
Belirtilen uyarıları hata olarak değerlendirir. Birden çok uyarı rakam, virgül veya noktalı virgül ile ayırın.  

**Tüm**  
Tüm uyarıları hata olarak değerlendirir.  

## <a name="output"></a>Çıkış  
Aşağıdaki ayarlar, yapılandırma işlemi çıktı seçeneklerini yapılandırmak için kullanılır.  

**Çıkış yolu**  
Bu projenin yapılandırması için çıkış dosyalarının konumunu belirtir. Bu kutuya yapı çıktı yolunu girin veya seçin **Gözat** düğmesine bir yol belirtin. Yolun göreli olduğunu unutmayın; mutlak bir yol girin, göreli olarak kaydedilir. Varsayılan yolun bin\Debug veya bin\Release olduğundan\\. Daha fazla bilgi için bkz: [hata ayıklama ve yayın proje yapılandırmaları](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  

Basitleştirilmiş derleme yapılandırmalarını, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. **Yapı** komutunu **hata ayıklama** menü (F5) bağımsız olarak, hata ayıklama konumda yapı koyacaktır **çıkış yolu** , belirtin. Ancak, **yapı** komutunu **yapı** menüsü, belirttiğiniz konuma yerleştirir. Daha fazla bilgi için bkz: [hata ayıklama ve yayın proje yapılandırmaları](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e).  

**XML belge dosyası**  
Hangi belgeleri açıklamaları işlenecek dosya adını belirtir. Daha fazla bilgi için bkz: [/doc (C# Derleyici Seçenekleri)](/dotnet/csharp/language-reference/compiler-options/doc-compiler-option).  

**COM birlikte çalışma için kaydolun**  
Yönetilen uygulama ile etkileşim kurmak bir COM nesnesi izin veren COM nesnesi (bir COM aranabilir sarmalayıcısı), yönetilen uygulamanızın açığa çıkarır gösterir. **Çıktı türü** özelliğinde [uygulama sayfası](../../ide/reference/application-page-project-designer-visual-basic.md) , **Proje Tasarımcısı** bu uygulama ayarlanmalıdır için **sınıf kitaplığı** içinde için sipariş **kaydetmek için COM birlikte çalışma** özelliği kullanılabilir. Dahil ve örnek bir sınıf için [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] bkz: uygulama ve bir COM nesnesi olarak açığa [örnek COM sınıfı](/dotnet/csharp/programming-guide/interop/example-com-class).  

**Seri hale getirme derlemesi oluşturma**  
Derleyici XML serileştirme derlemelerini oluşturmak için XML seri hale getirici Oluşturma Aracı (Sgen.exe) kullanıp kullanmayacağını belirtir. Serileştirme derlemelerini başlatma performansını geliştirebilir <xref:System.Xml.Serialization.XmlSerializer> kodunuzda türleri serileştirmek için o sınıfın kullandıysanız. Varsayılan olarak, bu seçeneği ayarlanmış **otomatik**, belirten yalnızca kullandıysanız, serileştirme derlemelerini oluşturulması <xref:System.Xml.Serialization.XmlSerializer> kodunuzda XML türleri kodlamak için. **Kapalı** serileştirme derlemelerini hiçbir zaman, kodunuzu kullanıp kullanmadığını bağımsız olarak oluşturulmasını belirtir <xref:System.Xml.Serialization.XmlSerializer>. **Üzerinde** serileştirme derlemelerini her zaman oluşturulması gerektiğini belirtir. Serileştirme derlemelerini adlı `TypeName`. XmlSerializers.dll. Daha fazla bilgi için bkz: [XML seri hale getirici Oluşturma Aracı (Sgen.exe)](/dotnet/framework/serialization/xml-serializer-generator-tool-sgen-exe).  

**Gelişmiş**  
Görüntülemek için tıklatın [Gelişmiş derleme Ayarları iletişim kutusu (C#)](../../ide/reference/advanced-build-settings-dialog-box-csharp.md) iletişim kutusu.  

## <a name="see-also"></a>Ayrıca Bkz.  
[Proje Özellikleri başvurusu](../../ide/reference/project-properties-reference.md)   
[C# Derleyici Seçenekleri](/dotnet/csharp/language-reference/compiler-options/index)
