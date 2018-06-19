---
title: Visual Studio'da yeniden adlandırma yeniden Düzenle
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 696ec34bb0009b9b09b5902a102c71cf1331f320
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945460"
---
# <a name="rename-a-code-symbol-refactoring"></a>Bir kod simgesi yeniden düzenleme yeniden adlandırma

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** alanları, yerel değişkenleri, yöntemleri, ad alanları, özellikleri ve türleri gibi kodu sembolleri tanımlayıcıları yeniden adlandır olanak sağlar.

**Ne zaman:** güvenli bir şekilde bir şey tüm örneklerini bulun ve yeni bir ad kopyala/yapıştır zorunda kalmadan yeniden adlandırmak istediğiniz.

**Neden:** Kopyala ve yeni bir ad arasında projenin tamamında yapıştırma misiniz olasılıkla neden hatalar. Bu yeniden düzenleme aracı doğru bir şekilde yeniden adlandırma eylemi gerçekleştirir.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci yeniden adlandırılacak öğesi içinde:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/rename-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/rename-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl + R**, ardından **Ctrl + R**. (Bağlı olarak hangi profilinde seçtiğiniz klavye kısayolu farklı olabileceğini unutmayın.)
   - **Fare**
     - Seçin **Düzenle > yeniden düzenlemeniz > yeniden adlandırma**.
     - Kod sağ tıklatıp **yeniden adlandırma**.

1. Öğeyi yeni bir ad yazarak yeniden adlandırın.

   - C# ' TA:

    ![Animasyon - C# yeniden adlandırma](media/rename-animated-cs.gif)

   - Visual Basic:

    ![Rename - VB](media/rename-rename-vb.png)

   > [!TIP]
   > Ayrıca açıklamaları ve bu yeni ad kullanmak üzere diğer dizeleri güncelleştirebilirsiniz yanı [Önizleme değişiklikleri](../../ide/preview-changes.md) önce kaydetme, içinde onay kutularını kullanarak **yeniden adlandırmak** üstünde görünür kutusunu düzenleyicinizi sağında.

1. Değişiklikle memnun kaldığınızda, seçin **Uygula** düğmesini veya tuşuna **Enter** ve değişiklikler uygulanır.

> [!NOTE]
> Bir çakışma neden olacağından, zaten bir ad kullanırsanız **yeniden adlandırma** kutusu sizi uyaracaktır.
>
> ![Çakışma yeniden adlandırma](media/rename-conflict-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)
