---
title: "Nasıl yapılır: bir temel doku gölgelendirici oluşturun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5af113fb-6415-4be0-8b23-10fddb10e80a
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 52e909e911a552b69930ef6a60257fca29a0794d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-basic-texture-shader"></a>Nasıl Yapılır: Temel Doku Gölgelendiricisi Oluşturma
Bu belgede gölgelendirici Tasarımcısı ve yönlendirilmiş grafik gölgelendirici dili (DGSL) tek doku gölgelendirici oluşturmak için nasıl kullanılacağı gösterilmektedir. Bu gölgelendirici son renk doğrudan RGB ve doku örneklenen alfa değerleri ayarlar.  
  
 Bu belgede, bu etkinlikler gösterir:  
  
-   Gölgelendirici grafikten düğümleri kaldırma  
  
-   Grafiğe düğüm ekleme  
  
-   Gölgelendirici parametreleri ayarlama  
  
-   Parametre görünürlük ayarlama  
  
-   Düğümlerini bağlayan  
  
## <a name="creating-a-basic-texture-shader"></a>Temel doku gölgelendirici oluşturma  
 Temel, tek doku gölgelendirici doğrudan son çıkış rengi renk ve alfa değerleri bir doku örnek yazarak uygulayabilirsiniz.  
  
 Başlamadan önce emin olun **özellikleri** penceresi ve **araç** görüntülenir.  
  
#### <a name="to-create-a-basic-texture-shader"></a>Temel doku gölgelendirici oluşturmak için  
  
1.  Çalışmak için DGSL gölgelendirici oluşturun. Başlarken bölümünde DGSL gölgelendirici projenize ekleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md).  
  
2.  Silme **nokta rengi** düğümü. İçinde **seçin** modunu Seç **nokta rengi** düğümü ve ardından menü çubuğunda, **Düzenle**, **silmek**. Bu, sonraki adımda eklenen düğüm için yer sağlar.  
  
3.  Ekleme bir **doku örnek** grafiğe düğüm. İçinde **araç**altında **doku**seçin **doku örnek** ve tasarım yüzeyine taşıyın.  
  
4.  Ekleme bir **doku koordine** grafiğe düğüm. İçinde **araç**altında **doku**seçin **doku koordine** ve tasarım yüzeyine taşıyın.  
  
5.  Uygulanacak bir doku seçin. İçinde **seçin** modunu seçin **doku örnek** düğümünü ve ardından **özellikleri** penceresinde kullanarak kullanmak istediğiniz doku belirtin **Filename**  özelliği.  
  
6.  Doku genel olarak erişilebilir hale getirir. Seçin **doku örnek** düğümünü ve ardından **özellikleri** penceresindeki ayarlayın **erişim** özelliğine **ortak**. Başka bir aracından gibi doku ayarlayabilirsiniz artık **Model Düzenleyicisinde**.  
  
7.  Doku koordinatları doku örneğe bağlanın. İçinde **seçin** modu, taşıma **çıkış** , terminal **doku koordine** düğüme **UV** , terminal **doku Örnek** düğümü. Bu bağlantı belirtilen koordinatlarının adresindeki doku örnekleri.  
  
8.  Doku örnek son renk bağlayın. Taşıma **RGB** , terminal **doku örnek** düğüme **RGB** , terminal **son renk** düğümünü ve ardından taşıyın **Alfa** , terminal **doku örnek** düğüme **alfa** , terminal **son renk** düğümü.  
  
 Aşağıdaki çizimde, grafik ve bir küp uygulanan gölgelendirici önizlemesini tamamlanmış gölgelendirici gösterir.  
  
> [!NOTE]
>  Bu çizimde, bir düzlemi Önizleme şekil olarak kullanılır ve bir doku daha iyi gölgelendirici etkisini göstermek için belirtilen.  
  
 ![Gölgelendirici grafik ve etkisini önizlemesini](../designers/media/digit-texture-effect.png "basamaklı doku etkisi")  
  
 Belirli şekillerin daha iyi önizlemeleri için bazı gölgelendiriciler sağlayabilir. Gölgelendirici Tasarımcısı'nda gölgelendiriciler önizleme hakkında daha fazla bilgi için bkz: [gölgelendirici Tasarımcısı](../designers/shader-designer.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: bir 3B modele gölgelendirici uygulama](../designers/how-to-apply-a-shader-to-a-3-d-model.md)   
 [Görüntü Düzenleyicisi](../designers/image-editor.md)   
 [Gölgelendirici Tasarımcısı](../designers/shader-designer.md)   
 [Gölgelendirici Tasarımcısı Düğümleri](../designers/shader-designer-nodes.md)