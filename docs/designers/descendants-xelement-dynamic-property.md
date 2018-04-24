---
title: Alt öğeleri (XElement dinamik özellik)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 76b08f4521182c8b50f0ca5f527068d7c97bd425
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="descendants-xelement-dynamic-property"></a>Alt öğeleri (XElement dinamik özellik)

Belirtilen genişletilmiş adı ile eşleşen tüm alt öğeleri geçerli öğenin almak için kullanılan bir dizin oluşturucu alır.

## <a name="syntax"></a>Sözdizimi

```
elem.Descendants[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bir dizin oluşturucu türü `IEnumerable<XElement> Item(String expandedName)`. Bu dizin oluşturucu genişletilmiş adının belirtilen alt öğelerinin alıp eşleşen alt öğeleri döndüren bir <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` koleksiyonu.

## <a name="remarks"></a>Açıklamalar

Bu özellik eşdeğerdir <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> yöntemi <xref:System.Xml.Linq.XContainer> sınıfı.

Döndürülen koleksiyonundaki XML kaynak belge düzeninde öğelerdir.

Bu özellik, ertelenmiş yürütme kullanır.

## <a name="see-also"></a>Ayrıca bkz.

- [XElement Sınıfı Dinamik Özellikleri](../designers/xelement-class-dynamic-properties.md)
- [Elements](../designers/elements-xelement-dynamic-property.md)