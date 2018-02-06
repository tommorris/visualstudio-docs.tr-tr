---
title: "XML belgeleri yorumları - kod oluşturma (C#) oluştur | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2025bd2-5984-4486-a61c-0a0933a735ea
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: b0a0ec1db54f57e14ddd412248f7a396336fe009
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="generate-xml-documentation-comments-in-c"></a>XML belgeleri yorumları C# ' ta oluştur #
**Ne:** hemen XML seçilen öğeyi belge için gerekli temel oluşturmanıza olanak sağlar. 

**Ne zaman:** Sandcastle gibi bir belge araç tarafından daha sonra işlenmek üzere XML belge açıklamaları oluşturmak istediğiniz.

**Neden:** ancak bu zamandan ve temel şablonu ve ek öğeler oluşturarak doğruluğunu artırmak el ile tüm açıklama bloğu kendiniz oluşturabilirsiniz. 

**Nasıl:**

1. Metin imlecinizi belge, örneğin, bir yöntem istediğiniz öğenin üstüne getirin.

   ![Belgeye yöntemi](media/doc-highlight-cs.png)

1. Sonra aşağıdakileri yazın  **///**  (3 İleri Yatık çizgi), temel şablonu ve ek öğeleri gerektiğinde otomatik olarak oluşturur.  Bir yöntem Yorum olduğunda, örneğin, üretecektir  **\<Özet\>**  etiketleri yanı sıra bir  **\<param\>**  olan her parametre için etiketi yönteme geçirilen ve  **\<döndürür\>**  ne yöntemi döndürür belge etiketi.

   ![Şablon](media/doc-preview-cs.png)

1. Açıklamaları tamamlayın ve düşündüğünüz herhangi bir ek bilgi gereklidir ekleyin.

   ![Tamamlanan açıklama](media/doc-result-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

[Kod Oluşturma](../code-generation-in-visual-studio.md)  
[XML belgeleri yorumları (C# programlama Kılavuzu)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
