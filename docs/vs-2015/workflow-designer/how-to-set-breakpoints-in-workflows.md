---
title: 'Nasıl yapılır: iş akışlarında kesme noktası ayarlama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: deeacfede4ace0c06d0c35418fe55bd74e57b19e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633887"
---
# <a name="how-to-set-breakpoints-in-workflows"></a>Nasıl yapılır: iş akışlarında kesme noktası ayarlama
Kullanırken [!INCLUDE[wfd1](../includes/wfd1-md.md)], Visual Basic veya C# kodunda yaptığınız gibi grafik iş akışlarında kesme noktalarını ayarlayabilir. Beklendiği gibi iş akışı yürütme ayarladığınız her bir kesme noktasında durur.  
  
 Bir kesme noktası üç durumu vardır: *bekleyen*, *bağlı*, ve *hata*. Bir kesme noktası ayarlarsanız, bekleyen ve düz kırmızı bir simge ile temsil edilir. Çalışma zamanı iş akışı türü yüklendiğinde bağlı olur. Geçerli olmayan bir etkinliği adı gibi kesme noktası için yanlış biçim belirtirseniz bir hata penceresinde görünür. Kesme noktası hala kesme noktası penceresine eklenir, ancak küçük "x" ile işaretlenir.  
  
> [!NOTE]
>  Çağrılan iş akışlarında kesme noktaları ayarlama desteklenmiyor.  
  
> [!WARNING]
>  Seçeneğini belirlediğinizden emin olun **yalnızca benim kodumu etkinleştir (sadece yönetilen)** gelen **Araçları**, **seçenekleri**, **hata ayıklama** , önce menüsü hata ayıklama. Başka bir dizi içinde iç içe iki diziyi varsa ve ilk iç dizisi üzerinde bir kesme noktası ayarlayın, tuşuna basarak **F11** ikinci iç dizisi hata ayıklaması değil **yalnızca benim kodumu etkinleştir (sadece yönetilen)** seçeneği belirlenmez.  
  
> [!WARNING]
>  XAML dosya özelliği tam yolu doğru değilse, bir iş akışında kesme noktaları ulaşırsınız değil. Proje/çözüm taşıdıktan sonra başka bir klasöre veya başka bir makineye özelliği XAML dosyasının tam yolu doğru değil. Kaydet ve tam yolunu özelliği güncelleştirmek için CTRL + S seçin.  
  
### <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>Tasarım görünümünde bir etkinlikte bir kesme noktası ayarlamak için  
  
1.  Hata ayıklayıcı kesmek istediğiniz etkinliği seçin.  
  
2.  Üzerinde **hata ayıklama** menüsünde **iki durumlu kesme noktası**. Etkinlik sol üst kenarına kırmızı bir simge görünür.  
  
     Alternatif olarak, aynı zamanda kısayol tuşlarına basabilirsiniz **F9** etkinlik veya seçerek etkinliğe sağ tıklayın ve da seçin sonra anahtar **kesme noktası** ardından **kesme noktası Ekle**bağlam menüsünden.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: iş akışı hata ayıklayıcısını çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md)   
 [İş Akışı Tasarımcısı ile iş akışlarında hata ayıklama](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)   
 [Nasıl Yapılır: İş Akışı Tasarımcısı ile XAML Hatalarını Ayıklama](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)