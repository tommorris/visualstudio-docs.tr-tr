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
ms.openlocfilehash: 1bf34acffb037369458aa4a86a5ecf629f127004
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="generate-xml-documentation-comments-in-c"></a>XML belgeleri yorumları C# ' ta oluştur #
**Ne:** hemen XML seçilen öğeyi belge için gerekli temel oluşturmanıza olanak sağlar. 

**Ne zaman:** Sandcastle gibi bir belge araç tarafından daha sonra işlenmek üzere XML belge açıklamaları oluşturmak istediğiniz.

**Neden:** ancak bu zamandan ve temel şablonu ve ek öğeler oluşturarak doğruluğunu artırmak el ile tüm açıklama bloğu kendiniz oluşturabilirsiniz. 

**Nasıl:**

1. Metin imlecinizi belge, örneğin, bir yöntem istediğiniz öğenin üstüne getirin.

   ![Belgeye yöntemi](media/doc_highlight.png)

1. Sonra aşağıdakileri yazın  **///**  (3 İleri Yatık çizgi), temel şablonu ve ek öğeleri gerektiğinde otomatik olarak oluşturur.  Bir yöntem Yorum olduğunda, örneğin, üretecektir  **\<Özet\>**  etiketleri yanı sıra bir  **\<param\>**  olan her parametre için etiketi yönteme geçirilen ve  **\<döndürür\>**  ne yöntemi döndürür belge etiketi.

   ![Şablon](media/doc_preview.png)

1. Açıklamaları tamamlayın ve düşündüğünüz herhangi bir ek bilgi gereklidir ekleyin.

   ![Tamamlanan açıklama](media/doc_result.png)

## <a name="see-also"></a>Ayrıca Bkz.
[Kod oluşturma (C#)](../code-generation-csharp.md)  
[XML belgeleri yorumları (C# programlama Kılavuzu)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
