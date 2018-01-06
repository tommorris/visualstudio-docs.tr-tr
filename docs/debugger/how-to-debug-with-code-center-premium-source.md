---
title: "Nasıl yapılır: Kod Merkezi birincil kaynağı ile hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Code Center Premium
- debugging [Visual Studio], Code Center Premium
ms.assetid: 18b4769d-b007-4428-9dae-9e72c283ff0d
caps.latest.revision: "23"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d7405deed95f14314215b869a02bcf8a1afddea2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-debug-with-code-center-premium-source"></a>Nasıl Yapılır: Kod Merkezi Birincil Kaynağı ile Hata Ayıklama
İle [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] hata ayıklayıcı, Microsoft MSDN Kod Merkezi birincil güvenli paylaşılan kaynaktan ayıklayabilirsiniz.  
  
 Bu konuda, ayarlama ve Visual Studio'da kod merkezi birincil kaynağı kodda hata ayıklama açıklanmaktadır.  
  
### <a name="to-prepare-for-debugging-with-code-center-premium"></a>Kod Merkezi birincil ile hata ayıklama için hazırlamak için  
  
1.  Akıllı kart okuyucu bağlanmak ve paylaşılan kaynak Initiative elde edilen kartı takın.  
  
2.  Visual Studio'yu başlatın.  
  
3.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
4.  İçinde **seçenekleri** açık iletişim kutusunu **hata ayıklama** düğümü ve tıklatın **genel**.  
  
5.  Clear **sadece kendi kodumu etkinleştir (sadece yönetilen)** onay kutusu.  
  
6.  Seçin **etkinleştirmek kaynak sunucu desteğini etkinleştir**.  
  
7.  Clear **kaynak dosyaları tam olarak eşleşen özgün sürümü gerektiren**.  
  
8.  Altında **hata ayıklama** düğümünü tıklatın **simgeleri**.  
  
9. İçinde **simge dosyası (.pdb) konumları** kutusunun işaretini kaldırın **Microsoft Server simgeleri** onay kutusunu işaretleyin ve aşağıdaki konumlardan ekleyin:  
  
     `https://codepremium.msdn.microsoft.com/symbols`  
  
     `src=https://codepremium.msdn.microsoft.com/source/Visual%20Studio%202010/SP1/`  
  
    > [!NOTE]
    >  Eğik eklediğinizden emin olun **/**  yolun sonuna.  
  
     Bu konumları bu simgeleri ilk yüklü olduğundan emin olmak için listenin üstüne taşıyın.  
  
    > [!NOTE]
    >  Yüklenen ilk konumları; böylece bu kod merkezi birincil konumları listelenmesi gerekir. Visual Studio 2010'da, yukarıdaki tüm sunucularını taşıyamazsınız **Microsoft simge sunucuları** onay kutusunu temizlemeniz gerekir neden olan girişi.  
    >   
    >  Hata ayıklama oturumu sırasında Microsoft sembolleri Semboller yüklemek için bunu yapın:  
    >   
    >  1.  Üzerinde **hata ayıklama** menüsünde seçin **Windows** ve ardından **modülleri**.  
    > 2.  Simgelerini istediğiniz modülü seçin ve ardından kısayol menüsünü açın. Seçin **yük simgeleri gelen** ve ardından **Microsoft simge sunucuları**.  
  
10. İçinde **önbelleğe simge sunucuları bu dizinde sembolleri** kutusunda, bir konum girin `C:\symbols` burada kod merkezi birincil önbelleğe simgeler. Simgeler önbelleğe alma hata ayıklama sırasında performansı önemli ölçüde artırabilir.  
  
     Kaynak kodu ile hata ayıklama zorluk yaşıyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bu yordamı tamamladıktan sonra simge önceden önbelleğe alınan ve güncel olmayan dosyalar için önbellek konumu denetleyin. Eski simge dosyalarını kaldırın.  
  
11. **Tamam**'ı tıklatın.  
  
12. Yeniden [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ayarları kalıcı olduğuna emin olmak için.  
  
### <a name="to-debug-your-source-code-using-attach-to-process"></a>İşleme Ekle kullanarak kaynak kodunuzu hata ayıklamak için  
  
1.  Akıllı kart okuyucu bağlanmak ve paylaşılan kaynak Initiative elde edilen kartı takın.  
  
2.  Visual Studio'yu başlatın.  
  
3.  Visual Studio projenizi açın.  
  
4.  Üzerinde **Araçları** menüsünde tıklatın **ekleme işlemi için**.  
  
5.  İçinde **ekleme işlemi için** iletişim kutusu, tıklatın **seçin**.  
  
6.  İçinde **kod türünü seç** iletişim kutusunda **bu kodu türlerini algılamak**seçin **yerel**, **yönetilen**, ve **yönetilen () v4.0)**.  
  
7.  Tıklatın **Tamam** kapatmak için **kod türünü seç** iletişim kutusu.  
  
8.  İçinde **kullanılabilir işlemler** kutusunda, hata ayıklamak için istediğiniz işlemi seçin.  
  
9. Tıklatın **Attach**.  
  
10. Sertifikanızı onaylamanız istendiğinde, tıklatın **Tamam**. Ardından PIN kodunuzu girin. Kod Merkezi birincil kullanım koşullarını kabul, istendiğinde kullanılır.  
  
     Simgeler indirme çok sayıda ağ hızına bağlı olarak zaman alabilir. Tüm sembolleri başarıyla indirildi zaman durum çubuğunu gösterir.  
  
11. Çözümünüzdeki tüm yönetilen projeleri için ek adımları yineleyin.  
  
### <a name="to-debug-source-code-from-an-existing-solution"></a>Varolan bir çözümü kaynak kodundan hata ayıklamak için  
  
1.  İçinde **Çözüm Gezgini**, çözüm için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  Çözüm özellik sayfaları iletişim kutusunda seçin **kaynak dosyalarında Hata Ayıkla** içinde **ortak özellikleri** düğümü.  
  
3.  Şu konuma eklemek **kaynak dosyalarını içeren dizinler** listesi:  
  
     `https://codepremium.msdn.microsoft.com/source/Visual%20Studio%202010/SP1/`  
  
    > [!NOTE]
    >  Eğik eklediğinizden emin olun **/**  yolun sonuna.  
  
4.  Çözümünüzü yönetilen her proje için aşağıdakileri yapın  
  
    1.  Çözüm Gezgini'nde, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
    2.  Seçin **hata ayıklama** ve ardından **yönetilmeyen kod hata ayıklamayı etkinleştir**.  
  
### <a name="to-debug-your-solution-with-code-center-premium-source"></a>Çözümünüzü kod merkezi birincil kaynağı ile hata ayıklamak için  
  
1.  İçinde `Package` sınıfı, bir kesme noktası paket Oluşturucu ayarlayın.  
  
2.  İçinde `Debug` menüsünde tıklatın **hata ayıklamayı Başlat**.  
  
3.  Paketi oluşturucusundaki kesme noktası isabet, Git **çağrı yığını** penceresini açın ve ardından simge, yüklemek istediğiniz derlemenin yığın çerçevesi sağ tıklatın **yük simgeleri**.  
  
     Kaynak yüklemek için çağrı çerçevesi çift tıklayın.  
  
### <a name="to-browse-source-code-on-code-center-premium"></a>Kod Merkezi birincil kaynağı kodu gözatmak için  
  
1.  Akıllı kart okuyucu bağlanmak ve paylaşılan kaynak Initiative elde edilen kartı takın.  
  
2.  Başlatma Internet Explorer aşağıdaki URL'yi girin:`https://codepremium.msdn.microsoft.com`  
  
3.  İstediğiniz kaynak bulmak için Gözat'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)   
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Kod Merkezi birincil](http://www.microsoft.com/resources/sharedsource/ccp.mspx)