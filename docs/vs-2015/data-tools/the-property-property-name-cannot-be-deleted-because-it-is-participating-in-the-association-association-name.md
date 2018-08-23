---
title: Özellik &lt;özellik adı&gt; ilişkilendirmesine katıldığından silinemiyor &lt;ilişkilendirme adı&gt; | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6983d52615219c386b049eea33f9f911956c6d59
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684238"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Özellik &lt;özellik adı&gt; ilişkilendirmesine katıldığından silinemiyor &lt;ilişkilendirme adı&gt;
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [özelliği &lt;özellik adı&gt; ilişkilendirmesine katıldığından silinemiyor &lt;ilişkilendirme adı&gt;](https://docs.microsoft.com/visualstudio/data-tools/the-property-property-name-cannot-be-deleted-because-it-is-participating-in-the-association-association-name).  
  
  
Seçilen özellik olarak ayarlandığından **ilişkilendirme** hata iletisinde belirtilen sınıfları arasında ilişkilendirme için. Veri sınıfları arasında ilişkilendirme katılan varsa özellikleri silinemez.  
  
 Ayarlama **ilişkilendirme** başarılı silinmesini istenen özelliği etkinleştirmek için veri sınıfın farklı bir özellik için.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Hata iletisinde belirtilen veri sınıfları bağlanan O/R Tasarımcısı'ndaki ilişkilendirme çizgisi seçin.  
  
2.  Satırı açmak için çift tıklatın **ilişkilendirme Düzenleyicisi** iletişim kutusu.  
  
3.  Özelliğinden kaldırılacak **ilişkilendirme özellikleri**.  
  
4.  Özelliği yeniden silmeyi deneyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ to SQL araçlarını Visual Studio'da](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Nasıl yapılır: LINQ to SQL sınıfları (O/R Tasarımcısı) arasında bir ilişki (ilişki) oluşturun](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [İzlenecek yol: LINQ to SQL sınıfları (O R Designer) oluşturma](http://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](http://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)

