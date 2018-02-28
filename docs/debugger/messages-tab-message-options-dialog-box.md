---
title: "İletiler sekmesi, ileti seçenekleri iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: b7c9d533d73039de699f59c2343f3f91f888710c
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2018
---
# <a name="messages-tab-message-options-dialog-box"></a>İletiler Sekmesi, İleti Seçenekleri İletişim Kutusu
Kullanım **iletileri** listesine ileti türlerini seçmek için sekme [iletiler görünümünü](../debugger/messages-view.md)ve ileti arama ölçütlerini belirtmek için. Görüntülenecek [ileti seçenekleri iletişim kutusu](../debugger/message-options-dialog-box.md), seçin **günlük iletilerini** gelen **Spy** menüsü.  
  
 Genellikle, ilk seçtiğiniz **ileti grupları**ve ardından seçimi tek tek seçerek ince ayar yapma **iletileri görüntülemek için**. **Tüm** düğmesini seçer tüm ileti türleri ve **hiçbiri** düğmesi tüm türleri temizler.  
  
 Aşağıdaki ayarlar kullanılabilir **iletileri** sekmesi:  
  
 **İletileri görüntülemek için**  
 Belirli iletileri görüntülemek için seçin. Yeni bir ileti penceresi oluşturduğunuzda, tüm iletileri görüntüleyebilirsiniz. Filtre zaman gelen iletileri **iletileri** sekmesinde, bu filtre yalnızca uygulanır yeni iletiler, zaten Windows görünümünde görüntülenen iletileri.  
  
 **İleti grupları**  
 İleti gruplarını görüntülemek için seçin. Kullanılabilir grupları Ekle:  
  
-   WM_USER: bir kod WM_USER eşit veya daha büyük  
  
-   Kayıtlı: kayıtlı **RegisterWindowMessage** çağırın  
  
-   Bilinmiyor: Bilinmeyen iletileri aralıktaki 0 (WM_USER - 1)  
  
 Unutmayın bunlar **ileti grupları** altında belirli girişlere eşlemediğinden **iletiler için görünümü**. Bir grup seçtiğinizde, seçimi doğrudan ileti akışı uygulanır.  
  
 Bir gri onay kutusu içinde **ileti grupları** belirten **iletiler için görünümü** liste kutusu, o gruptaki iletilerde değiştirildi; o gruptaki ileti türlerinin tümü seçilir.  
  
 **Ayarları varsayılan olarak Kaydet**  
 Daha sonra kullanmak için geçerli ayarları ileti arama seçenekleri kaydedin. Bu ayarlar, ayrıca Spy ++ çıkarken kaydedilir.