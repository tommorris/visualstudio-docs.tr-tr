---
title: "Visual Studio hata ayıklayıcısında ayrıştırılmış kodu görüntüleme | Microsoft Docs"
ms.custom: H1Hack27Feb2017
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.disassembly
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- assembly language, debugging inline assembly code
- breakpoints, Disassembly window
- Disassembly window
- machine code
ms.assetid: eaf84dd0-c82d-481b-af51-690b74e7794c
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c72de947262cd87e4920d87c2d4d54664e02cc0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="view-disassembly-code-in-the-visual-studio-debugger"></a>Visual Studio hata ayıklayıcısında görünüm Ayrıştırılmış kod
Bu özellik yalnızca adres düzeyi hata ayıklama etkinleştirilirse kullanılabilir **seçenekleri** iletişim kutusu, **hata ayıklama** düğümü. Komut dosyası veya SQL hata ayıklama için kullanılabilir değil.  
  
 **Ayrıştırılmış** penceresi derleyici tarafından oluşturulan yönergeleri karşılık gelen bütünleştirilmiş kodu gösterir. Yönetilen kodda hata ayıklama, bu derleme yönergeleri sadece zamanında (JIT) derleyici, Visual Studio derleyici tarafından üretilen Microsoft Ara dilde değil (MSIL) tarafından oluşturulan yerel kod karşılık gelir.  
  
 Derleme yönergeleri yanı sıra **ayrıştırılmış** penceresi aşağıdaki isteğe bağlı bilgileri gösterir:  
  
-   Her yönerge bulunduğu bellek adresi. Yerel uygulamalar için bu gerçek bellek adresidir. Visual Basic, C# veya yönetilen kod için bir uzaklık işlevi başından itibaren dayalıdır.  
  
-   Kaynak kodu derleme kodunu türetilen.  
  
-   Kod bayt — bayt gösterimlerini gerçek makine ya da MSIL yönergeleri.  
  
-   Bellek adreslerini sembol adları.  
  
-   Kaynak koduna karşılık gelen sayıları satır.  
  
 Assembly dili yönergeleri yönerge adları ve değişkenleri, kaydeder ve sabitleri temsil eden simgeler kısaltmalar anımsatıcıları oluşur. Her makine dili yönerge genellikle bir veya daha fazla değişkenleri, kaydeder veya sabitler tarafından izlenen bir derleme dili anımsatıcı temsil edilir.  
  
 Assembly dili okuyun ve Ayrıştırılmış kod penceresini tam olarak yararlanmak iyi kitap assembly dili programlama hakkında başvurun. Assembly dili programlama ne Biz bu kısa giriş ayrıştırma penceresi içinde karşılayabilirsiniz kapsamının dışındadır.  
  
 Bütünleştirilmiş kodu, işlemci kaydeder veya yönetilen kod söz konusu olduğunda yoğun olarak kullandığından, ortak dil çalışma zamanı kaydeder, genellikle kayıt incelemek izin veren yazmaçlar penceresi ile birlikte ayrıştırma penceresi kullanmak yararlı içeriği.  
  
 Büyük olasılıkla hiçbir zaman isteğini sahip veya kaldıracak kendi ham, sayısal form yerine assembly dili makine kodu yönergeleri görüntülemeniz gerekir. Ancak, bunu yapmak istiyorsanız, bu amaçla bellek penceresi kullanın veya kodu bayt Ayrıştırılmış kod penceresini kısayol menüsünden seçin.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-display-the-disassembly-window"></a>Ayrıştırılmış kod penceresini görüntülemek için  
  
-   Hata ayıklarken, seçin **hata ayıklama > Windows** ve ardından **ayrıştırılmış**.
  
### <a name="to-turn-optional-information-on-or-off"></a>İsteğe bağlı bilgileri açmak veya kapatmak için  
  
-   Sağ **ayrıştırılmış** penceresinde ayarlayın ve kısayol menüsünde istenen seçeneklerini temizleyin.  
  
     Sol kenar boşluğunda sarı bir ok geçerli yürütme noktasının konumunu işaretler. Yerel kod için bu CPU'lar program sayacı karşılık gelir. Bu konum programınıza yürütülecek sonraki yönerge gösterir.  
  
     Daha fazla bilgi için bkz: [disk belleği yukarı veya aşağı bellekte](../debugger/how-to-page-up-or-down-in-memory.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)   
 [Nasıl yapılır: yazmaçlar penceresini kullanma](../debugger/how-to-use-the-registers-window.md)