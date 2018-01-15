---
title: "Visual Basic'te bir yöntem imzası yeniden düzenlemeniz | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: daee27902bd602dfe1d67533ce45f42f44a3aba4
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="change-a-method-signature-in-visual-basic"></a>Visual Basic'te bir yöntem imzası değiştirme

**Ne:** kaldırın ya da bir yöntemin parametre sırasını değiştirme imkan tanır.

**Ne zaman:** taşımak veya çeşitli konumlara kullanılmakta olan bir yöntem parametresi kaldırmak istediğiniz.  

**Neden:** el ile kaldırın ve parametreleri yeniden Sırala sonra bu yöntem tüm çağrıları bulmak ve bunları tek tek değiştirmek, ancak hatalarına neden olabilir.  Bu yeniden düzenleme aracı görevi otomatik olarak gerçekleştirir.

**Nasıl:**

1. Vurgula veya metin imleci değiştirmek için yöntemi veya kendi kullanımlarından adını içinde:

   ![Vurgulanmış kodu](media/changesignature-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + V**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **değişiklik imza** gelen önizleme penceresi açılır.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > kaldırmak parametreleri**.
     * Seçin **Düzenle > yeniden düzenlemeniz > parametreleri yeniden Sırala**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **değişiklik imza** gelen önizleme penceresi açılır.

1. İçinde **değiştirmek imza** , POP iletişim yöntemini imza değiştirmek için sağ tarafta düğmeleri kullanabilirsiniz:

   ![İmza iletişim değiştirme](media/changesignature-dialog-vb.png)

   | Düğme | Açıklama
   | ------ | ---
   | **Yukarı/Aşağı** | Seçilen parametre listesi yukarı ve Aşağı Taşı
   | **Kaldır**  | Seçili parametreyi listeden kaldırın
   | **Geri yükleme** | Seçili, çizilmiş parametre listesine geri yükleme

   > [!TIP]
   > Kullanım [ **başvuru değişikliklerini Önizleme** ](../../ide/preview-changes.md) sonucu kaydetmeden önce olacağını görmek için onay kutusunu.

1. İşiniz bittiğinde, basın **Tamam** değişiklik yapmak için düğmesi.

   ![İmza sonuç değiştirme](media/changesignature-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)