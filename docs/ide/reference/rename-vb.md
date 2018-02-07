---
title: "Düzenleme yeniden adlandırmak, Visual Basic'te | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 0f9421ed314dc513d5e8af30bad907766342300a
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2018
---
# <a name="rename-a-code-symbol-in-visual-basic"></a>Visual Basic kodu sembolü yeniden adlandırma

**Ne:** alanları, yerel değişkenleri, yöntemleri, ad alanları, özellikleri ve türleri gibi kodu sembolleri tanımlayıcıları yeniden adlandır olanak sağlar.

**Ne zaman:** güvenli bir şekilde bir şey tüm örneklerini bulun ve yeni bir ad kopyala/yapıştır zorunda kalmadan yeniden adlandırmak istediğiniz.

**Neden:** Kopyala ve yeni bir ad arasında projenin tamamında yapıştırma misiniz olasılıkla neden hatalar.  Bu yeniden düzenleme aracı doğru bir şekilde yeniden adlandırma eylemi gerçekleştirir.

**Nasıl:**

1. Vurgula veya metin imleci yeniden adlandırılacak öğesi içinde:

   ![Vurgulanmış kodu](media/rename-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + R**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > yeniden adlandırma**.
     * Kod sağ tıklatıp **yeniden adlandırma**.

1. Öğeyi yeni bir ad yazarak yeniden adlandırın.

   ![Animasyon yeniden adlandırma](media/rename-rename-vb.png)

   > [!TIP]
   > Ayrıca açıklamaları ve bu yeni ad kullanmak üzere diğer dizeleri güncelleştirebilirsiniz yanı [Önizleme değişiklikleri](../../ide/preview-changes.md) önce kaydetme, içinde onay kutularını kullanarak **yeniden adlandırmak** üstünde görünür kutusunu IDE'yi sağında.

1. Değişiklikle memnun kaldığınızda, tıklatın **Uygula** düğmesini veya tuşuna **Enter** ve değişiklikler uygulanır.

> [!NOTE]
> Bir çakışma neden olacağından, zaten bir ad kullanırsanız **yeniden adlandırma** IDE'yi kutusunda sizi uyaracaktır.
>
> ![Çakışma yeniden adlandırma](media/rename-conflict-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)