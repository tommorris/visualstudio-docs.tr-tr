---
title: "Ayıklama yöntemi Visual Basic'te | Microsoft Docs"
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
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: f9e55a41f9a61626e8fce18cb11da6edc8a8bced
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="extract-a-method-in-visual-basic"></a>Visual Basic'te bir yöntemi

**Ne:** kendi yönteminin içine kod parçacığını kapatmanızı sağlar.

**Ne zaman:** başka bir yönteminden çağrılması gereken bazı yöntemi var olan kod parçacığını sahip.  

**Neden:** , kopyalayıp bu kodu yapıştırın, ancak çoğaltma için neden.  Bu parça, başka bir yöntemle serbestçe çağrılabilir kendi yöntemiyle yeniden düzenlemeniz daha iyi bir çözümdür.

**Nasıl:**

1. Ayıklanacak kod vurgula:

   ![Vurgulanmış kodu](media/extractmethod-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:
   * **Klavye**
     * Tuşuna **Ctrl + R**, ardından **Ctrl + M**.  (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     * Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ayıklama yöntemi** gelen önizleme penceresi açılır.
   * **Fare**
     * Seçin **Düzenle > yeniden düzenlemeniz > ayıklamak yöntemi**.
     * Kod sağ tıklatıp **yeniden düzenlemeniz > ayıklamak > ayıklama yöntemi**.
     * Kodu sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **ayıklama yöntemi** gelen önizleme penceresi açılır.

   Yöntem hemen oluşturulur.  Buradan, yeni bir ad yazarak şimdi yöntemi adlandırabilirsiniz.

   > [!TIP]
   > Ayrıca açıklamaları ve bu yeni ad kullanmak üzere diğer dizeleri güncelleştirebilirsiniz yanı [Önizleme değişiklikleri](../../ide/preview-changes.md) önce kaydetme, içinde onay kutularını kullanarak **yeniden adlandırmak** üstünde görünür kutusunu IDE'yi sağında.

   ![Yöntem yeniden adlandırma](media/extractmethod-rename-vb.png)

1. Değişiklikle memnun kaldığınızda, tıklatın **Uygula** düğmesini veya tuşuna **Enter** ve değişiklikler uygulanır.

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)  
[Değişiklikleri Önizleme](../../ide/preview-changes.md)