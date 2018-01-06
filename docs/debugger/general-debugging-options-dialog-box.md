---
title: "Genel, hata ayıklama, Seçenekler iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 05/23/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.options.General
- VS.ToolsOptionsPages.Debugger.General
- VS.ToolsOptionsPages.Debugger.ENC
- vs.debug.options.ENC
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords: Options dialog box, debugging
ms.assetid: b33aee0b-43c3-4c26-8ed4-bc673f491503
caps.latest.revision: "46"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bf693d7a5339e57edeaed82c25ed552901e1ea51
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="general-debugging-options-dialog-box"></a>Genel, Hata Ayıklama, Seçenekler İletişim Kutusu
**Araçlar > Seçenekler > hata ayıklama > Genel** sayfasında aşağıdaki seçenekleri ayarlamanıza olanak tanır:  
  
**Tüm kesme noktaları silmeden önce sor**  
Tamamlamadan önce onay gerektirir **silmek tüm kesme noktaları** komutu.  
  
**Tüm işlemler bir işlem böldüğünde bölün**  
Aynı anda bir sonu oluştuğunda, hata ayıklayıcı, bağlı olduğu tüm işlemler keser.  
  
**Özel durumlar AppDomain veya yönetilen/yerel sınırları geçtiğinde ayır**  
Yönetilen ya da karma modda hata ayıklama ortak dil çalışma zamanı aşağıdaki koşullar geçerli olduğunda, uygulama etki alanı sınırları veya yönetilen/yerel sınırları arası özel durumları yakalamak:  
  
1\) zaman yerel kod COM birlikte çalışma kullanarak yönetilen kod çağırır ve yönetilen kod bir özel durum oluşturur. Bkz: [COM birlikte çalışma giriş](/dotnet/articles/visual-basic/programming-guide/com-interop/introduction-to-com-interop).  
  
2\) zaman 1 uygulama etki alanında çalışan yönetilen kodu 2 uygulama etki alanında yönetilen kod çağırır ve uygulama etki alanı 2 kodda bir özel durum oluşturur. Bkz: [programlama uygulama etki alanları ile](/dotnet/articles/framework/app-domains/index).  

3\) zaman kod yansıma kullanarak bir işlevi çağırır ve işlev bir özel durum oluşturur. Bkz: [yansıma](/dotnet/framework/reflection-and-codedom/reflection).  
  
Koşul 2 ve 3, özel durum bazen yönetilen kodda tarafından yakalanan `mscorlib` ortak dil çalışma zamanı yerine. Bu seçenek etkilemez tarafından yakalanan özel durumları kesme `mscorlib`.  
  
**Adres düzeyi hata ayıklamayı etkinleştir**  
 Gelişmiş Özellikler adresi düzeyinde hata ayıklama için etkinleştirir ( **ayrıştırılmış** penceresinde **kaydeder** penceresi ve adres kesme noktaları).  
  
- **Kaynak kullanılabilir değilse, ayrıştırılmış Göster**  
    Otomatik olarak gösterir **ayrıştırılmış** hangi kaynak kodda hata ayıklama çalıştığınızda penceresi kullanılamıyor.  
  
**Kesme noktası filtrelerini etkinleştirin**  
Yalnızca belirli işlemleri, iş parçacığı veya bilgisayarları etkileyeceğini kesme noktaları üzerinde filtreleri ayarlamanıza olanak sağlar.  
 
**Yeni özel durum Yardımcısı kullanın**  
Özel durum Yardımcısı değiştirir özel durum Yardımcısı (Visual Studio 2017) sağlar.
  
> [!NOTE]
> Yönetilen kod için bu seçeneği önceden çağrıldı **özel durum Yardımcısı'nı etkinleştir** . 
  
**Yalnızca kendi kodum etkinleştir**  
Hata ayıklayıcı görüntüler ve yalnızca, kullanıcı kodu ("My kodu") içine adımları sistem kodu ve diğer kodları, iyileştirilmiş veya, hata ayıklama simgeleri yok yoksayılıyor.

- **Hiçbir kullanıcı kodu yoksa, başlatılırken (sadece yönetilen) uyar**  
    İle başlayan, hata ayıklama sırasında sadece kendi kodumu etkin, bu seçenek, hiçbir kullanıcı kodu ("My kodu") olduğunda sizi uyarır. 

**.NET Framework etkinleştirmek kaynak Adımlama**  
.NET Framework kaynağına adım hata ayıklayıcı sağlar. Bu seçenek otomatik olarak etkinleştirme yalnızca My kod .NET simgeleri bir önbellek konumuna indirilir Framework devre dışı bırakır. Önbellek konumunu değiştirebilirsiniz **seçenekleri** iletişim kutusu, **hata ayıklama** kategorisi, **simgeleri** sayfası.  
  
**Özellikler ve işleçler (sadece yönetilen) adım**  
Hata ayıklayıcı özellikleri ve yönetilen kod işleçleri içine Adımlama engeller.  
  
**Özellik değerlendirmesi ve diğer dolaylı işlev çağrılarını etkinleştir**  
Özellikleri ve dolaylı işlevi otomatik değerlendirme açar değişkenleri windows çağırır ve **QuickWatch** iletişim kutusu.  
  
- **Değişkenleri windows (C# ve JavaScript yalnızca) nesnelerde dize dönüştürme işlevini çağırın**  
    Örtük dize dönüştürme çağrısı değişkenleri windows nesneleri değerlendirirken yürütür. Bu nedenle, bu sonuç türü adı yerine bir dize olarak görüntülenir. Yalnızca C# kodunda hata ayıklama sırasında uygulanır. Bu ayar DebuggerDisplay özniteliği tarafından geçersiz kılınmış olabilir (bakın [DebuggerDisplay özniteliğini kullanma](../debugger/using-the-debuggerdisplay-attribute.md)).  
  
**Kaynak sunucu desteğini etkinleştir**  
Kaynak dosyaları SrcSrv uygulayan kaynak sunuculardan almak için Visual Studio hata ayıklayıcısı söyler (`srcsrv.dll`) protokolü. Team Foundation Server ve Windows için hata ayıklama araçları protokolünü uygulayan iki kaynak sunucular olan. SrcSrv kurulumu hakkında daha fazla bilgi için bkz: [SrcSrv](hhttps://msdn.microsoft.com/en-us/library/windows/hardware/ff558791(v=vs.85).aspx) belgeleri. Ayrıca bkz [belirtin simge (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
> [!IMPORTANT]
>  .Pdb dosyaları okuma rastgele kod dosyaları yürütebilir çünkü sunucu güvendiğinizden emin olun.  
  
- **Kaynak sunucu tanılama iletileri çıkış penceresine yazdırma**  
    Kaynak sunucu desteği etkinleştirildiğinde, bu ayarı tanılama ekranda kapatır.  
  
- **Kaynak sunucu için kısmi güven derlemeleri (sadece yönetilen) izin ver**  
    Kaynak sunucu desteği etkinleştirildiğinde, bu ayar kaynakları için kısmi güven derlemeleri almadığınızdan varsayılan davranışı geçersiz kılar.  

- **Kaynak bağlantı desteğini etkinleştir**  
    Kaynak dosyalarını kaynağı bağlantı bilgilerini içeren .pdb dosyaları indirmek için Visual Studio hata ayıklayıcısı söyler. Kaynak bağlantısı hakkında daha fazla bilgi için bkz: [kaynak bağlantı belirtimi](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/source_link.md).

    > [!IMPORTANT]
    >  Kaynak bağlantısı http veya https kullanarak dosyaları indirir çünkü .pdb dosyasını güvendiğinizden emin olun.  
  
**Kesme noktaları ve geçerli deyimi (C++ yalnızca) için tüm satırı vurgulayın**  
Hata ayıklayıcı bir kesme noktası ya da geçerli deyimi vurgular, tüm satırı vurgular.  
  
**Kaynak dosyalarını özgün sürümü tam olarak eşleşmesi iste**  
Bir kaynak dosyasını ayıkladığınız yürütülebilir oluşturmak için kullanılan kaynak kodu sürümüyle eşleşen doğrulamak için hata ayıklayıcı söyler. Sürüm eşleşiyorsa, eşleşen bir kaynak bulmak için istenir. Eşleşen bir kaynak bulunmazsa, kaynak kodu hata ayıklama sırasında görüntülenmez. 
  
**Tüm çıktı penceresi metni yeniden yönlendirme komut penceresi**  
Hata ayıklayıcı tüm normalde içinde görüneceği iletileri gönderir **çıkış** penceresine **hemen** penceresi yerine.  
  
**Nesnelerin ham yapısı değişkenleri windows Göster**  
Tüm nesne yapısı görünüm özelleştirmelerini devre dışı bırakır. Görünüm özelleştirmelerini hakkında daha fazla bilgi için bkz: [.managed nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md).  
  
**JIT iyileştirmesi modülü Yükü (sadece yönetilen) gösterme**  
Yönetilen kod JIT iyileştirmesi bir modül yüklenir ve hata ayıklayıcısı ekli sırada JIT derlenmiş devre dışı bırakır. En iyi duruma getirme devre dışı bırakma bazı sorunlar hata ayıklamak performans rağmen ödün verme pahasına kolaylaştırabilir. Sadece kendi kodumu kullanıyorsanız, JIT gizleme kullanıcı kodu ("My kodu") görünmesi kullanıcı olmayan kod iyileştirme neden olabilir.

**JavaScript, ASP.NET (Chrome ve IE) hata ayıklamayı etkinleştir** ASP.NET uygulamaları için komut dosyası hata ayıklayıcı sağlar. Chrome ilk kullanımda üzerinde yüklediğiniz Chrome uzantıları etkinleştirmek için ilk kullanımda tarayıcı oturumu açmak gerekebilir. Eski davranışa geri dönmek için bu seçeneği devre dışı bırakın.    

**DLL dışarı aktarmaları yükleme**  
DLL dışarı aktarma tabloları yükler. Dll dışarı aktarma tablolardan sembol bilgileri Windows iletileri, Windows yordamları (WindowProcs), COM nesneleri veya sıralama veya sembolleri olmayan herhangi bir dll ile çalışıyorsanız yararlı olabilir. DLL okuma bazı ek bilgi içerir. Bu nedenle, bu özellik varsayılan olarak kapalıdır.  
  
DLL'den dışarı aktarma tablosunda hangi simgeler kullanılabildiğinde görmek için `dumpbin /exports`. Simgeler herhangi bir 32-bit sistem dll için kullanılabilir. Okuyarak `dumpbin /exports` çıkışı, alfasayısal olmayan karakter dahil tam işlevi adını görebilirsiniz. Bu, bir işlev bir kesme noktası ayarlamak için yararlıdır. Dll dışarı aktarma tablolardan işlev adları başka bir yerde hata ayıklayıcıda kesilmiş görünebilir. Aramalar geçerli işlev en üstte (en yoğun şekilde iç içe geçmiş) olacak şekilde arama sırasıyla listelenir. Daha fazla bilgi için bkz: [DUMPBIN/dışarı aktarmalar](/cpp/build/reference/dash-exports).  
  
**Paralel Yığınlar diyagramı aşağıdan yukarıya Göster**  
İçinde yığınları görüntülenir yönünü denetler **Paralel Yığınlar** penceresi.  
  
**Yazılan veri değeri değiştirilmediyse GPU bellek erişimi özel durumları yoksay**  
Veri değiştirilmediyse hata ayıklama sırasında algılanan yarış durumları yoksayar. Daha fazla bilgi için bkz: [GPU kodunda hata ayıklama](../debugger/debugging-gpu-code.md).  
  
**Yönetilen uyumluluk modu kullan**  
Altyapısı bu senaryoları etkinleştirmek için eski bir sürümü ile hata ayıklama varsayılan değiştirir:  
  
- C#, VB ve F kendi ifade değerlendiricisi sağlayan # dışında bir .NET Framework dil kullanıyorsanız (Bu C + içerir +/ CLI).  
  
- Düzenle ve devam et C++ projeleri için karışık modda hata ayıklama sırasında etkinleştirmek istiyor.  
  
Yönetilen uyumluluk seçme modunu altyapısı hata ayıklama varsayılan olarak uygulanan bazı özellikler devre dışı bırakır olduğunu unutmayın. 

**Eski C# ve VB ifade değerlendiricisi kullanın**  
Hata ayıklayıcı Visual Studio 2013 C# /VB ifade değerlendiricisi yerine Visual Studio 2015 Roslyn tabanlı bir ifade değerlendiricisi kullanır.    
  
**Özel hata ayıklayıcı görselleştiriciler olmayabilecek işlemleri (sadece yönetilen) karşı kullanırken uyar**  
Güvenli olmayan kod çalıştıran çünkü kod ayıklayıcı işlemde çalıştırılıyor özel hata ayıklayıcı Görselleştirici kullanırken visual Studio, sizi uyarır.  
  
**Windows hata ayıklama yığını ayırıcısı (yalnızca yerel) etkinleştir**  
Yığın tanılama artırmak windows hata ayıklama yığınını sağlar. Bu seçeneğin etkinleştirilmesi, hata ayıklama performansını etkiler.  
  
**XAML için hata ayıklama araçları UI etkinleştir**  
Desteklenen proje türü (F5) hata ayıklama başlattığınızda Canlı görsel ağaç ve dinamik özellik keşfedin windows görünür. Daha fazla bilgi için bkz: [hata ayıklama sırasında XAML incelemek özellikleri](../debugger/inspect-xaml-properties-while-debugging.md).  
  
- **Canlı görsel ağaç seçilen öğeleri Önizleme**  
    Bağlamı seçili XAML öğesi Ayrıca seçili **Canlı görsel ağaç** penceresi.  
  
- **Uygulama çalışma zamanı araçlarını Göster**  
    Gösterir **Canlı görsel ağaç** ayıklanacak XAML uygulaması ana penceresinde bir araç komutları. Bu seçenek, Visual Studio 2015 güncelleştirme 2'de sunulmuştur. 

- **XAML Düzenle ve devam et etkinleştirmek** düzenleme kullanın ve XAML kodu için özellik devam sağlar. 
  
**Tanılama araçlarını hata ayıklama sırasında etkinleştir**  
**Tanılama araçları** hata ayıklarken penceresi görüntülenir.
  
**Hata ayıklama sırasında geçen süre PerfTip Göster**  
Kod penceresi ayıkladığınız verilen yöntem çağrısı geçen süre görüntüler.  
  
**Etkinleştirme Düzenle ve devam et**  
Düzenleme ve hata ayıklama sırasında işlevselliği devam kullanabilirsiniz.  
  
- **Yerel etkinleştirmek Düzenle ve devam et**  
    Düzen ve yerel C++ kod hata ayıklama sırasında işlevselliği devam edebilirsiniz. Daha fazla bilgi için bkz: [Düzenle ve devam et (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).  
  
- **Değişiklikleri uygulamak (yalnızca yerel) üzerinde devam**  
    Visual Studio otomatik olarak derler ve sonu durumundan işlemine devam zaman yapmış olduğunuz tüm bekleyen kod değişiklikleri uygular. Seçilmezse, hata ayıklama menüsünün altında "Kod değişiklikleri Uygula" öğesini kullanarak değişiklikleri uygulamak seçebilirsiniz.  
  
- **Eski kod (yalnızca yerel) hakkında uyar**  
    Eski kod hakkında uyarı alın.    

**Hata ayıklama sırasında düğmesini Düzenleyicisi'nde çalışma Göster** bu seçenek belirlendiğinde, [tıklatın çalıştırmak](debugger-feature-tour.md#run-to-a-point-in-your-code-quickly-using-the-mouse) düğmesi hata ayıklama sırasında gösterilecek.

## <a name="options-supported-in-older-versions-of-visual-studio"></a>Visual Studio'nun eski sürümlerinde desteklenen seçenekleri

Visual Studio'nun daha eski bir sürümü kullanıyorsanız, bazı ek seçenekleri mevcut olabilir.

**Özel durum Yardımcısı'nı etkinleştir**  
Yönetilen kod için özel durum Yardımcısı etkin. Visual Studio 2017 ', özel durum Yardımcısı özel durum Yardımcısı değiştirildi.

**İşlenmeyen özel durum çağrı yığınındaki geriye doğru izleme**  
Neden **çağrı yığını** işlenmeyen özel durum oluştu önce çağrı yığını noktasına geri almak için penceresi. 

**Simge, başlatılırken (yalnızca yerel) uyar**  
Hata ayıklayıcı sembol bilgileri olan bir program hata ayıklamak çalıştığınızda bir uyarı iletişim kutusu görüntüler. 

**Komut dosyasında hata ayıklama başlatılırken devre dışı olup olmadığını uyar**  
Hata ayıklayıcı komut dosyası hata ayıklamaya devre dışı başlatıldığında bir uyarı iletişim kutusu görüntüler.

**Yerel uyumluluk modu kullan**  
Bu seçenek belirlendiğinde, hata ayıklayıcı yeni yerel hata ayıklayıcı yerine Visual Studio 2010 yerel hata ayıklayıcı kullanır.  
  
.NET C++ kodu, hata ayıklama sırasında yeni bir hata ayıklama motoru değerlendirilirken .NET C++ ifadeleri desteklemediği için bu seçeneği kullanmanız gerekir. Ancak, çalışması için geçerli hata ayıklayıcı mantığınız bağımlı birçok özelliği yerel uyumluluk modu etkinleştirme devre dışı bırakır. Örneğin, yerleşik türler ister için eski altyapı birçok görselleştiriciler eksik `std::string` Visual Studio 2015 projelerinde.   Bu gibi durumlarda hata ayıklama en iyi deneyim için lütfen Visual Studio 2013 projeleri kullanın.
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcı özelliği turu](../debugger/debugger-feature-tour.md)