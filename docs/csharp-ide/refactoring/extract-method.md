---
title: "Ayıklama yöntemi yeniden düzenlemesi (C#) - | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: csharp
ms.openlocfilehash: 3890d427ed2888647675a241f4e62a5635d7308c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="extract-a-method-in-c"></a>C# yöntemi #
**Ne:** kendi yönteminin içine kod parçacığını kapatmanızı sağlar.

**Ne zaman:** başka bir yönteminden çağrılması gereken bazı yöntemi var olan kod parçacığını sahip.  

**Neden:** , kopyalayıp bu kodu yapıştırın, ancak çoğaltma için neden.  Bu parça, başka bir yöntemle serbestçe çağrılabilir kendi yöntemiyle yeniden düzenlemeniz daha iyi bir çözümdür.

**Nasıl:**

1. Ayıklanacak kod vurgula:

   ![Vurgulanmış kodu](media/extractmethod_highlight.png)

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

   ![Yöntem yeniden adlandırma](media/extractmethod_rename.png)

1. Değişiklikle memnun kaldığınızda, tıklatın **Uygula** düğmesini veya tuşuna **Enter** ve değişiklikler uygulanır.

## <a name="see-also"></a>Ayrıca Bkz.  
[Yeniden düzenlemesi (C#)](../refactoring-csharp.md)  
[Önizleme değişiklikleri](../../ide/preview-changes.md)