---
title: Öğe (XElement dinamik özellik)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0bdcb6f4524f4f2db7f119319cbb38a09f83f201
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="element-xelement-dynamic-property"></a>Öğe (XElement dinamik özellik)

Alt almak için kullanılan bir dizin oluşturucu, belirtilen Genişletilmiş adına karşılık gelen öğe örneğini alır.

## <a name="syntax"></a>Sözdizimi

```
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bir dizin oluşturucu türü `XElement Item(String expandedName)`. Bu dizin oluşturucu genişletilmiş name parametresi alır ve karşılık gelen döndürür <xref:System.Xml.Linq.XElement>, veya `null` belirtilen ada sahip herhangi bir öğe varsa.

## <a name="remarks"></a>Açıklamalar

Bu özellik eşdeğerdir <xref:System.Xml.Linq.XContainer.Element%2A> yöntemi <xref:System.Xml.Linq.XContainer?displayProperty=fullName> sınıfı.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [XElement Sınıfı Dinamik Özellikleri](../designers/xelement-class-dynamic-properties.md)
- [Elements](../designers/elements-xelement-dynamic-property.md)