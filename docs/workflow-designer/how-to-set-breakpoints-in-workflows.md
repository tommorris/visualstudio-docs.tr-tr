---
title: 'Nasıl yapılır: kesme akışlarında | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: e41b21c9-c061-4358-8e2f-eb5e412864a8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e4112e74336faf1fb456ebd94dd7c7617747a11f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-set-breakpoints-in-workflows"></a>Nasıl yapılır: iş akışlarında kesme noktalarını ayarlama
Windows iş akışı Tasarımcısı kullandığınızda, Visual Basic veya C# kodunda yaptığınız gibi grafik iş akışlarında kesme noktaları ayarlayabilirsiniz. Beklendiği gibi iş akışı yürütme ayarladığınız her kesme noktasında durur.

 Üç durumlu bir kesme noktası vardır: *bekleyen*, *bağlı*, ve *hata*. Bir kesme noktası ayarladığınızda, bekleyen ve düz bir kırmızı simgesiyle gösterilir. Çalışma zamanı iş akışı türü yüklendiğinde bağlı olur. Geçerli olmayan bir etkinlik adı gibi kesme için yanlış bir biçim belirtirseniz, bir hata penceresi görünür. Kesme noktası hala kesme noktası penceresine eklenen ancak küçük "x" ile işaretlenmiş.

> [!NOTE]
> Çağrılan iş akışlarında kesme noktalarını ayarlama desteklenmez.

> [!WARNING]
> Seçeneği belirlediğinizden emin olun **sadece kendi kodumu etkinleştir (sadece yönetilen)** gelen **Araçları**, **seçenekleri**, **hata ayıklama** , önce menüsü hata ayıklama. İçinde başka bir sırayla iç içe geçmiş iki sıraları varsa ve ilk iç dizisi üzerinde bir kesme noktası ayarlayın, tuşuna basarak **F11** ikinci iç dizisi debug if değil **sadece kendi kodumu etkinleştir (yönetilen yalnızca)**seçeneği seçili değil.

> [!WARNING]
> XAML dosya özelliği tam yolu doğru değilse, bir iş akışında kesme noktaları karşılaşır değil. Proje/çözüm taşıdıktan sonra başka bir klasöre veya başka bir makine özelliği XAML dosyasının tam yolunu doğru değil. Kaydetmek ve tam yolu özelliği güncelleştirmek için CTRL + S seçin.

### <a name="to-set-a-breakpoint-on-an-activity-in-the-design-view"></a>Tasarım görünümünde bir etkinlikte bir kesme noktası ayarlamak için

1.  Üzerinde ayırmak için hata ayıklayıcı istediğiniz etkinliği seçin.

2.  Üzerinde **hata ayıklama** menüsünde, select **kesme**. Etkinlik sol üst kenarına kırmızı bir simge görüntülenir.

     Alternatif olarak, kısayol tuşlarına da basabilirsiniz **F9** etkinlik veya seçerek etkinliğe sağ tıklayın ve da seçin sonra anahtar **kesme noktası** sonra **kesme noktası Ekle**ve bağlam menüsünden.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl Yapılır: İş Akışı Hata Ayıklayıcısını Çağırma](../workflow-designer/how-to-invoke-the-workflow-debugger.md)
- [İş Akışı Tasarımcısı ile İş Akışlarında Hata Ayıklama](../workflow-designer/debugging-workflows-with-the-workflow-designer.md)
- [Nasıl Yapılır: İş Akışı Tasarımcısı ile XAML Hatalarını Ayıklama](../workflow-designer/how-to-debug-xaml-with-the-workflow-designer.md)