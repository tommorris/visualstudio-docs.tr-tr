---
title: "Nasıl yapılır: bir özel kural kümesi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.addremoverulesets
helpviewer_keywords: Development Edition, rule sets
ms.assetid: bcc42508-9592-4802-9f66-a50111641d73
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 36b5e9e0a3ca0a994547679ba71e545b4235b6c5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-rule-set"></a>Nasıl yapılır: Özel Kural Kümesi Oluşturma
İçinde [!INCLUDE[vsUltShort](../code-quality/includes/vsultshort_md.md)], [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)], ve [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)], oluşturma ve özel bir değiştirme *kural kümesi* Kod Analizi ile ilişkilendirilmiş belirli proje gereksinimlerini karşılamak için. Özel bir kural oluşturmak için bir açın veya daha fazla standart kuralı kural kümesi Düzenleyicisi'nde ayarlar. Ekleyebilir veya belirli kuralları kaldırın ve Kod Analizi kural ihlal ettiğini belirlediğinde oluşan eylemi de değiştirebilirsiniz.  
  
 Yeni özel bir kural oluşturmak için yeni bir dosya adı kullanarak kaydedin. Özel kural kümesi projeye otomatik olarak atanır.  
  
## <a name="opening-the-rule-set-editor"></a>Açma kural kümesi Düzenleyici  
  
#### <a name="to-open-an-empty-rule-set-file-in-the-rule-set-editor"></a>Kural boş bir açmak için kural kümesi Düzenleyicisi'nde dosya kümesi  
  
1.  Üzerinde **dosya** menüsünü [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], işaret **yeni** ve ardından **dosya**.  
  
2.  İçinde **yeni dosya** iletişim kutusu, tıklatın **genel** içinde **yüklü şablonlar** listeleyin ve ardından **Kod Analizi kural kümesi**.  
  
3.  Kural kümesi Düzenleyicisi görüntülenir. Hiçbir kural Düzenleyicisi listesinde seçilir.  
  
#### <a name="to-create-a-custom-rule-from-a-single-existing-rule-set"></a>Tek bir var olan kural kümesinden özel bir kural oluşturmak için  
  
1.  Çözüm Gezgini'nde projeye sağ tıklayın ve ardından **özellikleri**.  
  
2.  Üzerinde **özellikleri** sekmesini tıklatın, **Kod Analizi**.  
  
3.  İçinde **kural kümesi** aşağı açılan listesinde, aşağıdakilerden birini yapın:  
  
    -   Özelleştirmek istediğiniz kural kümesini seçin.  
  
     \-veya -  
  
    -   Seçin  **\<Gözat... >** mevcut bir kuralı kümesini belirlemek için listede değil.  
  
4.  Tıklatın **açık** kuralları kural kümesi Düzenleyicisi'nde görüntülenecek.  
  
#### <a name="to-create-a-custom-rule-set-from-multiple-existing-rule-sets"></a>Özel bir kural oluşturmak için var olan birden çok kural kümesinden ayarlayın  
  
1.  Çözüm Gezgini'nde projeye sağ tıklayın ve ardından **özellikleri**.  
  
2.  Üzerinde **özellikleri** sekmesini tıklatın, **Kod Analizi**.  
  
3.  Seçin  **\<birden çok kural kümesi... Seç >** gelen **bu kural kümesini çalıştırmak**.  
  
4.  İçinde **Ekle veya Kaldır kural kümesi** kural ayarlar iletişim kutusunda, yeni kural kümesini temel ve ardından istediğiniz **Tamam**.  
  
5.  Yeni kural kümesi kaydedin.  
  
     Yeni Kural kümesinin adını seçili **bu kural kümesini çalıştırmak** listesi. Kural sonraki adımda kümesi görünen adını değiştirebilirsiniz.  
  
6.  (İsteğe bağlı) Kural kümesi görünen adını değiştirmek için **Görünüm** menüsünde tıklatın **Özellikler penceresini**. Görünen adı yazın **adı** kutusu.  
  
7.  Eklemek için kaldırmak veya yeni kural kümesinde belirli bir kod çözümleme kurallarını değiştirmek, **açık**.  
  
## <a name="modifying-a-rule-set"></a>Bir kural kümesini değiştirme  
  
#### <a name="to-modify-a-rule-set-in-the-rule-set-editor"></a>Bir kural değiştirmek için kural kümesi Düzenleyicisi'nde ayarlayın  
  
-   Kural kümesi görünen adını değiştirmek için **Görünüm** menüsünde tıklatın **Özellikler penceresini**. Görünen ad girin **adı** kutusu. Görünen adı dosya adından farklı olabilir dikkat edin.  
  
-   Grubun tüm kuralları bir özel kural kümesine eklemek için Grup onay kutusunu seçin. Grubun tüm kuralları kaldırmak için onay kutusunu temizleyin.  
  
-   Özel bir kural kümesi için belirli bir kural eklemek, kuralın onay kutusunu seçin. Kural kural kümesinden kaldırmak için onay kutusunu temizleyin.  
  
-   Bir kural bir kod analizi ihlal edildiğinde gerçekleştirilecek eylemi değiştirmek için tıklayın **eylem** kural için alan ve ardından aşağıdaki değerlerden birini seçin:  
  
     **Uyar** -bir uyarı oluşturur.  
  
     **Hata** -bir hata oluşturur.  
  
     **Hiçbiri** -kural devre dışı bırakır. Bu eylem kural kümesi kuralı kaldırma aynıdır.  
  
## <a name="changing-the-rule-set-editor-display"></a>Kural değiştirme Düzenleyicisi görüntü ayarlama  
  
#### <a name="to-group-filter-or-change-the-fields-in-the-rule-set-editor-by-using-the-rule-set-editor-toolbar"></a>Gruplandırmak için filtre veya kural kümesi Düzenleyici araç çubuğunu kullanarak kural kümesi Düzenleyici alanları değiştirin  
  
-   Tüm grupları kurallarında genişletmek için **Tümünü Genişlet**.  
  
-   Tüm grupları kurallarında daraltmak için **Daralt tüm**.  
  
-   Kurallar tarafından gruplandırılır alanını değiştirmek için alanından seçin **Group By** listesi. Gruplanmamış kurallarını görüntülemek için seçin  **\<Hiçbiri >**.  
  
-   Eklemek veya kural sütunlarında alanları kaldırmak için **sütun seçenekleri**.  
  
-   Geçerli çözüme uygulamayın kuralları gizlemek için **Gizle geçerli çözüme uygulamayın kuralları**.  
  
-   Gösterme ve gizleme hata eylemi atanmış olan kurallar arasında geçiş yapmak için tıklatın **Göster Kod Analizi hatalara neden olabilir kuralları**.  
  
-   Gösterme ve gizleme uyarı eylemi atanmış olan kurallar arasında geçiş yapmak için tıklatın **Göster Kod Analizi uyarıları oluşturan kuralları**.  
  
-   Gösterme ve gizleme atanan kuralları arasında geçiş yapmak için **hiçbiri** eylemini tıklatın **Göster etkin olmayan kuralları**.  
  
-   Ekleyin veya varsayılan kural kümesi geçerli kural kümesinde Microsoft kaldırmak için tıklatın **ekleme veya kaldırma alt kural kümeleri**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yönetilen kod projesi için kod çözümlemesini yapılandırma](../code-quality/how-to-configure-code-analysis-for-a-managed-code-project.md)   
 [Kod çözümleme kural kümesi başvurusu](../code-quality/code-analysis-rule-set-reference.md)