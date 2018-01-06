---
title: "XML belgeleri yorumları - kod oluşturma (Visual Basic) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f975fa077fe64052b54875b07d029ece71e83372
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>Visual Basic'te XML belgeleri yorumları oluştur
**Ne:** hemen XML seçilen öğeyi belge için gerekli temel oluşturmanıza olanak sağlar. 

**Ne zaman:** Sandcastle gibi bir belge araç tarafından daha sonra işlenmek üzere XML belge açıklamaları oluşturmak istediğiniz.

**Neden:** ancak bu zamandan ve temel şablonu ve ek öğeler oluşturarak doğruluğunu artırmak el ile tüm açıklama bloğu kendiniz oluşturabilirsiniz. 

**Nasıl:**

1. Metin imlecinizi belge, örneğin, bir yöntem istediğiniz öğenin üstüne getirin.

   ![Belgeye yöntemi](media/doc_highlight.png)

1. Sonra aşağıdakileri yazın **'''** (3 tek tırnak), otomatik olarak oluşturacak temel şablonu ve ek öğeleri gerektiği gibi.  Bir yöntem Yorum olduğunda, örneğin, üretecektir  **\<Özet\>**  etiketleri yanı sıra bir  **\<param\>**  olan her parametre için etiketi yönteme geçirilen ve  **\<döndürür\>**  ne yöntemi döndürür belge etiketi.

   ![Şablon](media/doc_preview.png)

1. Açıklamaları tamamlayın ve düşündüğünüz herhangi bir ek bilgi gereklidir ekleyin.

   ![Tamamlanan açıklama](media/doc_result.png)

## <a name="see-also"></a>Ayrıca Bkz.
[(Visual Basic) XML ile kodunuzu belgeleme](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[Kod oluşturma (Visual Basic)](../code-generation-vb.md) 