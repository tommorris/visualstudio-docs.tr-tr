---
title: Visual Studio'da yöntemi geçersiz kılma oluştur | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e5900872ab034daa24a28b8b97d96bbb736ae6e3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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

    ![IntelliSense C# geçersiz kıl](media/override-intellisense-cs.png)

   - Visual Basic:

    ![IntelliSense VB geçersiz kıl](media/override-intellisense-vb.png)

1. Temel sınıfından geçersiz kılmak istediğiniz yöntemi seçin.

   > [!TIP]
   > - Özellik simgesi kullanın ![Özellik simgesi](media/override-property-cs.png) göstermek veya özellikler listesinde gizlemek için.
   > - Yöntem simgesini kullanın ![Yöntem simgesi](media/override-method-cs.png) göstermek veya gizlemek listesinde yöntemleri için.

   Seçilen yöntemi veya özelliği sınıfa geçersiz kılma uygulanması için hazır eklenir.

   - C# ' TA:

      ![Sonuç C# geçersiz kıl](media/override-result-cs.png)

   - Visual Basic:

      ![Sonuç VB geçersiz kıl](media/override-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)
