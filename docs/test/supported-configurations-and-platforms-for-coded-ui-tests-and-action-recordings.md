---
title: "Desteklenen yapılandırmalar ve platformlar kodlanmış UI testleri ve eylem kayıtları için | Microsoft Docs"
ms.custom: 
ms.date: 2015-10-04
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- coded UI tests
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d2cc29115108b1a5d308a227ed0be30d44e56d67
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings"></a>Kodlanmış UI Testleri ve Eylem Kayıtları için Desteklenen Yapılandırmalar ve Platformlar
Desteklenen yapılandırmalar ve platformlar için Visual Studio Enterprise için kodlanmış UI testleri aşağıdaki tabloda listelenmiştir. Bu yapılandırmalar kullanılarak oluşturulan eylem kayıtları için de geçerlidir. [!INCLUDE[MTRlong](../test/includes/mtrlong_md.md)].  
  
> [!NOTE]
>  Kodlanmış kullanıcı arabirimi test işlemi, test altındaki uygulama ile aynı ayrıcalıklara sahip olmalıdır.  
  
 **Gereksinimler**  
  
-   Visual Studio Enterprise  
  
## <a name="supported-configurations"></a>Desteklenen Yapılandırmalar  
  
|Yapılandırma|Desteklenir|  
|-------------------|---------------|  
|İşletim Sistemleri|[!INCLUDE[win7](../debugger/includes/win7_md.md)]<br /><br /> [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]<br /><br /> [!INCLUDE[win8](../debugger/includes/win8_md.md)]<br /><br /> Windows 10|  
|32 bit / 64 bit Desteği|32 bit çalışan 32 bit Windows [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 32-bit uygulamaları test edebilirsiniz.<br /><br /> 32-bit çalıştıran 64 bit Windows [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] UI Synchronization.n 32-bit WOW uygulamaları test edebilirsiniz.<br /><br /> 32-bit çalıştıran 64 bit Windows [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 64-bit Windows Forms ve WPF UI Eşitlemesi olmayan uygulamaları test edebilirsiniz.|  
|Mimari|x86 hem x64 **Not:** Internet Explorer altında olduğunda çalışan dışında 64-bit modunda desteklenmez [!INCLUDE[win8](../debugger/includes/win8_md.md)] veya sonraki sürümler.|  
|.NET|.NET 2.0, 3.0, 3.5, 4 ve 4.5. **Not:** [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] ve Visual Studio hem de gerektirecektir çalışması .NET 4. Ancak, listelenen .NET sürümleri kullanılarak geliştirilen uygulamalar desteklenir.|  
  
> [!NOTE]
>  *UI eşitleme* burada kayıttan doğrulanır her denetim ileti sırasına bir özelliktir. Bir denetim kendisine gönderilen olaya yanıt vermiyorsa, olay yeniden gönderilir.  
  
## <a name="platform-support"></a>Platform Desteği  
  
|Platform|Destek Düzeyi|  
|--------------|----------------------|  
|Windows Phone uygulamaları|Yalnızca WinRT XAML uygulamaları desteklenmez telefonla.|  
|UWP uygulamaları|Yalnızca XAML tabanlı UWP uygulamaları desteklenmez.|  
|Evrensel Windows Uygulamaları|Yalnızca XAML tabanlı Evrensel Windows uygulamaları telefonu ve Masaüstü üzerinde desteklenir.|  
|Kenar|Eylem adımından kaydı veya nesne özelliklerini görüntülemek için oluşturucu kullanılarak desteklenmiyor. Testleri yürütülen geri Visual Studio 2015 güncelleştirme 2 ve sonraki sürümleri kullanarak Edge tarayıcısında [kodlanmış UI arası tarayıcı testi uzantısı](https://visualstudiogallery.msdn.microsoft.com/11cfc881-f8c9-4f96-b303-a2780156628d)|  
|Internet Explorer 8<br /><br /> Internet Explorer 9<br /><br /> Internet Explorer 10 **önemli:** Internet Explorer 10 masaüstünde yalnızca desteklenir. <br /><br /> Internet Explorer 11 **önemli:** Internet Explorer 11 masaüstünde yalnızca desteklenir.|Tam olarak desteklendi.<br /><br /> -   **Internet Explorer 9 ve Internet Explorer 10 HTML5 destek:** kodlanmış UI testleri desteği kaydı, yürütme ve doğrulama HTML5 denetimleri: ses, Video, ProgressBar ve kaydırıcı. Daha fazla bilgi için bkz: [kodlanmış UI testlerinde HTML5 denetimleri kullanma](../test/using-html5-controls-in-coded-ui-tests.md). **Uyarı:** bir kodlanmış oluşturursanız, Internet Explorer 10 UI testlerinde, çalıştırılamıyor Internet Explorer 9 veya Internet Explorer 8 kullanarak. Bunun nedeni Internet Explorer 10'un Ses, Video, İlerleme Çubuğu ve Kaydırma gibi HTML5 denetimlerini içermesidir. Bu HTML5 denetimleri, Internet Explorer 9 veya Internet Explorer 8 tarafından tanınmaz. Benzer şekilde, Internet Explorer 9 kullanarak kodlanmış UI testleri, Internet Explorer 8 tarafından tanınmayacak bazı HTML5 denetimleri de içerebilir.<br />-   **Internet Explorer 10 yazım denetimi için destek:** Internet Explorer 10 yazım denetimi tüm metin kutuları için özellikleri içerir. Bu, önerilen düzeltmeler listesinden seçim yapmanızı sağlar. Kodlanmış UI Testi, alternatif yazım önerisi seçmek gibi kullanıcı eylemlerini yoksayar. Yalnızca metin kutusuna yazılan son metin kaydedilir.<br />     Yazım denetimini kullanan kodlanmış kullanıcı arabirimi testi için şu eylemler kaydedilir: Sözlüğe Ekle, Kopyala, Tümünü Seç, Sözlüğe Ekle ve Yoksay.<br />-   **64-bit Internet Explorer'ın altında Windows 8 çalıştıran desteği:** önceden, Internet Explorer'ın 64 bit sürümleri kaydetme ve kayıttan yürütme için desteklenen değil. İle [!INCLUDE[win8](../debugger/includes/win8_md.md)] ve [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], kodlanmış UI testleri için Internet Explorer'ın 64 bit sürümleri etkinleştirildi. **Uyarı:** Internet Explorer için 64-bit desteği geçerlidir yalnızca zaman çalıştırıyorsanız [!INCLUDE[win8](../debugger/includes/win8_md.md)] veya sonraki bir sürümü.<br />-   **Internet Explorer 9'daki sabitlenmiş siteleri için destek:** Internet Explorer 9'da, sabitlenmiş sitelerin giriş yaptınız. İliştirilmiş Sitelerle, sevdiğiniz sitelere önce Internet Explorer'ı açmak zorunda kalmadan doğrudan Windows görev çubuğundan ulaşabilirsiniz. Kodlanmış UI testleri iliştirilmiş sitelerde amaç duyarlı eylemler oluşturabilir. Sabitlenmiş siteleri hakkında daha fazla bilgi için bkz: [sabitlenmiş siteleri](http://go.microsoft.com/fwlink/?LinkId=220037).<br />-   **Internet Explorer 9 anlamsal etiketleri desteği:** Internet Explorer 9 sunulan aşağıdaki anlamsal etiketler: bölüm, nav, makale, kenara, hgroup, üstbilgi, altbilgi, şekil, figcaption ve işareti. Kodlanmış UI testleri kaydedilirken bu anlamsal etiketlerin tamamını yoksayar. Kodlanmış UI Test Oluşturucusu kullanarak bu etiketlere onaylama ekleyebilirsiniz. Bu öğelerin herhangi birine gidip özelliklerini görüntülemek için kodlandırılmış UI Test Oluşturucusu'nda gezinti aramayı kullanabilirsiniz.<br />-   **Sorunsuz işleme, boşluk karakterleri Internet Explorer sürümleri arasında:** Internet Explorer 8, Internet Explorer 9 ve Internet Explorer 10 arasındaki boşluk karakterleri işleme farklılıklar vardır. Kodlanmış UI Testi bu farklılıkları sorunsuz bir şekilde işler. Dolayısıyla, örneğin, Internet Explorer 8'de oluşturulmuş bir kodlanmış UI testinin kayıttan oynatılması Internet Explorer 9 ve Internet Explorer 10'da başarıyla yapılabilir.<br />-   **Bildirim alanı, Internet Explorer olan şimdi kaydedilen ile "Hatası devam" özniteliğini ayarlayın:** Internet Explorer bildirim alanında tüm eylemler şimdi "Hatası devam" öznitelik kümesiyle kaydedilir. Kayıttan yürütme sırasında bildirim çubuğu görünmüyorsa, eylemleri yoksayılır ve kodlanmış UI testi sonraki eylem ile devam eder.|  
|Windows Forms ve WPF üçüncü taraf denetimleri|Tam olarak desteklendi.<br /><br /> Windows Formlar ve WPF uygulamalarında üçüncü taraf denetimleri etkinleştirmek için başvurular ve kod eklemeniz gerekir. Daha fazla bilgi için bkz: [etkinleştirmek kodlanmış UI testi, bilgisayarınızı denetimleri](../test/enable-coded-ui-testing-of-your-controls.md).|  
|Internet Explorer 6<br /><br /> Internet Explorer 7|Desteklenmez.|  
|Chrome<br /><br /> Firefox|Eylem adımlarını kaydetme desteklenmiyor. Kodlanmış UI Testleri Chrome ve Firefox tarayıcılarda Visual Studio 2012 Update 4 veya sonraki sürümüyle kayıttan yürütülebilir. Git [burada](http://msdn.microsoft.com/library/jj835758.aspx) daha fazla ayrıntı için.|  
|Opera<br /><br /> Safari|Desteklenmez.|  
|Silverlight|Desteklenmez.<br /><br /> Visual Studo 2013 ancak indirebilirsiniz [Microsoft Visual Studio 2013 kodlanmış UI testi eklentisi Silverlight için](https://go.microsoft.com/fwlink/?LinkId=691026) Visual Studio Galerisi'nden.|  
|Flash/Java|Desteklenmez.|  
|Windows Forms 2.0 ve ileri sürümü|Tam olarak desteklendi. **Not:** NetFx denetimleri tam olarak desteklenir, ancak tüm üçüncü taraf denetimleri desteklenmez.|  
|WPF 3.5 ve ileri sürümü|Tam olarak desteklendi.<br /><br /> **Not** NetFx denetimleri tam olarak desteklenir, ancak tüm üçüncü taraf denetimleri desteklenmez.|  
|Windows Win32|Bazı bilinen sorunlar ile çalışabilir, ancak resmi olarak desteklenmez.|  
|MFC|Kısmen desteklenir. Aşağıdaki bakın [Microsoft Web sitesini](http://go.microsoft.com/fwlink/?LinkId=206511) hangi özelliklerin desteklendiğini ayrıntılarını için.|  
|SharePoint|Tam olarak desteklendi.|  
|Office İstemci Uygulamaları|Desteklenmez.|  
|Dynamics CRM web istemcisi|Tam olarak desteklendi.|  
|Dynamics (Ax) 2012 işlemcisi|Eylem kaydı ve kayıttan yürütme kısmen desteklenir. Aşağıdaki bakın [Microsoft Web sitesini](http://go.microsoft.com/fwlink/?LinkId=232677) Ayrıntılar için.|  
|SAP|Desteklenmez.|  
|Citrix/Terminal Hizmetleri|Terminal sunucusu kaydı eylemleri öneririz yok. Kaydedici, aynı anda birden çok örneği çalıştıran desteklemiyor.|  
|PowerBuilder|Kısmen desteklenir.<br /><br /> Desteğin kapsamı, PowerBuilder denetimleri için erişilebilirliğin etkin olduğu kadardır.|  
  
 Diğer platformları destekleyecek uzantılar oluşturma hakkında daha fazla bilgi için bkz: [etkinleştirmek kodlanmış UI testi, bilgisayarınızı denetimleri](../test/enable-coded-ui-testing-of-your-controls.md) ve [genişletme kodlanmış UI testleri ve Eylem kayıtlarını Microsoft Excel'i desteklemek için](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md).  
  
## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu Test Etmek için UI Otomasyonunu Kullanma](../test/use-ui-automation-to-test-your-code.md)  
