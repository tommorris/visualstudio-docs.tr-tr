---
title: "Bir geçersiz kılma - kod oluşturma (Visual Basic) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c8cfc4-7c1f-4606-970e-3f7651604bab
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 4a384eb3e75a499eb2a35c747f003846580738e9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-an-override-in-visual-basic"></a>Visual Basic'te bir geçersiz kılma oluştur
**Ne:** hemen kod hangi kılınabilir herhangi bir yöntem için bir taban sınıftan oluşturmanıza olanak sağlar. 

**Ne zaman:** bir temel sınıf yöntemini geçersiz kılın ve imza otomatik olarak oluşturmak istediğiniz.  

**Neden:** ancak, bu özellik imza otomatik olarak oluşturur, yöntem imzası kendiniz yazabilirsiniz. 

**Nasıl:**

1. Tür **geçersiz kılmaları** burada geçersiz kılınan yöntem imzası eklemek ister misiniz ve IntelliSense açılır listesinde görünür ve bir boşluk, anahtar sözcük.

   ![IntelliSense geçersiz kıl](media/override_intellisense.png)

1. Fareyle tıklatarak veya ona klavye ve tuşlarına basarak gezinme temel sınıfından geçersiz kılmak istediğiniz yöntemi seçin **Enter**.

<!--
   >[!TIP]
   >* Use the Property icon ![Property icon](media/override_property.png) to show or hide  Properties in the list.
   >* Use the Method icon ![Property icon](media/override_method.png) to show or hide Methods in the list.
-->

1. Seçilen yöntemi veya özelliği geçersiz kılma uygulanması için hazır sınıfa eklenir.

   ![Sonuç geçersiz kıl](media/override_result.png)

## <a name="see-also"></a>Ayrıca Bkz.  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md) 