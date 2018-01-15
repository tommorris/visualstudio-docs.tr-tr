---
title: "Visual Basic'te bir özellik için bir alan yeniden düzenlemeniz | Microsoft Docs"
ms.custom: 
ms.date: 12/14/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.encapsulatefield
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 010a297745ed6028f7ee127fffc210097d6d26f5
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="encapsulate-a-field-in-visual-basic"></a>Visual Basic'te bir alanı Yalıt

**Ne:** bir alan bir özellikte açın ve yeni oluşturulan özelliği kullanmak için bu alanın tüm kullanımları güncelleştirmenize olanak sağlar.

**Ne zaman:** bir özellikte alandan ve bu alan için tüm başvuruları güncelleştirmek istiyor.  

**Neden:** bir alana diğer sınıflar erişim vermek istediğiniz, ancak doğrudan erişim sağlamak için bu sınıfların istemezsiniz.  Bir özellik alanında kaydırma tarafından örneğin atanmasına değerini doğrulamak için kod yazabilirsiniz.

**Nasıl:**

1. Vurgula veya metin imleci kapsülleyen alanın adını içinde:

   ![Vurgulanmış kodu](media/encapsulate-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + E**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünü seçin **yalıtma alan** girişi önizleme penceresi açılır.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > alanı Yalıt**.
     * Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünü seçin **yalıtma alan** girişi önizleme penceresi açılır.

   Seçim | Açıklama
   --------- | -----------
   **Alanı Yalıt (ve özelliğini kullanın)** | Bir özellik alanıyla yalıtır ve oluşturulan özelliği kullanmak için alanının tüm kullanımları güncelleştirir
   **Alanı Yalıt (ancak hala alanını kullanın)** | Bir özellik alanıyla saklar, ancak alanının tüm kullanımları dokunulmadan bırakır

   Özellik hemen oluşturulur ve alan başvuruları, seçili güncelleştirilecektir.

   > [!TIP]
   > Kullanım [ **Önizleme değişiklikleri** ](../../ide/preview-changes.md) sonucu kaydetmeden önce olacağını görmek için açılan penceredeki bağlantı.

   ![Özellik sonuç yalıtma](media/encapsulate-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)