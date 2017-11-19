---
title: "Yerel bir değişken - kod oluşturma (Visual Basic) tanıtmak | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1490d6ac-ed56-4d03-95db-c23f23cba70d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 67302893dbebb65316b9c2aab09f70ddaa3e6567
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="introduce-a-local-variable-in-visual-basic"></a>Visual Basic'te yerel bir değişken tanıtır
**Ne:** hemen var olan bir ifade değiştirmek için yerel bir değişken oluşturmanıza olanak sağlar.

**Ne zaman:** yerel bir değişkende olsaydı, kolayca daha sonra yeniden koduna sahip.  

**Neden:** kopyalayın ve yerel değişken throughought kullanın, bir yerel değişkende sonucu depolamak ve bir kez işlemi gerçekleştirmek daha iyi ancak kodu çeşitli yerlerde kullanmak için birden çok kez yapıştırın. 

**Nasıl:**

1. Yeni yerel bir değişkene atamak istediğiniz ifade vurgulayın.

   ![Vurgulanmış kodu](media/local_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **(tüm oluşumları için) yerel tanıtmak '*ifade*' ** önizleme penceresi açılan, gelen nerede *ifade* vurgulanmış kodu.
   * **Fare**
     * Sağ tıklayın ve **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select  **(tüm oluşumları için) yerel tanıtmak '*ifade*' ** önizleme penceresi açılan, gelen Burada *ifade* vurgulanmış kodu.
     * ' I tıklatın ![Ampul](media/bulb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Yerel Önizleme tanıtır](media/local_preview.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Yerel değişken kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak oluşturulur.  Yeni yerel değişken bu yazarak yeni bir ad verin.

   ![Yerel sonuç tanıtır](media/local_result.png)

   >[!NOTE]
   >Kullanabileceğiniz **.. olan örnek...**  her bulundu, seçilen ifade yalnızca özellikle vurgulanmış bir örneğini değiştirmek için menü seçeneği.

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md) 