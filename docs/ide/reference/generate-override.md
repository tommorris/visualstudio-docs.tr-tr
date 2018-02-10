---
title: "Visual Studio'da yöntemi geçersiz kılma oluştur | Microsoft Docs"
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
ms.openlocfilehash: df0eecdeb2aad15e1da68cef3b125c3c95f57e78
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="generate-an-override-in-visual-studio"></a>Visual Studio'da bir geçersiz kılma oluştur

Bu kod oluşturma için geçerlidir:

- C#

- Visual Basic

**Ne:** hemen bir taban sınıftan hangi kılınabilir herhangi bir yöntemini kodunu oluşturmak olanak tanır.

**Ne zaman:** bir temel sınıf yöntemini geçersiz kılın ve imza otomatik olarak oluşturmak istediğiniz.

**Neden:** ancak, bu özellik imza otomatik olarak oluşturur, yöntem imzası kendiniz yazabilirsiniz.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. Tür `override` C# veya `Overrides` Visual Basic'te, ardından olduğu gibi bir geçersiz kılma yöntemi eklemek için bir boşluk.

   - C# ' TA:

    ![Override IntelliSense C#](media/override-intellisense-cs.png)

   - Visual Basic:

    ![Override IntelliSense VB](media/override-intellisense-vb.png)

1. Temel sınıfından geçersiz kılmak istediğiniz yöntemi seçin.

   > [!TIP]
   > - Özellik simgesi kullanın ![Özellik simgesi](media/override-property-cs.png) göstermek veya özellikler listesinde gizlemek için.
   > - Yöntem simgesini kullanın ![Yöntem simgesi](media/override-method-cs.png) göstermek veya gizlemek listesinde yöntemleri için.

   Seçilen yöntemi veya özelliği sınıfa geçersiz kılma uygulanması için hazır eklenir.

   - C# ' TA:

      ![Override result C#](media/override-result-cs.png)

   - Visual Basic:

      ![Sonuç VB geçersiz kıl](media/override-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)
