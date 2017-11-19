---
title: "Bir geçersiz kılma - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d2972cfe2ea4481ab8f5eab6284277615d1d64a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="generate-an-override-in-c"></a>Bir geçersiz kılma C# ' ta oluştur #
**Ne:** hemen kod hangi kılınabilir herhangi bir yöntem için bir taban sınıftan oluşturmanıza olanak sağlar. 

**Ne zaman:** bir temel sınıf yöntemini geçersiz kılın ve imza otomatik olarak oluşturmak istediğiniz.  

**Neden:** ancak, bu özellik imza otomatik olarak oluşturur, yöntem imzası kendiniz yazabilirsiniz. 

**Nasıl:**

1. Tür **geçersiz kılma** burada geçersiz kılınan yöntem imzası eklemek ister misiniz ve IntelliSense açılır listesinde görünür ve bir boşluk, anahtar sözcük.

   ![IntelliSense geçersiz kıl](media/override_intellisense.png)

1. Fareyle tıklatarak veya ona klavye ve tuşlarına basarak gezinme temel sınıfından geçersiz kılmak istediğiniz yöntemi seçin **Enter**.

   >[!TIP]
   >* Özellik simgesi kullanın ![Özellik simgesi](media/override_property.png) göstermek veya özellikler listesinde gizlemek için.
   >* Yöntem simgesini kullanın ![Özellik simgesi](media/override_method.png) göstermek veya listede yöntemleri gizlemek için.

1. Seçilen yöntemi veya özelliği geçersiz kılma uygulanması için hazır sınıfa eklenir.

   ![Sonuç geçersiz kıl](media/override_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (C#)](../code-generation-csharp.md)  
