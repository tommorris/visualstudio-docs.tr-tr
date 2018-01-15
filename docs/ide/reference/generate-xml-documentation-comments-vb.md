---
title: "Visual Basic for XML belgeleri yorumları oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2f421553657dfafb265140e44e38a2c7722a7303
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-xml-documentation-comments-in-visual-basic"></a>Visual Basic'te XML belgeleri yorumları oluştur

**Ne:** hemen XML seçilen öğeyi belge için gerekli temel oluşturmanıza olanak sağlar. 

**Ne zaman:** Sandcastle gibi bir belge araç tarafından daha sonra işlenmek üzere XML belge açıklamaları oluşturmak istediğiniz.

**Neden:** ancak bu zamandan ve temel şablonu ve ek öğeler oluşturarak doğruluğunu artırmak el ile tüm açıklama bloğu kendiniz oluşturabilirsiniz. 

**Nasıl:**

1. Metin imlecinizi belge, örneğin, bir yöntem istediğiniz öğenin üstüne getirin.

   ![Belgeye yöntemi](media/doc-highlight-vb.png)

1. Sonra aşağıdakileri yazın **'''** (3 tek tırnak), otomatik olarak oluşturacak temel şablonu ve ek öğeleri gerektiği gibi.  Bir yöntem Yorum olduğunda, örneğin, üretecektir  **\<Özet\>**  etiketleri yanı sıra bir  **\<param\>**  olan her parametre için etiketi yönteme geçirilen ve  **\<döndürür\>**  ne yöntemi döndürür belge etiketi.

   ![Şablon](media/doc-preview-vb.png)

1. Açıklamaları tamamlayın ve düşündüğünüz herhangi bir ek bilgi gereklidir ekleyin.

   ![Tamamlanan açıklama](media/doc-result-vb.png)

## <a name="see-also"></a>Ayrıca bkz.

[(Visual Basic) XML ile kodunuzu belgeleme](/dotnet/visual-basic/programming-guide/program-structure/documenting-your-code-with-xml)  
[Kod Oluşturma](../code-generation-in-visual-studio.md)