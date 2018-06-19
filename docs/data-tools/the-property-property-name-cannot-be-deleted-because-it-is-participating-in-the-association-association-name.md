---
title: İlişkiye katılan için özellik silinemiyor
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 98f95c489758b808ae7a210f7d83332f84571d1f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924145"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Özellik &lt;özellik adı&gt; ilişkiye katılan olduğundan silinemez &lt;ilişkilendirme adı&gt;

Seçilen özellik olarak ayarlanmış olan **Association özelliği** hata iletisinde belirtilen sınıflar arasındaki bir ilişkilendirme için. Veri sınıfları arasında bir ilişki içinde katılan varsa özellikleri silinemez.

Ayarlama **Association özelliği** istenen özelliği başarıyla silinmesini sağlamak için veri sınıfının farklı bir özellik için.

## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Hata iletisinde belirtilen veri sınıfları bağlayan O/R Tasarımcısı İlişkilendirme satırında seçin.

2. Çizgiyi açmak için çift **ilişkilendirme Düzenleyicisi** iletişim kutusu.

3. Bir özellikten kaldırmak **ilişki özellikleri**.

4. Özellik silmeyi tekrar deneyin.

## <a name="see-also"></a>Ayrıca bkz.

- [O/R Tasarımcısı iletileri](../data-tools/o-r-designer-messages.md)
- [LINQ-SQL Visual Studio Araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)