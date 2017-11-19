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
ms.openlocfilehash: 1291667c7acb47abe543d275549179abea0c8467
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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