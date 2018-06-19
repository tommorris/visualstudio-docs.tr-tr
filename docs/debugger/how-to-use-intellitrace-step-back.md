---
title: IntelliTrace adım geri kullanarak bir anlık görüntü görüntüleme
ms.description: Learn how to take snapshots, and view snapshots with IntelliTrace step-back
ms.custom: mvc
ms.date: 05/01/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
ms.assetid: 7c60d929-d993-49dc-9db3-43b30be9912b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 68fec4e10d172f79908e57828c542a444d081b50
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33881230"
---
# <a name="view-snapshots-using-intellitrace-step-back-in-visual-studio"></a>Visual Studio IntelliTrace adım geri kullanarak görünüm anlık görüntüler

IntelliTrace adım sonradan bir anlık görüntüsünü her kesme ve hata ayıklayıcı uygulamanızın adım olay otomatik olarak alır. Kaydedilmiş anlık görüntüler, önceki kesme noktaları veya adımları geri dönün ve geçmişte haliyle uygulamanın durumunu görüntülemek etkinleştirin. IntelliTrace adım arka önceki uygulama durumu görmek istediğiniz ancak hata ayıklamayı yeniden başlatın veya istenen uygulama durumu yeniden istemediğiniz durumlarda size zaman kazandırabilir.

Visual Studio Enterprise 2017 sürüm 15,5 ve daha yüksek başlangıç IntelliTrace adım geri kullanılabilir ve Windows 10 Anniversary güncelleştirmesi gerektirir veya üstü. Bu özellik şu anda hata ayıklama, ASP.NET, WinForms, WPF, yönetilen konsol uygulamaları ve yönetilen sınıf kitaplıkları için desteklenir. Visual Studio 2017 Enterprise sürümü 15.7 ile preview 1 başlayarak, ASP.NET Core ve .NET Core için de özelliği desteklenir. UWP uygulamalarında hata ayıklama şu anda desteklenmiyor.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * IntelliTrace olayları ve anlık görüntüleri etkinleştir
> * Adım geri ve İleri Adım komutları kullanarak olayları gidin
> * Görünüm olay anlık görüntüler
  
## <a name="enable-intellitrace-events-and-snapshots-mode"></a>IntelliTrace olayları ve anlık görüntü modunu etkinleştir 

1. Projenizi Visual Studio kuruluş içinde açın.

1. Açık **Araçları** > **seçenekleri** > **IntelliTrace** Ayarları ' nı seçip seçeneği **IntelliTrace olayları ve anlık görüntüleri** . 

    ![IntelliTrace olayları ve anlık görüntüleri modunu etkinleştirme](../debugger/media/intellitrace-enable-snapshots.png "IntelliTrace olayları etkinleştirmek ve anlık görüntü modu")

1. Özel durumları görüntüleme anlık görüntüleri için seçenekleri yapılandırmak istiyorsanız, seçin **IntelliTrace** > **Gelişmiş** gelen **seçenekleri** iletişim kutusu.

    Bu seçenekler, Visual Studio 2017 Enterprise sürümü 15.7 başlayarak kullanılabilir.

    ![Anlık görüntüler için davranışı özel durumları yapılandırın](../debugger/media/intellitrace-enable-snapshots-on-exceptions.png)

    Olayları ve anlık görüntüleri etkinleştirdiğinizde, özel durumları anlık görüntüleri alma de varsayılan olarak etkindir. Özel durumlar anlık görüntü kaldırarak devre dışı bırakabilirsiniz **özel durum olaylarına anlık görüntüleri toplamak**. Bu özellik etkinleştirildiğinde, anlık görüntüleri işlenmeyen özel durumlar için alınır. İşlenmiş özel durumlar için anlık görüntüler, yalnızca özel durum oluşur ve bir daha önce oluşturulan özel durum yeniden throw değilse alınır. Aşağı açılan listeden bir değer seçerek, Maksimum sayıda anlık görüntü özel durumlar ayarlayabilirsiniz. Uygulamanız (örneğin, uygulamanızı bir kesme noktası isabet) Kesme moduna girer her zaman için en fazla geçerlidir.

    > [!NOTE]
    > Anlık görüntü yalnızca özel durum olayları için IntelliTrace kaydeden alınır. Hangi olayların IntelliTrace kayıtları seçerek belirtebilirsiniz **Araçları** > **seçenekleri** > **IntelliTrace olayları**.

1. Projeniz, bir veya daha fazla kesme noktaları ayarlayın ve hata ayıklamayı Başlat (basın **F5**), ya da kodunuzu adımla hata ayıklamayı Başlat (**F10** veya **F11**).

    IntelliTrace her bir hata ayıklayıcı adım, kesme olayı ve işlenmeyen özel durum olayı uygulamanın işleminin bir anlık görüntüsünü alır. Bu olaylar kaydedilir **olayları** sekmesinde **tanılama araçları** diğer IntelliTrace olayları birlikte penceresi. Bu pencereyi açmak için **hata ayıklama** > **Windows** > **tanılama araçları Göster**.

    Kamera simgesine anlık görüntüleri kullanılabilir olayları yanında görüntülenir. 

    ![Olayları sekmesinde sahip anlık görüntüleri](../debugger/media/intellitrace-events-tab-with-snapshots.png "kesme noktaları ve adımlar anlık görüntü ile olaylar sekmesi")

    Çok hızlı bir şekilde adımı performans nedenleriyle anlık görüntüleri katılmaz. Hiçbir kamera simgesinin yanında adım görüntülenirse, daha yavaş atlama deneyin.

## <a name="navigate-and-view-snapshots"></a>Gidin ve anlık görüntüleri görüntüleme

1. Kullanarak olayları arasında gezinmek **adım geriye dönük (Alt + [)** ve **İleri (Alt +])** hata ayıklama araç çubuğu düğmeleri.

    Bu düğmeleri görünür olayları gidin **olayları** sekmesinde **tanılama araçları penceresindeki**. İleri ve geri olaya otomatik olarak atlama etkinleştirir [geçmiş hata ayıklama](../debugger/historical-debugging.md) seçili olay.

    ![Geriye doğru adım ve İleri düğmelerini](../debugger/media/intellitrace-step-back-icons-description.png "adım geri ve İleri düğmeleri")

    Geri adım ya da adım ileri, Visual Studio Geçmiş hata ayıklama modunu girer. Bu modda, hata ayıklayıcı'nın içerik seçili olay zaman kaydedildiği zaman geçer. Visual Studio karşılık gelen bir satır kod kaynak penceresinde işaretçiyi da taşır. 

    Bu görünümden değerleri inceleyebilirsiniz **çağrı yığını**, **Yereller**, **otomobiller**, ve **izleme** windows. DataTips görüntülemek ve ifade değerlendirmesi gerçekleştirmek için değişkenleri üzerine de gelebilirsiniz **hemen** penceresi. Gördüğünüz geçen süre içinde bu noktada uygulamanın işlem anlık görüntüden veridir.

    Böylece, örneğin, bir kesme noktası isabet ve bir adım gerçekleştirilecek (**F10**), **adım geriye dönük** düğmesi kesme noktasına karşılık gelen kod satırı geçmiş modunda Visual Studio koyar. 

    ![Bir anlık görüntü sahip bir olay geçmiş modunu etkinleştirme](../debugger/media/intellitrace-historical-mode-with-snapshot.png "bir anlık görüntü sahip bir olay geçmiş modunu etkinleştirme")

2. Canlı yürütme dönmek için seçin **devam (F5)** veya **Canlı hata ayıklama için iade** Bilgi Çubuğu'nda bağlantı. 

3. Bir anlık görüntüden de görüntüleyebilirsiniz **olayları** sekmesi. Bunu yapmak için bir anlık görüntü sahip bir olay seçin ve **geçmiş hata ayıklama etkinleştirme**.

    ![Bir olaya geçmiş hata ayıklama etkinleştirme](../debugger/media/intellitrace-activate-historical-debugging.png "etkinleştirmek geçmiş hata ayıklama olay")

    Farklı **sonraki deyimi Ayarla** komutu, bir anlık görüntü görüntüleme kodunuzu yeniden değil; Bu, statik bir görünüm durumu uygulamanın bir noktada geçmişte oluştu zaman sağlar.

    ![IntelliTrace adım geri genel bakış](../debugger/media/intellitrace-step-back-overview.png "genel bakış, IntelliTrace adım geri")

    Visual Studio'da değişkenleri incelemek hakkında daha fazla bilgi için bkz: [özelliği turu hata ayıklayıcı](../debugger/debugger-feature-tour.md)  

## <a name="frequently-asked-questions"></a>Sıkça Sorulan Sorular

#### <a name="how-is-intellitrace-step-back-different-from-intellitrace-events-only-mode"></a>IntelliTrace adım geri IntelliTrace olayları yalnızca modundan farklı mı?

Olaylar yalnızca modunda IntelliTrace geçmiş hata ayıklayıcı adımlar ve kesme noktaları üzerinde hata ayıklamayı etkinleştirmek izin vermez. Ancak, IntelliTrace verileri yalnızca yakalar **Yereller** ve **otomobiller** windows açık olan ve yalnızca genişletilmiş verileri yakalar, windows ve görünüm. Olaylar yalnızca modunda, genellikle tam görünümünü değişkenleri ve karmaşık nesneler yok. Ayrıca, ifade değerlendirmesi ve görüntüleme verileri **izleme** penceresi desteklenmiyor. 

Olayları ve anlık görüntüleri modunda IntelliTrace uygulamanın işlemi, karmaşık nesneler de dahil olmak üzere tüm görüntüsünü yakalar. Kod satırında bir kesme noktasında durdurulan (ve bilgileri daha önce genişletilen önemi değil varsa gibi), aynı bilgileri görebilirsiniz. İfade değerlendirme, bir anlık görüntü görüntülerken de desteklenir.  

#### <a name="what-is-the-performance-impact-of-this-feature"></a>Bu özellik performans etkisini nedir? 

Genel sürüm performans üzerindeki etkisini, uygulamaya bağlı olarak değişir. Bir anlık görüntü alma yükünü yaklaşık 30 ms ' dir. Bir anlık görüntü alınırken uygulamanın işlem çatallanmış ve forked kopyalama askıya alınır. Bir anlık görüntü görüntülediğinizde, Visual Studio işlemi forked kopyaya ekleniyor. Her anlık görüntü için Visual Studio yalnızca sayfa tablosu kopyalar ve sayfalarını kopyalama yazarken için ayarlar. Yığında nesneleri ile ilişkili anlık görüntüleri hata ayıklayıcı adımları arasında değiştirirseniz, ilgili sayfa tablosu sonra en az bellek maliyet kaynaklanan kopyalanır. Visual Studio anlık almak için yeterli bellek yok algılarsa, bir almaz.
 
## <a name="known-issues"></a>Bilinen Sorunlar  
* Windows 10 sonbaharda oluşturucuları güncelleştirme (RS3) önceki Windows sürümlerinde IntelliTrace olayları ve anlık görüntü modu kullanıyorsanız ve uygulama hata ayıklama platform hedefi için x86 ayarlarsanız, IntelliTrace anlık görüntüleri almaz.

    Geçici çözüm:
    * Yükleyin veya Windows 10 sonbaharda oluşturucuları için güncelleştirme (RS3) yükseltin. 
    * Alternatif olarak: 
        1. Visual Studio yükleyicisinden masaüstü için VC++ 2015.3 v140 araç seti (x86, x64) bileşenini yükleyin.
        2. Hedef uygulamayı derleyin.
        3. Komut satırından editbin ayarlamak için aracını `Largeaddressaware` hedef çalıştırılabilir için bayrak. Örneğin, bu komutu (yolu güncelleştirdikten sonra) kullanabileceğinize: "C:\Program Files (x86) \Microsoft Visual Studio\Preview\Enterprise\VC\Tools\MSVC\14.12.25718\bin\Hostx86\x86\editbin.exe" /Largeaddressaware "C:\Path\To\Application\app.exe".
        4. Hata ayıklama başlatmak için basın **F5**. Şimdi, anlık görüntüleri hata ayıklayıcı adımları ve kesme noktaları alınır.

        > [!Note]
        > `Largeaddressaware` Yürütülebilir değişikliklerle yeniden her zaman bayrağını ayarlayın.

* Bir anlık görüntüsünü uygulama işlemi kalıcı bir bellek eşlemeli dosyası kullanan bir uygulama alındığında, anlık görüntü işlemine bellekle eşlenen dosyanın özel bir kilit (hatta üst işlemi, kilit yayımladı sonra) tutar. Diğer işlemlerin okuyun, ancak, bellekle eşlenen dosyasına yazmayacak hala imkanınız olur.

    Geçici çözüm:
    * Hata ayıklama oturumu sonlandırarak tüm anlık görüntüleri silin. 

* Çok sayıda benzersiz bellek bölgeler, DLL'ler, çok sayıda yükleyen bir uygulama gibi işlem sahip bir uygulama hata ayıklama sırasında etkin anlık görüntüleri ile performans atlama etkilenebilir. Bu sorun gelecekteki bir Windows sürümünde ele alınacaktır. Bu sorunu yaşıyorsanız, adresinden bize ulaşmak stepback@microsoft.com. 

* Bir dosya kaydedilirken **hata ayıklama > IntelliTrace > Kaydet IntelliTrace oturumunu** olaylar ve anlık görüntü modu altında anlık görüntülerden yakalanan ek verileri .itrace dosyasında mevcut değil. Kesme ve adım olaylarına IntelliTrace olayları yalnızca modunda dosya kaydetmiş gibi aynı bilgileri görebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, IntelliTrace adım geri kullanmayı öğrendiniz. Diğer IntelliTrace özellikleri hakkında daha fazla bilgi edinmek isteyebilirsiniz.

> [!div class="nextstepaction"]
> [IntelliTrace özellikleri](../debugger/intellitrace-features.md)
