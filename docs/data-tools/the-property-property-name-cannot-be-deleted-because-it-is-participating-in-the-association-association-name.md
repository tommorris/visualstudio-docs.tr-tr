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
ms.openlocfilehash: 150d176c105e8368fc97f36a19774824dcb91c3e
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
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