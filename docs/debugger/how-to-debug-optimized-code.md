---
title: "Nasıl yapılır: iyileştirilmiş kodda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- breakpoints, in optimized code
- debugging [C++], optimized code
- optimization, debug builds
- debug builds, optimizing
- optimized code, debugging
ms.assetid: fc8eeeb8-6629-4c9b-99f7-2016aee81dff
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12f376932a260c556ac2ea2b0f1a2a53c59c752f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-optimized-code"></a>Nasıl Yapılır: İyileştirilmiş Kodda Hata Ayıklama
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için Araçlar menüsünden içeri ve dışarı aktarma ayarları seçin. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
> [!NOTE]
>  [/Zo (geliştirmek en iyi duruma getirilmiş hata ayıklama)](/cpp/build/reference/zo-enhance-optimized-debugging)derleyici seçeneği (Visual Studio güncelleştirme 3'te tanıtılan) en iyi duruma getirilmiş kodu için daha zengin hata ayıklama bilgileri oluşturur (ile oluşturulan olmayan projeleri **/Od** derleyici seçeneği. Bkz: [/O seçenekler (kodu İyileştir)](/cpp/build/reference/o-options-optimize-code)). Bu, yerel değişkenleri ve satır içi işlevleri hata ayıklama için geliştirilmiş destek içerir.  
>   
>  [Düzenle ve devam et](../debugger/edit-and-continue-visual-csharp.md) ne zaman devre dışı **/Zo** ocompiler seçenek kullanılır.  
  
 Derleyici kodu en iyi duruma getirir, yeniden konumlandırır ve yönergeleri yeniden düzenler. Bu daha verimli derlenmiş kodda sonuçlanır. Bu yeniden düzenleme nedeniyle yapılmasını hata ayıklayıcı yönergeleri kümesine karşılık gelen kaynak kodu her zaman tanımlanamıyor.  
  
 En iyi duruma getirme etkileyebilir:  
  
-   İyileştirici tarafından kaldırıldı veya hata ayıklayıcı anlamadığı konumlara taşınan yerel değişkenler.  
  
-   Kod blokları iyileştirici birleştirir bağlandığınızda değiştirilir konumlar bir işlev içinde.  
  
-   İyileştirici iki işlevlerini birleştirir, bir sorun olabilir çağrı yığınında çerçeveler için işlev adlarını.  
  
 Çağrı yığınındaki gördüğünüz çerçeveler neredeyse her zaman ancak, tüm çerçeveler simgelerini sahip olduğu varsayılarak doğrudur. Çerçeveler çağrı yığınında derleme dilde işlevleri varsa yığın bozulması varsa veya işletim sistemi çerçeveler çağrı yığınında eşleştirme simgeleri olmadan varsa yanlış olacaktır.  
  
 Genel ve statik değişkenleri her zaman doğru şekilde gösterilir. Bu nedenle yapısı düzeni olur. Bir işaretçi yapısına sahip ve işaretçi değeri doğru ise, her üye değişkeni yapısı doğru değerini gösterir.  
  
 Bu sınırlamalar nedeniyle programınızın iyileştirilmemiş bir sürümünü mümkünse kullanarak hata ayıklama. Varsayılan olarak, en iyi duruma getirme bir Visual C++ programı hata ayıklama yapılandırmasını da kapalı ve sürüm yapılandırmasında açık.  
  
 Ancak, bir hata yalnızca en iyi duruma getirilmiş bir program sürümünde görünebilir. Bu durumda, iyileştirilmiş kodda hata ayıklama gerekir.  
  
### <a name="to-turn-on-optimization-in-a-debug-build-configuration"></a>Bir hata ayıklama iyileştirme açmak için yapılandırma oluşturma  
  
1.  Yeni bir proje oluşturduğunuzda seçmeniz `Win32 Debug` hedef. Kullanım `Win32``Debug` programınızı tam hata ayıklaması ve oluşturmak hazır kadar hedef bir `Win32 Release` hedef. Derleyici değil en iyi duruma getirme `Win32 Debug` hedef.  
  
2.  Çözüm Gezgini'nde proje seçin.  
  
3.  Üzerinde **Görünüm** menüsünde tıklatın **özellik sayfaları**.  
  
4.  İçinde **özellik sayfaları** iletişim kutusunda, emin olun `Debug` seçildiyse **yapılandırma** aşağı açılan liste.  
  
5.  Solda klasör görünümünde seçin **C/C++** klasör.  
  
6.  Altında **C++** klasöründe seçin `Optimization`.  
  
7.  Sağdaki özellikler listesinde bulun `Optimization`. Ayar yanında büyük olasılıkla diyor `Disabled (` [/Od](/cpp/build/reference/od-disable-debug)`)`. Diğer seçeneklerden birini seçin (`Minimum Size``(`[/O1](/cpp/build/reference/o1-o2-minimize-size-maximize-speed)`)`, `Maximum Speed``(` [O2](/cpp/build/reference/o1-o2-minimize-size-maximize-speed)`)`, `Full Optimization``(` [/Ox](/cpp/build/reference/ox-full-optimization) `)`, veya `Custom`).  
  
8.  Seçerseniz `Custom` seçenek için `Optimization`, artık özellikler listesinde gösterilen diğer özelliklerinden herhangi birini seçeneklerini ayarlayabilirsiniz.  
  
9. Geçiyor özellikleri, C/C++, proje özellikleri sayfasında komut satırı düğümünü seçin ve ekleyin `(` [/Zo](/cpp/build/reference/zo-enhance-optimized-debugging) `)` için **ek seçenekler** metin kutusu.  
  
    > [!WARNING]
    >  `/Zo`Visual Studio 2013 güncelleştirme 3 veya sonraki bir sürümünü gerektirir.  
    >   
    >  Ekleme `/Zo` devre dışı bırakır [Düzenle ve devam et](../debugger/edit-and-continue-visual-csharp.md).  
  
 İyileştirilmiş kodda hata ayıklarken kullanmak **ayrıştırılmış** hangi yönergeleri gerçekten oluşturulduğunu ve yürütülen görmek için penceresi. Kesme noktaları ayarladığınızda, kesme noktası ile birlikte bir yönerge taşıma bilmeniz gerekir. Örneğin, aşağıdaki kodu göz önünde bulundurun:  
  
```  
for (x=0; x<10; x++)  
```  
  
 Bu satırında bir kesme noktası belirleyerek varsayalım. 10 kez çıkmaya kesme noktası beklediğiniz, ancak iyileştirilmiş kodda, yalnızca bir kez kesme noktası isabet. İlk yönergenin değerini ayarlar çünkü `x` 0. Bu yalnızca bir kez yapılması gerekir ve döngü dışında taşır, derleyicisi tanır. Kesme noktası ile taşır. Karşılaştırır ve Artır yönergeleri `x` döngünün içinde kalır. Görüntülediğinizde **ayrıştırılmış** penceresinde [adım birimini](http://msdn.microsoft.com/en-us/8791dac9-64d1-4bb9-b59e-8d59af1833f9) yönergesi için en iyi duruma getirilmiş kod üzerinden adım bağlandığınızda yararlıdır daha fazla denetim için otomatik olarak ayarlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)