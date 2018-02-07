---
title: "Yerel bir değişken - kod oluşturma (Visual Basic) tanıtmak | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1490d6ac-ed56-4d03-95db-c23f23cba70d
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: abc0ef3ffdbada86a66bac9823894ee83d04047f
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="introduce-a-local-variable-in-visual-basic"></a>Visual Basic'te yerel bir değişken tanıtır
**Ne:** hemen var olan bir ifade değiştirmek için yerel bir değişken oluşturmanıza olanak sağlar.

**Ne zaman:** yerel bir değişkende olsaydı, kolayca daha sonra yeniden koduna sahip.  

**Neden:** kopyalayın ve yerel değişken throughought kullanın, bir yerel değişkende sonucu depolamak ve bir kez işlemi gerçekleştirmek daha iyi ancak kodu çeşitli yerlerde kullanmak için birden çok kez yapıştırın. 

**Nasıl:**

1. Yeni yerel bir değişkene atamak istediğiniz ifade vurgulayın.

   ![Vurgulanmış kodu](media/local-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **(tüm oluşumları için) yerel tanıtmak '*ifade*'** önizleme penceresi açılan, gelen nerede *ifade* vurgulanmış kodu.
   * **Fare**
     * Sağ tıklayın ve **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **(tüm oluşumları için) yerel tanıtmak '*ifade*'** önizleme penceresi açılan, gelen Burada *ifade* vurgulanmış kodu.
     * ' I tıklatın ![Ampul](media/bulb-vb.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Yerel Önizleme tanıtır](media/local-preview-vb.png)

   >[!TIP]
   >Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) seçiminizi yaptıktan önce yaptığınız tüm değişiklikleri görmek için Önizleme pencerenin altındaki bağlantıyı.

1. Yerel değişken kendi kullanımdan çıkarımı yapılan tür ile otomatik olarak oluşturulur.  Yeni yerel değişken bu yazarak yeni bir ad verin.

   ![Yerel sonuç tanıtır](media/local-result-vb.png)

   >[!NOTE]
   >Kullanabileceğiniz **.. olan örnek...**  her bulundu, seçilen ifade yalnızca özellikle vurgulanmış bir örneğini değiştirmek için menü seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md) 