---
title: Bir dosya adı Visual Studio'da türüyle eşleşecek şekilde yeniden adlandırın
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 58a4a1647912203fd1415176f4089904f8c70e0f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947475"
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-refactoring"></a>Bir dosya adı ya da yeniden düzenleme türü için bir dosya türüne eşitleme

Bu yeniden düzenleme için geçerlidir:

- C#

- Visual Basic

**Ne:** bir türü filename eşleşecek şekilde yeniden adlandırın ya da bir dosya adı içerdiği türüyle eşleşecek şekilde yeniden adlandırın imkan tanır.

**Ne zaman:** bir dosya veya türü adlandırdınız ve karşılık gelen dosya ya da türü eşleşecek şekilde güncelleştirildi henüz yapmadıysanız.

**Neden:** farklı bir ad ya da tam tersini, onu aradığınızı bulmak zor sahip bir dosya türü yerleştirmekten. Türü ya da dosya yeniden adlandırmadan kodunu daha okunabilir ve gitmek daha kolay olur.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Vurgula veya metin imleci eşitlemek için türünün adı içinde:

   - C# ' TA:

    ![Vurgulanmış kodu - C#](media/synctype-highlight-cs.png)

   - Visual Basic:

    ![Vurgulanmış kodu - Visual Basic](media/synctype-highlight-vb.png)

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **dosyayı yeniden adlandır *TypeName*.cs** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve Seç **yeniden adlandırmak için türü _Filename_**  önizleme penceresi açılan, gelen nerede *Filename* geçerli dosyanın adıdır.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menü ve select **dosyayı yeniden adlandır *TypeName*.cs** önizleme penceresi açılan, gelen nerede *TypeName* seçtiğiniz türünün adı.
     - Kodu sağ tıklayın, **hızlı Eylemler ve yapan yeniden düzenlemeler** menüsünde ' nı seçip **yeniden adlandırmak için türü _Filename_**  önizleme penceresi açılan, gelen nerede  *Dosya adı* geçerli dosyanın adıdır.

   Tür veya dosya yeniden adlandırılır.

   - C# ' ta: Aşağıdaki örnekte, dosyanın **MyClass.cs** yeniden adlandırıldı **MyNewClass.cs** türü adı ile eşleşmesi için.

      ![Satır içi sonuç C#](media/synctype-result-cs.png)

   - Visual Basic: Aşağıdaki örnekte, dosyanın **Employee.vb** yeniden adlandırıldı **Person.vb** türü adı ile eşleşmesi için.

      ![Satır içi sonuç Visual Basic](media/synctype-result-vb.png)

> ! [NOT] Bu yeniden düzenleme henüz .NET standart ve .NET Core projeleri için kullanılabilir değil.

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
