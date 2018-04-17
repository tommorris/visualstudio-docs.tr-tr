---
title: Visual Studio'da yerel bir değişken tanıtmak | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: b7af958e923c6af7929b8e4a9309c210dbf8ced5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="introduce-a-local-variable-in-visual-studio"></a>Visual Studio'da yerel bir değişken tanıtır

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen var olan bir ifade değiştirmek için yerel bir değişken oluşturmanıza olanak sağlar.

**Ne zaman:** yerel bir değişkende olsaydı, kolayca daha sonra yeniden koduna sahip.

**Neden:** kopyalayın ve yerel değişken throughought kullanın, bir yerel değişkende sonucu depolamak ve bir kez işlemi gerçekleştirmek daha iyi ancak kodu çeşitli yerlerde kullanmak için birden çok kez yapıştırın.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Yeni yerel bir değişkene atamak istediğiniz ifade vurgulayın.

   - C# ' TA:

    ![Vurgulanmış kodu C#](media/local-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu VB](media/local-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
   - **Fare**
     - Sağ tıklatıp **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsü.
     - &nbsp; ![Ampul](media/bulb-cs.png) metin imleci kırmızı dalgalı satırıyla açıksa sol kenar boşluğunda görüntülenen simgesine.

   ![Yerel Önizleme tanıtır](media/local-preview-cs.png)

1. Seçin **(tüm oluşumları için) yerel tanıtmak '*ifade*'** açılır menüsünden.

   > [!TIP]
   > Kullanım **Önizleme değişiklikleri** önizleme penceresinin altındaki bağlantıyı [tüm değişiklikleri görmek için](../../ide/preview-changes.md) , oluşturulacak seçiminizi yaptıktan önce.

   Kendi kullanımdan çıkarımı yapılan tür yerel değişken oluşturulur. Yeni yerel değişken yeni bir ad verin.

   - C# ' TA:

      ![Uygulama arabirimi sonuç C#](media/local-result-cs.png)

   - Visual Basic:

      ![Uygulama arabirimi sonuç VB](media/local-result-vb.png)

   > [!NOTE]
   > Kullanabileceğiniz **.. olan örnek...**  her seçili ifadesi, yalnızca özellikle vurgulanmış bir örneğini değiştirmek için menü seçeneği.

## <a name="see-also"></a>Ayrıca bkz.

- [Kod Oluşturma](../code-generation-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)
