---
title: Özellik &lt;özellik adı&gt; ilişkiye katılan olduğundan silinemez &lt;ilişkilendirme adı&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5121d79e6db6bdef1deb0ee04540295b2a109f72
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Özellik &lt;özellik adı&gt; ilişkiye katılan olduğundan silinemez &lt;ilişkilendirme adı&gt;
Seçilen özellik olarak ayarlanmış olan **Association özelliği** hata iletisinde belirtilen sınıflar arasındaki bir ilişkilendirme için. Veri sınıfları arasında bir ilişki içinde katılan varsa özellikleri silinemez.  
  
 Ayarlama **Association özelliği** istenen özelliği başarıyla silinmesini sağlamak için veri sınıfının farklı bir özellik için.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Hata iletisinde belirtilen veri sınıfları bağlayan O/R Tasarımcısı İlişkilendirme satırında seçin.  
  
2.  Çizgiyi açmak için çift **ilişkilendirme Düzenleyicisi** iletişim kutusu.  
  
3.  Bir özellikten kaldırmak **ilişki özellikleri**.  
  
4.  Özellik silmeyi tekrar deneyin.  
  
## <a name="see-also"></a>Ayrıca bkz.
[O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)  
[LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)