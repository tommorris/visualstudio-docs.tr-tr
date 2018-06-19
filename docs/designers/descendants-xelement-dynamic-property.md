---
title: Alt öğeleri (XElement dinamik özellik)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7c1b0aa0c55c0da2a6f9af58f5d54ff607a409ce
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31925407"
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