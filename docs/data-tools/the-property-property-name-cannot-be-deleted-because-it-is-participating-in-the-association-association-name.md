---
title: İlişkiye katılan için özellik silinemiyor
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9e65049ae881ff11cd647fe09df3a6919dd8818c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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