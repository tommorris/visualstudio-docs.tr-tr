---
title: Genel, hata ayıklama, Seçenekler iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 05/23/2017
ms.technology: vs-ide-debug
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
helpviewer_keywords:
- Options dialog box, debugging
ms.assetid: b33aee0b-43c3-4c26-8ed4-bc673f491503
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 071f6782350a3786b1a3b61b1ef3292d76867531
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42626120"
---
# <a name="general-debugging-options-dialog-box"></a>Genel, Hata Ayıklama, Seçenekler İletişim Kutusu
**Araçlar > Seçenekler > hata ayıklama > Genel** sayfasında bu makalede açıklanan seçenekler ayarlamanıza imkan sağlar.

Varsayılan ayarlarını geri yüklemeniz gerekirse, bu kullanarak yapabilirsiniz **Araçları** > **içeri ve dışarı aktarma ayarları** > **tüm ayarları Sıfırla**. Yalnızca bir alt kümesini ayarlarını sıfırlamak istiyorsanız, ayarlarınızı kaydedin **içeri ve dışarı aktarma ayarları Sihirbazı** test etmek istediğiniz değişiklik yapmadan önce sonra kaydedilmiş ayarlarınızı daha sonra içeri aktarın.
  
**Tüm kesme noktalarını silmeden önce sor** tamamlamadan önce onay gerektirir **tüm kesme noktalarını Sil** komutu.  
  
**Bir işlem kesildiğinde tüm işlemleri Kes** , hata ayıklayıcının bağlı, bir kesme oluştuğunda tüm işlemler aynı anda keser.  
  
**Özel durumlar, AppDomain veya yönetilen/yerel sınırları geçtiğinde Kes** yönetilen veya karma mod hata ayıklama ortak dil çalışma zamanı uygulama etki alanı sınırları veya yönetilen/yerel sınırları çapraz özel durumları yakalayabilir, aşağıdaki koşullar geçerli olur:  
  
1\) yerel kod, COM birlikte çalışabilirliği kullanılarak yönetilen kodu çağırır ve yönetilen kod bir özel durum oluşturduğunda. Bkz: [COM birlikte çalışma'ya giriş](/dotnet/articles/visual-basic/programming-guide/com-interop/introduction-to-com-interop).  
  
2\) ne zaman 1 uygulama etki alanında çalışan yönetilen kod 2 uygulama etki alanındaki yönetilen kodu çağırır ve 2 uygulama etki alanındaki kod bir özel durum oluşturur. Bkz: [uygulama etki alanlarıyla programlama](/dotnet/articles/framework/app-domains/index).  

3\) zaman kod, yansıma kullanarak bir işlev çağırdığında ve işlev bir özel durum oluşturur. Bkz: [yansıma](/dotnet/framework/reflection-and-codedom/reflection).  
  
2. ve 3 koşul içinde özel durum bazen yönetilen kod tarafından yakalandı `mscorlib` ortak dil çalışma zamanı yerine. Bu seçenek etkilemez tarafından yakalanan özel bozucu `mscorlib`.  
  
**Adres seviyesinde hata ayıklamayı** Gelişmiş adres düzeyinde hata ayıklama özellikleri etkinleştirir ( **ayrıştırılmış kodu** penceresinde **kaydeder** penceresi ve adres kesme noktaları).  
  
- **Kaynak kullanılamıyorsa ayrıştırılmış Kodu Göster** otomatik olarak gösterir **ayrıştırılmış kodu** için hangi kaynak kod hata ayıklamayı denediğinizde penceresi kullanılamıyor.  
  
**Kesme noktası filtrelerini etkinleştir** , böylece yalnızca belirli işlemleri, iş parçacıklarını veya bilgisayarları etkiler kesme noktalarında filtreler ayarlamanızı sağlar.  
 
**Yeni özel durum Yardımcısını Kullan** özel durum Yardımcısını değiştirir. özel durum Yardımcısı (Visual Studio 2017) sağlar.
  
> [!NOTE]
> Yönetilen kod için bu seçenek daha önceden çağrıldığından **özel durum Yardımcısını** . 
  
**Sadece benim kodumu etkinleştir** hata ayıklayıcı görüntüler ve adımları kullanıcı kodu ("kodum") yalnızca, sistem kodunu ve en iyisi olan veya olmayan hata ayıklama simgeleri diğer kod yoksayılıyor.

- **(Sadece yönetilen) hiç kullanıcı kodu yoksa uyar** yalnızca kendi kodum ile hata ayıklama başladığında, bu seçenek, kullanıcı kodu ("kodum") olup olmadığını sizi uyarır. 

**Etkinleştirme .NET Framework kaynak Adımlamayı** hata ayıklayıcının .NET Framework kaynağına ilerlemesine olanak sağlar. Bu seçeneği etkinleştirmek otomatik olarak yalnızca My Code .NET sembolleri bir önbellek konumuna karşıdan yüklenir Framework'ü devre dışı bırakır. Önbellek konumunu değiştirebilirsiniz **seçenekleri** iletişim kutusu, **hata ayıklama** kategori **sembolleri** sayfası.  
  
**Özellikler ve işleçler (sadece yönetilen) üzerinden adımla** hata ayıklayıcı, yönetilen kod içindeki özellikler ve işleçlerin içine adımlamasını engeller.  
  
**Özellik değerlendirmesini ve diğer örtük işlev çağrılarını ekinleştir** özelliklerin ve örtülü işlev otomatik olarak değerlendirilmesini etkinleştirir değişkenler pencerelerinde çağırır ve **QuickWatch** iletişim kutusu.  
  
- **(C# ve JavaScript yalnızca) değişken pencerelerindeki nesnelerde dize dönüştürme işlevini çağırma** değişken pencerelerinde nesneleri değerlendirirken bir örtük dize dönüştürmesi çağrısı yürütür. Sonuç tür adı yerine bir dize olarak görüntülenir. Yalnızca C# kodunda hata ayıklama sırasında uygulanır. Bu ayar DebuggerDisplay özniteliği tarafından geçersiz kılınmış olabilir (bakın [DebuggerDisplay özniteliğini kullanma](../debugger/using-the-debuggerdisplay-attribute.md)).  
  
**Kaynak sunucusu desteğini etkinleştir** Visual Studio hata ayıklayıcıya SrcSrv uygulayan kaynak sunuculardan kaynak dosyaları almak için (`srcsrv.dll`) protokolü. Team Foundation Server ve Windows için hata ayıklama araçları protokol uygulayan iki kaynak sunucular olan. SrcSrv kurulumu hakkında daha fazla bilgi için bkz. [SrcSrv](https://msdn.microsoft.com/library/windows/hardware/ff558791(v=vs.85).aspx) belgeleri. Ayrıca bkz [belirtin sembol (.pdb) ve kaynak dosyaları](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
> [!IMPORTANT]
> Çünkü okuma *.pdb* dosyaları, dosyalarda rasgele kod yürütebilir, sunucunun güvenilir olduğundan emin olun.  
  
- **Kaynak sunucusu tanılama iletilerini çıkış penceresine Yazdır** kaynak sunucu desteği etkinleştirildiğinde, bu ayar tanılama görüntüsünü etkinleştirir.  
  
- **Kısmi güven derlemeleri (sadece yönetilen) için kaynak sunucuya izin** kaynak sunucu desteği etkinleştirildiğinde, bu ayar kısmi güven derlemeleri için kaynakları almayarak varsayılan davranışını geçersiz kılar.  

**Kaynak bağlantısı desteğini etkinleştir** kaynak bağlantı bilgilerini içeren .pdb dosyaları için kaynak dosyalarını indirmek üzere Visual Studio hata ayıklayıcıya bildirir. Kaynak bağlantısı hakkında daha fazla bilgi için bkz: [kaynak bağlantı belirtimi](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/source_link.md).

    > [!IMPORTANT]
    >  Because Source Link will download files using http or https, make sure you trust the .pdb file.  
  
**Kesme noktaları ve geçerli deyim (yalnızca C++) için satırın tamamını vurgulayın** hata ayıklayıcı bir kesme noktası veya geçerli ifadeyi Vurguladığında tüm satırı vurgular.  
  
**Özgün sürümle kaynak dosyaların uyuşmasını gerektir** bir kaynak dosyası hata ayıklamasını yaptığınız çalıştırılabilir dosyayı oluşturmak için kullanılan kaynak kodu sürümüyle eşleşen doğrulamak için hata ayıklayıcıya bildirir. Sürüm eşleşmiyorsa, eşleşen bir kaynak bulmanız istenir. Eşleşen bir kaynak bulunamıyorsa, kaynak kodu hata ayıklama sırasında görüntülenmez. 
  
**Tüm çıkış penceresi metnini yürütme penceresine yeniden yönlendir** normalde içinde görünecek ileti tüm hata ayıklayıcı gönderir **çıkış** penceresine **hemen** penceresi yerine.  
  
**Nesnelerin ham yapısını değişkenler pencerelerinde Göster** tüm nesne yapısı görünümü özelleştirmelerini devre dışı bırakır. Görünüm özelleştirmeleri hakkında daha fazla bilgi için bkz. [.managed nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md).  
  
**Modül yükleme (sadece yönetilen) JIT iyileştirmesini bastır** hata ayıklayıcı JIT derlenmiş ve bir modül yüklendiğinde yönetilen kodun JIT iyileştirmesini devre dışı bırakır. İyileştirme devre dışı bırakma bazı sorunların hatalarını ayıklamak performans rağmen çoğaltamaz kolaylaştırabilir. Yalnızca kendi Kodum'u kullanıyorsanız, JIT gizleme kullanıcı kodu ("kodum") görüntülenecek kullanıcı olmayan kod iyileştirme neden olabilir. Daha fazla bilgi için [JIT iyileştirmesi ve hata ayıklama](../debugger/jit-optimization-and-debugging.md).

**JavaScript (Chrome ve IE) ASP.NET için hata ayıklamayı** ASP.NET uygulamaları için betik hata ayıklayıcısı sağlar. Chrome'da ilk kez kullanıldığında, yüklemiş olduğunuz Chrome uzantıları etkinleştirmek için ilk kullanımda tarayıcıda oturum açmanız gerekebilir. Eski davranışa dönmek için bu seçeneği devre dışı bırakın.    

**Dll dışarı aktarmaları Yükle** dll dışa aktarma tablolarını yükler. Dll dışa aktarma tablolarının sembol bilgilerini Windows iletileri, Windows yordamları (WindowProcs), COM nesneleri veya sıralama veya sembolleri olmayan herhangi bir dll ile çalışıyorsanız yararlı olabilir. Dışa aktarma bilgilerini okuma dll bazı ek okumalar içerir. Bu nedenle, bu özellik varsayılan olarak kapalıdır.  
  
Bir DLL'nin dışa aktarma tablosunda hangi sembollerin kullanılabilir görmek için `dumpbin /exports`. Semboller tüm 32-bit sistem dll için kullanılabilir. Okuyarak `dumpbin /exports` çıkışı, alfasayısal olmayan karakterler de dahil tam işlev adını görebilirsiniz. Bu, bir işlev bir kesme noktası ayarlamak için yararlıdır. Dll dışarı aktarma tablolarındaki işlev adları hata ayıklayıcıda başka bir yerde kesilmiş görünebilir. Aramalar geçerli işlev en üstte (en yoğun şekilde iç içe geçmiş) olacak şekilde arama sırasıyla listelenir. Daha fazla bilgi için [dumpbin/EXPORTS](/cpp/build/reference/dash-exports).  
  
**Show Paralel Yığınlar diyagramını aşağıdan yukarıya** , görüntülenme yönünü denetler **Paralel Yığınlar** penceresi.
  
**Yazılan veriler değeri değiştirmiyorsa GPU bellek erişimi özel durumlarını Yoksay** veri değişmediyse hata ayıklama sırasında algılanan yarış durumlarını yoksayar. Daha fazla bilgi için [GPU kodunda hata ayıklama](../debugger/debugging-gpu-code.md).  
  
**Yönetilen Uyumluluk modunu kullan** varsayılan hata ayıklama altyapısı bu senaryoları sağlamak için eski bir sürüm ile değiştirir:  
  
- C#, VB veya F kendi ifade değerlendiricisi sağlayan # dışındaki bir .NET Framework dili kullanıyorsunuz (buna C + dahildir +/ CLI).  
  
- Karışık modda hata ayıklarken C++ projeleri için Düzenle ve Devam Et'i etkinleştirmek istediğiniz.  
  
> [!NOTE]
> Yönetilen uyumluluk modu yalnızca hata ayıklama altyapısı varsayılan uygulanan bazı özellikler devre dışı bırakır. 

**Eski C# ve VB ifade değerlendiricilerini kullan** hata ayıklayıcı, Visual Studio 2013'ün C# /VB ifade değerlendiricilerini yerine Visual Studio 2015 Roslyn tabanlı ifade değerlendiricilerini kullanacak.    
  
**(Sadece yönetilen) güvenli olmayan işlemlere karşı özel hata ayıklama görselleştiricileri kullanıldığında uyar** Visual Studio sizi uyarır, güvenli olmayan çalışıyor olabilir çünkü kod hata ayıklanan işlemde çalışan bir özel hata ayıklama görselleştiricisi kullanırken kodu.  
  
**Windows hata ayıklama yığın ayırıcısını (yalnızca yerel) etkinleştirme** yığın tanılamayı geliştirme amacıyla windows hata ayıklama yığınındaki sağlar. Bu seçenek etkinleştirildiğinde, hata ayıklama performansını etkiler.  
  
**XAML için UI hata ayıklama araçlarını etkinleştir** desteklenen proje türü (F5) hata ayıklaması başlattığınızda, Live Visual Tree ve Live özellik keşfedin windows görünür. Daha fazla bilgi için [hata ayıklama sırasında XAML İnceleme özellikleri](../debugger/inspect-xaml-properties-while-debugging.md).  
  
- **Seçilen öğeleri Canlı görsel ağaç Önizleme** XAML öğesi bağlamı seçiliyse seçili ayrıca **Live Visual Tree** penceresi.  
  
- **Çalışma zamanı araçlarını uygulamada Göster** gösterir **Live Visual Tree** ayıklanmakta olan XAML uygulamanın ana pencere bir araç komutları. Bu seçenek, Visual Studio 2015 güncelleştirme 2'de sunulmuştur. 

- **XAML Düzenle ve Devam Et'i etkinleştir** düzenleme kullanın ve XAML kodu için özellik devam olanak tanır. 
  
**Hata ayıklama sırasında tanılama araçları etkinleştirme** **tanılama araçları** ayıklarken penceresi görüntülenir.
  
**Hata ayıklama sırasında PerfTip geçen süresini göster** hata ayıklaması yapıyorsanız Kod penceresi belirtilen yöntem çağrısının geçen süreyi görüntüler.  
  
**Düzenle ve Devam Et'i etkinleştir** düzenleme ve hata ayıklama sırasında işlevselliği devam kullanabilirsiniz.  
  
- **Yerel Düzenle ve Devam Et'i etkinleştir** düzenleme ve yerel C++ kodunu ayıklarken İşlevselliği devam kullanabilirsiniz. Daha fazla bilgi için [Düzenle ve devam et (Visual C++)](../debugger/edit-and-continue-visual-cpp.md).  
  
- **Değişiklikleri Uygula (yalnızca yerel) üzerinde devam** Visual Studio otomatik olarak derler ve bir kesme durumundan işlemine devam etmek, yapmış olduğunuz bekleyen kod değişiklikleri uygular. Seçilmezse, hata ayıklama menüsünün altında "Kod değişikliklerini uygulama" öğesini kullanarak değişiklikleri uygulamak seçebilirsiniz.  
  
- **(Yalnızca yerel) eski kod hakkında uyar** eski kod hakkında uyarı alın.    

**Hata ayıklama sırasında düğmesini düzenleyicide çalışma Göster** bu seçenek belirlendiğinde, [tıklanan satıra kadar Çalıştır](debugger-feature-tour.md#run-to-a-point-in-your-code-quickly-using-the-mouse) hata ayıklama sırasında düğmesi gösterilir.

## <a name="options-supported-in-older-versions-of-visual-studio"></a>Visual Studio'nun eski sürümlerinde desteklenen seçenekleri

Visual Studio'nun daha eski bir sürümü kullanıyorsanız, bazı ek seçenekler mevcut olabilir.

**Özel durum Yardımcısını** yönetilen kod için özel durum Yardımcısını etkin. Visual Studio 2017'de, özel durum Yardımcısını özel durum Yardımcısı değiştirildi.

**Çağrı yığınını işlenmeyen özel durumlar üzerinde bırakma** neden **çağrı yığını** çağrı yığınını işlenmeyen özel durum oluşmadan önceki noktaya geri almak için penceresi. 

**(Yalnızca yerel) sembol yoksa uyar** hata ayıklayıcı sembol bilgisi içermediği bir programdaki hataları ayıklamayı denediğinizde bir uyarı iletişim kutusu görüntüler. 

**Hata ayıklamayı başlatma sırasında devre dışı bırakılıp bırakılmadığını uyar** hata ayıklayıcı komut dosyası ile hata ayıklaması devre dışı olarak başlatıldığında bir uyarı iletişim kutusu görüntüler.

**Yerel Uyumluluk modunu kullan** hata ayıklayıcı bu seçenek belirlendiğinde, yeni yerel hata ayıklayıcı yerine Visual Studio 2010 yerel hata ayıklayıcı kullanır.  
  
.NET C++ kodunu ayıklarken yeni hata ayıklama motoru değerlendirilirken .NET C++ deyimleri desteklemediğinden, bu seçeneği kullanmanız gerekir. Ancak, çalışması için geçerli hata ayıklayıcı mantığınız bağımlı birçok özelliği yerel uyumluluk modu etkinleştirme devre dışı bırakır. Örneğin, yerleşik türler ister için eski motoru birçok görselleştiriciler eksik `std::string` Visual Studio 2015 projelerinde.   Visual Studio 2013 proje, bu gibi durumlarda en iyi hata ayıklama deneyimi için kullanır.
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visual Studio’da hata ayıklama](../debugger/index.md)  
 [Hata ayıklayıcısı özellik turu](../debugger/debugger-feature-tour.md)
