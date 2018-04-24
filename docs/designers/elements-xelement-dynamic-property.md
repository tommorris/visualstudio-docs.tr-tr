---
title: Öğeleri (XElement dinamik özellik)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 614914b5ff2a71cbca06b957ea381b9926a10574
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="elements-xelement-dynamic-property"></a>Öğeleri (XElement dinamik özellik)

Belirtilen genişletilmiş adı ile eşleşen geçerli öğenin alt öğeleri almak için kullanılan bir dizin oluşturucu alır.

## <a name="syntax"></a>Sözdizimi

```
elem.Elements[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bir dizin oluşturucu türü `IEnumerable<XElement> Item(String expandedName)`. Bu dizin oluşturucu öğeleri istenen alt genişletilmiş adını alır ve eşleşen alt öğeleri döndürür bir <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` koleksiyonu.

## <a name="remarks"></a>Açıklamalar

Bu özellik eşdeğerdir <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> yöntemi <xref:System.Xml.Linq.XContainer> sınıfı.

Döndürülen koleksiyonundaki XML kaynak belge düzeninde öğelerdir.

Bu özellik, ertelenmiş yürütme kullanır.

## <a name="see-also"></a>Ayrıca bkz.

- [XElement Sınıfı Dinamik Özellikleri](../designers/xelement-class-dynamic-properties.md)
- [Öğesi](../designers/element-xelement-dynamic-property.md)
- [Alt öğeleri](../designers/descendants-xelement-dynamic-property.md)