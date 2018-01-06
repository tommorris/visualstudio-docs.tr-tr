---
title: "Nasıl yapılır: uygulama hata işaretçileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - error markers
ms.assetid: e8e78514-5720-4fc2-aa43-00b6af482e38
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d41c1bf063ea074df217934a00f73291a10e051d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-error-markers"></a>Nasıl yapılır: uygulama hata işaretçileri
Hata işaretçileri (veya kırmızı dalgalı alt çizgiler) uygulamak için metin düzenleyici özelleştirmeleri en zor olduğu. Ancak, VSPackage kullanıcılara verdikleri avantajları kadar sağlayacağını maliyetinden üstün. Hata işaretçileri dilden çok az dil Ayrıştırıcıyı dalgalı veya dalgalı bir kırmızı çizgiyle yanlış uymak açısından gerekli olduğunu metin işaretleyin. Bu göstergenin görsel olarak yanlış kod görüntüleyerek programcıları yardımcı olur.  
  
 Kırmızı dalgalı alt çizgiler uygulamak için metin işaretçileri kullanın. Bir kural olarak, dil hizmetlerini kırmızı dalgalı alt çizgiler metin arabelleğini arka plan geçiş olarak boşta kalma zaman veya bir arka plan iş parçacığı ekleyin.  
  
### <a name="to-implement-the-red-wavy-underline-feature"></a>Kırmızı dalgalı alt çizgi özelliği uygulamak için  
  
1.  Altında kırmızı dalgalı alt çizgi yerleştirmek istediğiniz metni seçin.  
  
2.  Bir işaretçi türü oluşturma `MARKER_CODESENSE_ERROR`. Daha fazla bilgi için bkz: [nasıl yapılır: standart metin işaretçileri eklemek](../extensibility/how-to-add-standard-text-markers.md).  
  
3.  Bundan sonra geçirin bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> arabirimi işaretçisi.  
  
 Bu işlem, ipucu metnini veya bir özel bağlam menüsü belirli bir işaret oluşturmanıza olanak sağlar. Daha fazla bilgi için bkz: [nasıl yapılır: standart metin işaretçileri eklemek](../extensibility/how-to-add-standard-text-markers.md).  
  
 Aşağıdaki nesneler hata işaretçileri görüntülenebilmesi gereklidir.  
  
-   Bir Ayrıştırıcı.  
  
-   Bir görev sağlayıcısı (diğer bir deyişle, uygulaması <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider2>), tutar satırı bilgileri değişiklikleri kaydını yeniden ayrıştırılmış olmasını satırları belirlemek amacıyla.  
  
-   Şapka yakalayan metin Görünüm filtresi değişiklik olayları görünüm kullanımından <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents.OnChangeCaretLine%2A>) yöntemi.  
  
 Ayrıştırıcı, görev sağlayıcısı ve filtre hata işaretçileri olanak sağlamak gerekli altyapıyı sağlar. Aşağıdaki adımlar, hata işaretçileri görüntülemek için işlem sağlar.  
  
1.  Filtre uygulanan bir görünümde, filtre bu görünümün verileri ile ilişkili görevi sağlayıcısı için bir işaretçi alır.  
  
    > [!NOTE]
    >  Yöntem ipuçları, deyim tamamlama, hata işaretçileri ve benzeri için aynı komutu filtresini kullanabilirsiniz.  
  
2.  Filtre için başka bir satır taşınmış belirten bir olayı aldığında, bir görev hataları denetlemek için oluşturulur.  
  
3.  Görev işleyici satırının kirli olup olmadığını denetler. Bu durumda, hatalar için satır ayrıştırır.  
  
4.  Hataları bulunamazsa, görev sağlayıcısı görev öğesi örneği oluşturur. Bu örnek metin görünümünde bir hata işaretçisi olarak ortamı kullanır metin işaretçisi oluşturur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Nasıl yapılır: standart metin işaretleyicileri ekleyin](../extensibility/how-to-add-standard-text-markers.md)   
 [Nasıl yapılır: özel metin işaretçileri oluşturma](../extensibility/how-to-create-custom-text-markers.md)   
 [Nasıl yapılır: metin işaretçileri kullanın](../extensibility/how-to-use-text-markers.md)