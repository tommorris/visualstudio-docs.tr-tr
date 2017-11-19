---
title: "Kural kümeleri kullanma çalıştırılacak C++ kurallarını belirtmek için | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac3877e6-5349-4c03-9541-3d5be259f1e8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5ad51388ae1580ada61442798b46048ad71ece64
ms.sourcegitcommit: fb751e41929f031d1a9247bc7c8727312539ad35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="using-rule-sets-to-specify-the-c-rules-to-run"></a>Çalıştırılacak C++ Kurallarını Belirtmek için Kural Kümeleri Kullanma
İçinde [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] ve [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)], oluşturma ve özel bir değiştirme *kural kümesi* Kod Analizi ile ilişkilendirilmiş belirli proje gereksinimlerini karşılamak için. C++ özel bir kural oluşturmak için C/C++ projesi Visual Studio IDE içinde açık olması gerekir. Kural kümesi Düzenleyicisi'nde bir standart bir kural kümesi'ni açın ve ardından ekler veya belirli kuralları kaldırın ve isteğe bağlı olarak Kod Analizi kural ihlal ettiğini belirlediğinde gerçekleştirilen eylemleri değiştirebilirsiniz.  
  
 Yeni özel bir kural oluşturmak için yeni bir dosya adı kullanarak kaydedin. Özel kural kümesi projeye otomatik olarak atanır.  
  
## <a name="opening-the-rule-set-editor"></a>Açma kural kümesi Düzenleyici  
  
#### <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Tek bir var olan kural kümesinden özel bir kural oluşturmak için  
  
1.  Çözüm Gezgini'nde, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  Üzerinde **özellikleri** sekmesinde, seçin **Kod Analizi**.  
  
3.  İçinde **kural kümesi** aşağı açılan listesinde, aşağıdakilerden birini yapın:  
  
    -   Özelleştirmek istediğiniz kural kümesini seçin.  
  
     \-veya -  
  
    -   Seçin  **\<Gözat... >** mevcut bir kuralı kümesini belirlemek için listede değil.  
  
4.  Seçin **açık** kuralları kural kümesi Düzenleyicisi'nde görüntülenecek.  
  
#### <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Bir kural değiştirmek için kural kümesi Düzenleyicisi'nde ayarlayın  
  
-   Kural kümesi görünen adını değiştirmek için **Görünüm** menüsünde seçin **Özellikler penceresini**. Görünen ad girin **adı** kutusu. Görünen adı dosya adından farklı olabilir dikkat edin.  
  
-   Grubun tüm kuralları bir özel kural kümesine eklemek için Grup onay kutusunu seçin. Grubun tüm kuralları kaldırmak için onay kutusunu temizleyin.  
  
-   Özel bir kural kümesi için belirli bir kural eklemek, kuralın onay kutusunu seçin. Kural kural kümesinden kaldırmak için onay kutusunu temizleyin.  
  
-   Bir kod analizi kural ihlal edildiğinde gerçekleştirilecek eylemi değiştirmek için tercih **eylem** kural için alan ve aşağıdaki değerlerden birini seçin:  
  
     **Uyar** -bir uyarı oluşturur.  
  
     **Hata** -bir hata oluşturur.  
  
     **Hiçbiri** -kural devre dışı bırakır. Bu eylem kural kümesi kuralı kaldırma aynıdır.  
  
#### <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Gruplandırmak için filtre veya kural kümesi Düzenleyici araç çubuğunu kullanarak kural kümesi Düzenleyici alanları değiştirin  
  
-   Tüm grupları kurallarında genişletmek için seçin **Tümünü Genişlet**.  
  
-   Tüm grupları kurallarında daraltmak için tercih **Daralt tüm**.  
  
-   Kurallar tarafından gruplandırılır alanını değiştirmek için alanından seçin **Group By** listesi. Gruplanmamış kuralları görüntülemeyi seçebilir  **\<Hiçbiri >**.  
  
-   Eklemek veya kural sütunlarında alanları kaldırmak istediğiniz **sütun seçenekleri**.  
  
-   Geçerli çözüme uygulamayın kuralları gizlemek için seçin **Gizle geçerli çözüme uygulamayın kuralları**.  
  
-   Gösterme ve gizleme hata eylemi atanmış olan kurallar arasında geçiş yapmak için tercih **Göster Kod Analizi hatalara neden olabilir kuralları**.  
  
-   Gösterme ve gizleme uyarı eylemi atanmış olan kurallar arasında geçiş yapmak için tercih **Göster Kod Analizi uyarıları oluşturan kuralları**.  
  
-   Gösterme ve gizleme atanan kuralları arasında geçiş yapmak için **hiçbiri** eylemi seçin **Göster etkin olmayan kuralları**.  
  
-   Eklemek veya varsayılan kural kümesi geçerli kural kümesinde Microsoft kaldırmak istediğiniz **ekleme veya kaldırma alt kural kümeleri**.