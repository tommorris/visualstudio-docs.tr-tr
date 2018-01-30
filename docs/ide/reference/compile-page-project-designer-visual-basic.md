---
title: "Derle sayfası, Proje Tasarımcısı (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.ProjectPropertiesCompile
helpviewer_keywords:
- compilation, Visual Basic projects
- compilation, options [Visual Basic]
- compilers, Visual Basic options
- compilation, instructions [Visual Basic]
- compiler options, Visual Basic
- Project Designer, Compile page
- Compile page in Project Designer
ms.assetid: b2a80230-906e-4e85-b3e0-fcd9c40426e1
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 32a883c1a04dc6ab5189cd5b2e5173406c098f6d
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="compile-page-project-designer-visual-basic"></a>Derleme Sayfası, Proje Tasarımcısı (Visual Basic)
Kullanım **derleme** derleme yönergeleri belirtmek için Proje Tasarımcısı'nın sayfası. Bu sayfada Gelişmiş derleyici seçenekleri ve ön derleme veya sonrası derleme olayları de belirtebilirsiniz.  
  
Erişim için **derleme** sayfası, proje düğümüne seçin (değil **çözüm** düğümü) içinde **Çözüm Gezgini**. Ardından **proje**, **özellikleri** menü çubuğunda. Proje Tasarımcısı görüntülendiğinde **derleme** sekmesi.  
  
[!INCLUDE[note_settings_general](../../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="configuration-and-platform"></a>Yapılandırması ve platformu  
 Aşağıdaki ayarları görüntülemek veya değiştirmek için platform ve yapılandırma seçmenizi sağlar.  
  
> [!NOTE]
> Basitleştirilmiş derleme yapılandırmalarını, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. Bu nedenle, **yapılandırma** ve **Platform** listelerinde görüntülenmez.
  
 **Yapılandırma**  
 Görüntülemek veya değiştirmek için hangi yapılandırma ayarlarını belirtir. Ayarlar **hata ayıklama** (varsayılan), **sürüm**, veya **tüm yapılandırmaları**. Daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../../ide/understanding-build-configurations.md) ve [nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../../ide/how-to-create-and-edit-configurations.md).
  
 **Platform**  
 Görüntülemek veya değiştirmek için hangi platform ayarlarını belirtir. Belirleyebileceğiniz **herhangi bir CPU** (varsayılan), **x64**, veya **x86**.
  
## <a name="compiler-configuration-options"></a>Derleyici yapılandırma seçenekleri  
 Aşağıdaki ayarlar, derleyici yapılandırma seçeneklerini ayarlamanıza olanak verir.  
  
 **Derleme çıktı yolu**  
 Bu projenin yapılandırması için çıkış dosyalarının konumunu belirtir. Derleme çıktı yolu bu kutuya yazın ya da tıklatın **Gözat** düğmesine tıklayarak bir yol seçin. Yolun göreli olduğunu unutmayın; mutlak bir yol girin, göreli olarak kaydedilir. Varsayılan yol bin\Debug\ bin\Release mi\\.
  
 Basitleştirilmiş derleme yapılandırmalarını, proje sistemi sürümünü veya bir hata ayıklama geliştirmek belirler. **Yapı** komutunu **hata ayıklama** menü (F5) bağımsız olarak, hata ayıklama konumda yapı koyacaktır **çıkış yolu** , belirtin. Ancak, **yapı** komutunu **yapı** menüsü, belirttiğiniz konuma yerleştirir.
  
 **Açık seçeneği**  
 Örtük bildirimi değişkenlerin izin verilip verilmeyeceğini belirtir. Seçin **üzerinde** değişkenlerin açıkça bildirilmesini istemek için. Kullanıldıkları önce değişkenleri bildirilmeyen varsa bu derleyici hatalarını raporlamak neden olur. Seçin **kapalı** değişkenleri örtük bildirimi izin vermek için.  
  
 Bu ayar karşılık gelir [/optionexplicit](/dotnet/visual-basic/reference/command-line-compiler/optionexplicit) derleyici seçeneği.  
  
 Kaynak kodu dosyasının içeriyorsa bir [Option Explicit deyimi](/dotnet/visual-basic/language-reference/statements/option-explicit-statement), `On` veya `Off` deyimindeki değerini geçersiz kılar **Option Explicit** ayarı **derleme Sayfa**.  
  
 Yeni bir proje oluşturduğunuzda **Option Explicit** ayarı **derleme sayfa** değerine ayarlanmış **Option Explicit** ayarı **seçenekleri**  iletişim kutusu. Görüntülemek veya bu iletişim kutusundaki ayarı değiştirmek için **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **VB varsayılanları**. İlk varsayılan ayarını **Option Explicit** içinde **VB varsayılanları** olan **üzerinde**.  
  
 Ayarı **Option Explicit** için `Off` genellikle iyi bir uygulama değildir. Bir değişken adı konumlarda programını çalıştırdığınızda, beklenmeyen sonuçlara neden olacağından bir veya daha fazla hata hatalı.  
  
 **Option strict**  
Kesin türü anlamları zorlanıp zorlanmayacağını belirtir. Zaman **Option Strict** olan **üzerinde**, aşağıdaki durumlardan bir derleme zamanı hatasına neden:  
  
-   Örtük daraltma dönüşümleri  
  
-   Geç bağlama  
  
-   Örtük sonuçlanan yazarak bir `Object` türü  
  
Daraltma dönüştürme örtük veri türü dönüşümü olduğunda örtük daraltma dönüştürme hataları oluşur. Daha fazla bilgi için bkz: [Option Strict deyimi](/dotnet/visual-basic/language-reference/statements/option-strict-statement), [dolaylı ve açık dönüştürmeler](/dotnet/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions), ve [Widening ve daraltma dönüşümleri](/dotnet/visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions).  
  
Bir özellik veya yöntem türü olarak bildirilmiş bir değişkenin atandığında bir nesne geç bağlama `Object`. Daha fazla bilgi için bkz: [Option Strict deyimi](/dotnet/visual-basic/language-reference/statements/option-strict-statement) ve [erken ve geç bağlama](/dotnet/visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding).  
  
Örtük nesne türü hatalar ortaya uygun bir tür bulunamadığında bildirilen bir değişken için bu nedenle bir tür çıkarımı yapılan `Object` algılanır. Kullandığınızda bu öncelikle oluşur. bir `Dim` kullanmadan bir değişken bildirmek için deyimi bir `As` yan tümcesi ve `Option Infer` kapalıdır. Daha fazla bilgi için bkz: [Option Strict deyimi](/dotnet/visual-basic/language-reference/statements/option-strict-statement), [Option Infer deyimi](/dotnet/visual-basic/language-reference/statements/option-infer-statement)ve [Visual Basic dil belirtimi](/dotnet/visual-basic/reference/language-specification).  
  
**Option Strict** ayarı karşılık gelen [/optionstrict](/dotnet/visual-basic/reference/command-line-compiler/optionstrict) derleyici seçeneği.  
  
Kaynak kodu dosyasının içeriyorsa bir [Option Strict deyimi](/dotnet/visual-basic/language-reference/statements/option-strict-statement), `On` veya `Off` deyimindeki değerini geçersiz kılar **Option Strict** ayarı **derleme sayfası** .  
  
Bir proje oluşturduğunuzda **Option Strict** ayarı **derleme sayfa** değerine ayarlanmış **Option Strict** ayarı **seçenekleri** iletişim kutusu. Görüntülemek veya bu iletişim kutusundaki ayarı değiştirmek için **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **VB varsayılanları**. İlk varsayılan ayarını **Option Strict** içinde **VB varsayılanları** olan **devre dışı**.  
  
**Bireysel uyarılar katı seçeneği.** **Uyarı yapılandırmaları** bölümünü **derleme sayfa** derleme zamanı hatasına neden olan üç koşulları karşılık gelen ayarlara sahip olduğunda `Option Strict` açıktır. Bu ayarlar aşağıda verilmiştir:  
  
-   **Örtük dönüştürme**  
  
-   **Geç bağlama; Çalışma zamanında çağrısı başarısız olabilir**  
  
-   **Örtük türü; kabul nesnesi**  
  
Ayarladığınızda **Option Strict** için **üzerinde**, bu uyarı yapılandırma ayarları üçünü kümesine **hata**. Ayarladığınızda **Option Strict** için **kapalı**, tüm üç ayarları ayarlamak **hiçbiri**.  
  
Tek tek her uyarı yapılandırma ayarını değiştirebilirsiniz **hiçbiri**, **uyarı**, veya **hata**. Tüm üç uyarı yapılandırma ayarları ayarlandıysa **hata**, `On` görünür `Option strict` kutusu. Üç ayarlandıysa **hiçbiri**, `Off` bu kutuda görünür. Bu ayarlar, herhangi bir birleşimini için **(özel)** görüntülenir.  
  
**Seçenek karşılaştırma**  
Kullanılacak dize karşılaştırma türünü belirtir. Seçin **ikili** derleyicinin ikili, büyük küçük harf duyarlı dize karşılaştırmalarını kullanmasını istemek için. Seçin **metin** metin yerel ayarlara özgü, büyük küçük harf duyarsız dize karşılaştırmalarını kullanılacak.  
  
Bu ayar karşılık gelir [/optioncompare](/dotnet/visual-basic/reference/command-line-compiler/optioncompare) derleyici seçeneği.  
  
Kaynak kodu dosyasının içeriyorsa bir [Option Compare deyimi](/dotnet/visual-basic/language-reference/statements/option-compare-statement), `Binary` veya `Text` deyimindeki değerini geçersiz kılar **seçeneği karşılaştırmak** ayarı **derleme Sayfa**.  
  
Bir proje oluşturduğunuzda **seçeneği karşılaştırmak** ayarı **derleme sayfa** değerine ayarlanır **seçeneği karşılaştırmak** ayarı **seçenekleri** iletişim kutusu. Görüntülemek veya bu iletişim kutusundaki ayarı değiştirmek için **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **VB varsayılanları**. İlk varsayılan ayarını **seçeneği karşılaştırmak** içinde **VB varsayılanları** olan **ikili**.  
  
**Option Infer**  
Yerel türü çıkarımı değişken bildirimlerinde izin verilip verilmeyeceğini belirtir. Seçin **üzerinde** yerel türü çıkarımı kullanımına izin vermek için. Seçin **kapalı** blok yerel türü çıkarımı için.  
  
Bu ayar karşılık gelir [/optioninfer](/dotnet/visual-basic/reference/command-line-compiler/optioninfer) derleyici seçeneği.  
  
Kaynak kodu dosyasının içeriyorsa bir [Option Infer deyimi](/dotnet/visual-basic/language-reference/statements/option-infer-statement), `On` veya `Off` deyimindeki değerini geçersiz kılar **Option Infer** ayarı **derleme sayfası** .  
  
Bir proje oluşturduğunuzda **Option Infer** ayarı **derleme sayfa** değerine ayarlanmış **Option Infer** ayarı **seçenekleri**iletişim kutusu. Görüntülemek veya bu iletişim kutusundaki ayarı değiştirmek için **Araçları** menüsünde tıklatın **seçenekleri**. İçinde **seçenekleri** iletişim kutusunda, genişletin **projeler ve çözümler**ve ardından **VB varsayılanları**. İlk varsayılan ayarını **Option Infer** içinde **VB varsayılanları** olan **üzerinde**.  
  
**Hedef CPU**  
Çıkış dosyası tarafından hedeflenecek işlemci belirtir. Belirtin **x86** herhangi 32-bit Intel dönük olarak uyumlu işlemci **x64** herhangi bir 64-bit Intel dönük olarak uyumlu işlemci için **ARM** tüm ARM işlemci veya **herhangi bir CPU**  tüm işlemci kabul edilebilir olduğunu belirtmek için. **Tüm CPU** uygulamanın donanım türleri üzerinde en büyük sayı çalışmasına izin verdiğinden yeni projeler için varsayılan değerdir.  
  
Daha fazla bilgi için bkz: [/Platform (Visual Basic)](/dotnet/visual-basic/reference/command-line-compiler/platform).  
  
**32-bit tercih**  
Varsa **Prefer32 bit** onay kutusu seçiliyse, uygulama bir 32 bit uygulama olarak, Windows'un 32 bit ve 64 bit sürümlerinde çalışır. Aksi takdirde uygulama Windows ve Windows 64 bit sürümlerinde 64-bit uygulama olarak 32 bit sürümleri üzerinde bir 32 bit uygulama olarak çalışır.  
  
64 bit bir uygulama işaretçi boyutu iki katına çıkarır ve yalnızca 32-bit kitaplıkları ile uyumluluk sorunlarına yol açabilir gibi çalışır. Yalnızca önemli ölçüde daha hızlı çalışır veya 4 GB'den fazla bellek gereken bir uygulamayı 64-bit olarak çalıştırmak için mantıklıdır.  
  
Bu onay kutusu, yalnızca aşağıdaki koşulların tümü doğruysa, kullanılabilir:  
  
-   Üzerinde **derle sayfası**, **hedef CPU** listesinin **herhangi bir CPU**.  
  
-   Üzerinde **uygulama sayfası**, **uygulama türü** listesi, projenin bir uygulaması olduğunu belirtir.  
  
-   Üzerinde **uygulama sayfası**, **hedef framework** listesi, .NET Framework 4.5 belirtir.  
  
**Uyarı yapılandırmaları**  
Bu tabloda yapı koşullar ve karşılık gelen bildirim düzeyini **hiçbiri**, **uyarı**, veya **hata** her.  
  
Varsayılan olarak, tüm derleyici uyarıları derleme sırasında görev listesine eklenir. Seçin **tüm uyarıları devre dışı bırakmak** görevlendirin sorunu uyarılar veya hatalar için. Seçin **tüm uyarıları hata ele** derleyici uyarıları düzeltilmesi gereken hata olarak değerlendirmek istiyorsanız.  
  
**Tüm uyarıları devre dışı bırak**  
Derleyici belirtildiği gibi bildirimler yayınlamasına izin verilip verilmeyeceğini belirtir **koşul ve bildirim** bu belgenin önceki bölümlerinde açıklanan tablo. Varsayılan olarak, bu onay kutusu işaretli değildir. Görevlendirin uyarılar veya hatalar değil vermek için bu onay kutusunu seçin.  
  
Bu ayar karşılık gelir [/nowarn](/dotnet/visual-basic/reference/command-line-compiler/nowarn) derleyici seçeneği.  
  
**Tüm uyarıları hata olarak işle**  
Uyarıları ele alınacağını belirler. Tüm uyarı bildirimleri için ayarlanmış olarak kalır, böylece varsayılan olarak, bu onay kutusu, temizlenir **uyarı**. Tüm uyarı bildirimleri değiştirmek için bu onay kutusunu işaretleyin **hata**.  
  
Bu seçenek yalnızca **tüm uyarıları devre dışı bırakmak** temizlenir.  
  
**XML belge dosyası oluşturma**  
Belge bilgi oluşturulup oluşturulmayacağını belirtir. Varsayılan olarak, belge bilgileri oluşturmak ve bir XML dosyasına eklemek için derleyici bilgilendirerek bu onay kutusu seçilidir. Belge oluşturmamayı görevlendirin için bu onay kutusunu temizleyin.  
  
Bu ayar karşılık gelir [/doc](/dotnet/visual-basic/reference/command-line-compiler/doc) derleyici seçeneği.  
  
**COM birlikte çalışma için kaydolun**  
Yönetilen uygulamanızın uygulama ile etkileşim kurmak bir COM nesnesi sağlayan bir COM nesnesi (COM aranabilir sarmalayıcısı) kullanıma olup olmadığını belirtir.  
  
Varsayılan olarak, uygulama COM birlikte çalışma izin verme belirten bu onay kutusu temizlenir. COM birlikte çalışma izin vermek için bu onay kutusunu seçin.  
  
Bu seçenek Windows uygulaması veya konsol uygulaması projeleri için kullanılabilir değildir.  
  
**Derleme olayları**  
Erişim için bu düğmeye tıklayın **yapı olayları** iletişim kutusu. Proje oluşturma öncesi ve sonrası yapı yapılandırma yönergeleri belirtmek için bu iletişim kutusunu kullanın. Bu iletişim kutusu, yalnızca Visual Basic projeleri için geçerlidir. Daha fazla bilgi için bkz: [derleme olayları iletişim kutusu (Visual Basic)](../../ide/reference/build-events-dialog-box-visual-basic.md).  
  
**Gelişmiş derleme seçenekleri**  
Erişim için bu düğmeye tıklayın **AdvancedCompiler ayarları** iletişim kutusu. Kullanım **AdvancedCompiler ayarları** Gelişmiş yapı yapılandırma özellikleri iletişim kutusu bir projeyi belirtin. Bu iletişim kutusu, yalnızca Visual Basic projeleri için geçerlidir. Daha fazla bilgi için bkz: [Gelişmiş derleyici Ayarları iletişim kutusu (Visual Basic)](../../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md).  

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl Yapılır: Derleme Olayları Belirtme (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)  
[Visual Basic komut satırı derleyicisi](/dotnet/visual-basic/reference/command-line-compiler/index)  
[Nasıl Yapılır: Yapılandırmaları Oluşturma ve Düzenleme](../../ide/how-to-create-and-edit-configurations.md)