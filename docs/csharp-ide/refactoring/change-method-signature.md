---
title: "Değişiklik yöntemi imza yeniden düzenlemesi (C#) - | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: b4f45f9d-9c8f-46ae-99f7-7705c6d90b6e
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.remove
- vs.csharp.refactoring.reorder
dev_langs: csharp
ms.openlocfilehash: 9ed72704c37fcfc5d0c48ba17937f5b06097ce0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="change-a-method-signature-in-c"></a>C# yöntemi imzayı değiştirme #
**Ne:** kaldırın ya da bir yöntemin parametre sırasını değiştirme imkan tanır.

**Ne zaman:** taşımak veya çeşitli konumlara kullanılmakta olan bir yöntem parametresi kaldırmak istediğiniz.  

**Neden:** el ile kaldırın ve parametreleri yeniden Sırala sonra bu yöntem tüm çağrıları bulmak ve bunları tek tek değiştirmek, ancak hatalarına neden olabilir.  Bu yeniden düzenleme aracı görevi otomatik olarak gerçekleştirir.

**Nasıl:**

1. Vurgula veya metin imleci değiştirmek için yöntemi veya kendi kullanımlarından adını içinde:

   ![Vurgulanmış kodu](media/changesignature_highlight.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + V**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **değişiklik imza** gelen önizleme penceresi açılır.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > kaldırmak parametreleri**.
     * Seçin **Düzenle > yeniden düzenlemeniz > parametreleri yeniden Sırala**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **değişiklik imza** gelen önizleme penceresi açılır.

1. İçinde **değiştirmek imza** , POP iletişim yöntemini imza değiştirmek için sağ tarafta düğmeleri kullanabilirsiniz:

   ![İmza iletişim değiştirme](media/changesignature_dialog.png)

   | Düğme | Açıklama
   | ------ | ---
   | **Yukarı/Aşağı** | Seçilen parametre listesi yukarı ve Aşağı Taşı
   | **Kaldır**  | Seçili parametreyi listeden kaldırın
   | **Geri yükleme** | Seçili, çizilmiş parametre listesine geri yükleme

   > [!TIP]
   > Kullanım [ **başvuru değişikliklerini Önizleme** ](../../ide/preview-changes.md) sonucu kaydetmeden önce olacağını görmek için onay kutusunu.

1. İşiniz bittiğinde, basın **Tamam** değişiklik yapmak için düğmesi.

   ![İmza sonuç değiştirme](media/changesignature_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Yeniden düzenlemesi (C#)](../refactoring-csharp.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)