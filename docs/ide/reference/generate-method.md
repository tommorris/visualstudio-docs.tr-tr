---
title: "Visual Studio'da bir yöntem oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 29405c25e404d0183409fc00b7107888dba23541
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
---
# <a name="generate-a-method-in-visual-studio"></a>Visual Studio'da bir yöntem oluşturma

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen bir yöntem bir sınıfa eklemenizi sağlar.

**Ne zaman:** yeni bir yöntem ve düzgün bir şekilde, otomatik olarak bildirmek istiyor.

**Neden:** ancak, bu özellik bildirimi otomatik olarak oluşturur, yöntemi ve parametreleri, kullanmadan önce bildirebilirsiniz.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi satıra yerleştirin kırmızı dalgalı olduğu. Kırmızı dalgalı henüz mevcut olmayan bir yöntemi gösterir.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/method-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/method-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - Kırmızı dalgalı getirin ve'ı tıklatın ![Ampul](media/bulb-cs.png) görüntülenen simge.
     - ' I tıklatın ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

    ![Yöntem Önizleme oluşturma](media/method-preview-cs.png)

1. Seçin **üretme yöntemi** açılır menüsünden.

   > [!TIP]
   > Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.

   Yöntemi, kullanımdan çıkarımı yapılan herhangi bir parametre ile oluşturulur.

   - C# ' TA:

      ![Yöntem sonuç C# oluştur](media/method-result-cs.png)

   - Visual Basic:

      ![Yöntem sonuç VB oluştur](media/method-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)
