---
title: IntelliTrace özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- IntelliTrace, debugging with events
- IntelliTrace, recording execution history
- debugging [Visual Studio ALM], recording execution history
- IntelliTrace, turn off
- IntelliTrace, navigating event and call history
- IntelliTrace, saving your session
- IntelliTrace, enabling
- IntelliTrace, start debugging
- IntelliTrace, debugging with events and call information
- IntelliTrace, disabling
- IntelliTrace, turn on
- debugging [Visual Studio ALM], IntelliTrace
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 18e3058416e6ce14dd8a481eb5dd8f8200217895
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31478219"
---
# <a name="intellitrace-features"></a>IntelliTrace Özellikleri

Yürütme farklı noktalarda (çağrı yığını ve yerel değişken değerleri) durumu incelemek izin veren uygulamanızı yöntemini çağırır ve olayların kaydedilmesinin IntelliTrace kullanabilirsiniz. Yalnızca her zamanki gibi hata ayıklamayı Başlat - IntelliTrace varsayılan olarak kapatılır ve IntelliTrace kaydı yeni bilgileri görebilirsiniz **tanılama araçları** penceresinde altında **olayları** sekmesi. Bir olay seçin ve tıklatın **geçmiş hata ayıklama etkinleştirme** çağrı yığını ve bu olay için kaydedilen Yereller görmek için.

Adım adım açıklama için bkz: [izlenecek yol: IntelliTrace'i kullanarak](../debugger/walkthrough-using-intellitrace.md).

IntelliTrace kullanılabilir Visual Studio Enterprise Edition'da ancak Visual Studio Professional veya topluluk sürümlerinde değil.

IntelliTrace açık olduğunu onaylamak için açık **Araçlar > Seçenekler > IntelliTrace** seçenekler sayfası. **IntelliTrace'i etkinleştirme** varsayılan olarak işaretlenmelidir.

> [!NOTE]
> Tüm ayarları kapsamını **IntelliTrace** seçenekleri sayfasıdır Visual Studio tamamını, bireysel projeleri veya çözümler. Bu ayarlar bir değişiklik Visual Studio, tüm hata ayıklama oturumları ve tüm projeleri veya çözümleri tüm örneklerine uygulanır.

## <a name="ChooseEvents"></a> IntelliTrace kaydeden olayları seçme

Belirli IntelliTrace olayları kaydı açıp kapatabilir.

Hatalarını ayıkladığınız, hata ayıklamayı durdurun. Git **Araçlar > Seçenekler > IntelliTrace > IntelliTrace olayları**. IntelliTrace kaydetmek istediğiniz olayları seçin.

## <a name="Snapshots"></a> Olayları ve anlık görüntüleri toplamak

Bu varsayılan olarak etkin değildir ancak IntelliTrace anlık görüntülerini uygulamanızı her kesme ve hata ayıklayıcısı adım olay yakalayabilir ve bu anlık görüntüler Geçmiş hata ayıklama oturumunda görüntüleyebilirsiniz. Bir anlık görüntü, tam uygulama durumu görünümünü verir. Anlık görüntü yakalama etkinleştirmek için şu adrese gidin **Araçlar > Seçenekler > IntelliTrace > Genel**seçip **IntelliTrace olayları ve anlık görüntüleri**. Daha fazla bilgi için bkz: [IntelliTrace adım geri kullanarak anlık görüntüleri görüntüleme](../debugger/how-to-use-intellitrace-step-back.md)

Anlık görüntüler Visual Studio Enterprise 2017 15,5 ve daha yüksek bir sürümü kullanılabilir olduğunda ve Windows 10 Anniversary güncelleştirmesi gerektirir veya üstü.  .NET Core ve ASP.NET Core uygulamaları için Visual Studio Enterprise 2017 sürüm 15.7 preview 1 gereklidir.

## <a name="GoingFurther"></a> IntelliTrace olayları toplamak ve çağrı bilgileri

Bu varsayılan olarak etkin değildir, ancak IntelliTrace olayları birlikte yöntem çağrılarını kaydedebilirsiniz. Yöntem çağrıları Git toplanmasını etkinleştirmek için **Araçlar > Seçenekler > IntelliTrace > Genel**seçip **IntelliTrace olayları ve arama bilgileri**.

Çağrı bilgileri .NET Core ve ASP.NET Core uygulamaları için şu anda kullanılabilir değil. 

Bu, çağrı yığını Geçmişi'ne bakın ve geriye doğru adım ve kodunuzu çağrılarında üzerinden iletmek sağlar. IntelliTrace yöntem adları, yöntem giriş ve çıkış noktaları ve belirli parametre değerlerini ve dönüş değerleri gibi verileri kaydeder.

> [!TIP]
> Önemli ölçüde gider eklediğinden bu seçenek varsayılan olarak etkin değildir. Yalnızca IntelliTrace uygulamanızı yapar her yöntem çağrısı müdahale gerekmez, ancak Ayrıca ekranda gösteren veya diske kalıcı geldiğinde çok daha büyük bir veri ile mücadele etmek içerir.
>
> IntelliTrace kaydeden olayların listesini kısıtlayarak performans ek yükünü azaltabilir ve modülleri sayısı tutarak minimumda topluyorsunuz. Daha fazla bilgi için bkz: [denetim IntelliTrace kayıtları ne kadar bilgi çağrı](../debugger/intellitrace-features.md#ControlCallData).

### <a name="use-the-navigation-gutter"></a>Gezinti kanalı kullanın

Kod penceresi solunda görüntülenen gezinti kanalı kullanabilirsiniz. Gezinti kanalı görmüyorsanız, Git **Araçlar > Seçenekler > IntelliTrace > Gelişmiş**ve seçin **hata ayıklama modunda Gezinti kanalı görüntülemek**.

Gezinti kanalı yöntem çağrılarını ve geçmiş hata ayıklama modunda olayları aracılığıyla iletir ve geriye doğru taşımanızı sağlar. Geçmiş hata ayıklama hakkında daha fazla bilgi için bkz: [geçmiş hata ayıklama](../debugger/historical-debugging.md). Komutlarının sayısı vardır:

|||
|-|-|
|**Hata ayıklayıcı bağlamını burada ayarlayın**|Hata ayıklama bağlam göründüğü çağrısı dilimini ayarlayın.<br /><br /> Bu simge, yalnızca geçerli çağrı yığınındaki görüntülenir.|
|**Site çağrı geri dön**|İşaretçi ve hata ayıklama bağlamı geri burada geçerli işlevi çağrıldı için taşıyın.<br /><br /> Dinamik hata ayıklama modunda olduğunda, bu komut geçmiş hata ayıklama açar. Özgün yürütme sonu giderseniz, geçmiş hata ayıklama devre dışı ve dinamik hata ayıklama açıktır.|
|**Önceki arama veya IntelliTrace olayı gidin**|İşaretçi ve hata ayıklama bağlamı önceki arama veya olay geri dönün.<br /><br /> Canlı hata ayıklama modunda olduğunda bu komut geçmiş hata ayıklamasını etkinleştirir.|
|**Adımı**|Şu anda seçili işlevdeki adım.<br /><br /> Bu komut, yalnızca geçmiş hata ayıklama modunda olduğunda kullanılabilir.|
|**Sonraki çağrı veya IntelliTrace olayı gidin**|İşaretçi ve hata ayıklama bağlam sonraki çağrı veya olay verileri için hangi IntelliTrace var. taşıyın.<br /><br /> Bu komut, yalnızca geçmiş hata ayıklama modunda olduğunda kullanılabilir.|
|**Mod Canlı Git**|Dinamik hata ayıklama modu döndür.|

### <a name="search-for-a-line-or-method-in-intellitrace"></a>Bir satır veya IntelliTrace yönteminde aramak için

Yalnızca yöntemi çağrı bilgileri etkinleştirildiğinde yöntemleri arayabilirsiniz. IntelliTrace geçmiş belirli bir satırın veya yöntemi için arama yapabilirsiniz. Hata ayıklayıcı yürütme durdurulamaz olsa da, bağlam menüsünde görmek için işlev gövdesi içinde sağ tıklatın ve ya da **arama için bu satırı içinde IntelliTrace** veya **arama için bu yöntemi, IntelliTrace**.

### <a name="ControlCallData"></a> Denetim IntelliTrace kayıtları ne kadar bilgi arama

Varsayılan olarak IntelliTrace çözümünüz tarafından kullanılan tüm modülleri için bilgileri kaydeder. Sizi ilgilendiren modüller için kayıt çağrısı bilgilere IntelliTrace ayarlayabilirsiniz. İçinde **Araçlar > Seçenekler > IntelliTrace > modülleri**, dahil etmek için modül veya modülleri IntelliTrace dosyasından Dışla belirtebilirsiniz. IntelliTrace belirttiğiniz modüllerden kaynaklanan olayları toplar ve modülleri içinde gerçekleşen yöntem çağrılarını ilgilendiğiniz.

Birden çok modül eklemek için dizenin başında veya sonunda * joker karakterini kullanın. Modül isimleri için derleme adlarını değil dosya adlarını kullanın. Dosya yolları kabul edilmez.

En az olarak modül sayısı tutmaya çalışın. Toplanacak daha az veri olduğundan daha iyi performans elde. Üzerinden geçmek için daha az veri olduğundan kullanıcı Arabiriminde ayrıca daha az gürültü alın.

## <a name="SaveSession"></a> IntelliTrace verilerini dosyasına kaydetme

IntelliTrace topladığı veri kaydedebilirsiniz gidip **hata ayıklama > IntelliTrace > Kaydet IntelliTrace oturumunu** ayıkladığınız ve uygulamayı bir kesme durumda. Menü öğesi devre dışı bırakılır ve IntelliTrace uygulama hala çalışıyorsa veya hata ayıklama durdurduysanız topladığı verileri kaydetmek mümkün olmaz.

Otomatik olarak giderek bir dosyaya kaydetmek için IntelliTrace'i yapılandırabilirsiniz **Araçlar > Seçenekler > IntelliTrace > Gelişmiş** ve seçerek **deposu IntelliTrace kayıtlarını bu dizinde**. Alan tükendiğinde olduğunda eski verilerin üzerine yazmak IntelliTrace neden oluşturulan dosya boyutunu Ayarla da yapılandırabilirsiniz. Visual Studio iki dosyaları ne zaman otomatik olarak kaydedilir ve barındırma süreci (vshost.exe) Visual Studio açık her IntelliTrace oturum oluşturur.

> [!TIP]
> Disk alanı kaydetmek için artık gerekmediğinde dosyaları otomatik olarak kaydetmeme. Varolan dosyalar silinmez. Her zaman isteğe bağlı dosya bağlam menüsünden kaydedebilirsiniz.

Dosya için IntelliTrace verilerini kaydettiğinizde, IntelliTrace toplanan her işlem için bir .itrace dosyası alın. Giderek .itrace dosyasını Visual Studio'da sonra açabilirsiniz **Dosya > Aç > Dosya** ve Dosya Aç iletişim kutusundan .itrace dosya seçme. Daha fazla bilgi için bkz: [IntelliTrace verilerini kaydedilmiş kullanma](../debugger/using-saved-intellitrace-data.md).

## <a name="blogs"></a>Bloglar

[Visual Studio Enterprise 2015 IntelliTrace](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/intellitrace-in-visual-studio-ultimate-2015.aspx)

[İzlenecek yol, Canlı IntelliTrace Visual Studio 2015 (Metin Düzenleyicisi) kullanarak hata ayıklama](http://blogs.msdn.com/b/visualstudioalm/archive/2015/01/16/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-text-editor.aspx)

[İzlenecek yol, Canlı IntelliTrace Visual Studio 2015 (sosyal kulübü) kullanarak hata ayıklama](http://blogs.msdn.com/b/visualstudioalm/archive/2000/1/1/walkthrough-of-live-debugging-using-intellitrace-in-visual-studio-2015-social-club.aspx)

[Visual Studio Enterprise destekler ekleme artık 2015'te IntelliTrace!](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/intellitrace-in-visual-studio-enterprise-2015-now-supports-attach.aspx)

[IntelliTrace Standalone Collector kullanarak bir windows Hizmeti'nden verilerini topla](http://blogs.msdn.com/b/visualstudioalm/archive/2015/05/14/collect-data-from-a-windows-service-using-the-intellitrace-standalone-collector.aspx)

[IntelliTrace koleksiyon planı düzenleme](http://blogs.msdn.com/b/visualstudioalm/archive/2015/03/09/editing-the-intellitrace-collection-plan.aspx)

[Özel TraceSource ve IntelliTrace kullanarak hata ayıklama](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/17/custom-tracesource-and-debugging-using-intellitrace.aspx)

[IntelliTrace Standalone Collector ve uygulama havuzları çalışan Active Directory hesaplar](http://blogs.msdn.com/b/visualstudioalm/archive/2014/12/22/intellitrace-standalone-collector-and-application-pools-running-under-active-directory-accounts.aspx)

## <a name="forums"></a>Forumlar

[Visual Studio Debugger](http://go.microsoft.com/fwlink/?LinkId=262263)

## <a name="videos"></a>Videolar

[IntelliTrace deneyimi](https://channel9.msdn.com/Series/Visual-Studio-2015-Enterprise-Videos/IntelliTrace-Experience)

[Microsoft Visual Studio IntelliTrace ile geçmiş hata ayıklama Ultimate 2015](https://channel9.msdn.com/events/Ignite/2015/BRK3716)
