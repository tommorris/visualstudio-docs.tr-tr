---
title: "Bir arabirim Visual Studio'da yeniden düzenleme ayıklamak | Microsoft Docs"
ms.custom: 
ms.date: 01/26/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords:
- vs.csharp.refactoring.extractinterface
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 451b5ccddf6052eca3ae0a19b87076d2fd88a952
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="extract-an-interface-refactoring"></a>Bir arabirimi yeniden düzenleme Ayıkla

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** üyelerin bir sınıf, yapı ya da arabirimi kullanarak bir arabirim oluşturmanızı sağlar.

**Ne zaman:** çeşitli sınıflar, yapılar veya arabirimler ortak ve diğer sınıflar, yapılar veya arabirimler tarafından kullanılan yapılamadı yöntemleriyle sahip.

**Neden:** nesne odaklı tasarımları için harika yapılar arabirimlerdir. Tüm Eat, içki, uyku gibi yaygın yöntemleri olabilir çeşitli hayvanlar (köpek, kat, kuş) için sınıflar sahip düşünün. IAnimal gibi bir arabirim kullanarak köpek, kat ve kuş ortak bir "imza" Bu yöntemlere ait olmasını olanak tanır.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Yalnızca metin imleci sınıf adında bir yerde put veya eylemi gerçekleştirmek için sınıfı adı vurgulayın.

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/extractinterface-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/extractinterface-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl + R**, ardından **Ctrl + ı**. (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
     - Tuşuna **Ctrl +.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **arayüz** gelen önizleme penceresi açılır.
   - **Fare**
     - Seçin **Düzenle > yeniden düzenlemeniz > ayıklamak arabirimi**.
     - Select sınıfın adını sağ tıklatın **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve seçin **arayüz** gelen önizleme penceresi açılır.

1. İçinde **arayüz** , POP iletişim kutusunun sorulan bilgileri girin:

   ![Ayıklama Arabirimi](media/extractinterface-dialog-cs.png)

   | Alan | Açıklama |
   | --- | --- |
   | **Yeni Arabirim adı** | Oluşturulacak arabirimi adı. Bu t varsayılan*ClassName*, burada *ClassName* Yukarıda seçilen sınıf adı. |
   | **Yeni dosya adı** | Arabirimi içerecek oluşturulacak olan dosya adı. Arabirim adı ile bu t varsayılan olarak*ClassName*, burada *ClassName* Yukarıda seçilen sınıf adı. |
   | **Form arabirimi ortak üyeleri seçin** | Ayıklama arabirimi öğeler. İstediğiniz gibi birçok seçebilirsiniz. |

1. Seçin **Tamam**.

   Arabirim, belirtilen adı dosyasında oluşturulur. Ayrıca, seçtiğiniz sınıfı bu arabirimi uygular.

   - C# ' TA:

    ![Sonuçta elde edilen sınıf:-C#](media/extractinterface-class-cs.png)
    ![elde edilen arabirim - C#](media/extractinterface-interface-cs.png)

   - Visual Basic:

    ![Sonuçta elde edilen sınıf - Visual Basic](media/extractinterface-class-vb.png)
    ![elde edilen arabirim - Visual Basic](media/extractinterface-interface-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Yeniden Düzenleme](../refactoring-in-visual-studio.md)