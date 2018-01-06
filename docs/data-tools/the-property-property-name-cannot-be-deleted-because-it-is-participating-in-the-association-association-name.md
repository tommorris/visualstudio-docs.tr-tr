---
title: "Özellik &lt;özellik adı&gt; ilişkiye katılan olduğundan silinemez &lt;ilişkilendirme adı&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 44a83e15cd712fb98c697b68b1dccaea5d0caf99
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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