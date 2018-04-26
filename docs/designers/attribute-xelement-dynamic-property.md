---
title: Öznitelik (XElement dinamik özellik)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9ac173785804ce2ed2874b9628c68d3ab78be6e1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="attribute-xelement-dynamic-property"></a>Öznitelik (XElement dinamik özellik)

Belirtilen genişletilmiş adına karşılık gelen öznitelik örneği almak için kullanılan bir dizin oluşturucu alır.

## <a name="syntax"></a>Sözdizimi

```
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Bir dizin oluşturucu türü `XAttribute Item(String expandedName)`. Bu dizin oluşturucu genişletilmiş belirtilen özniteliğin adını alır ve karşılık gelen döndürür <xref:System.Xml.Linq.XAttribute>, veya `null` hiçbir öznitelik belirtilen ada sahip.

## <a name="remarks"></a>Açıklamalar

Bu özellik eşdeğerdir <xref:System.Xml.Linq.XElement.Attribute%2A> yöntemi <xref:System.Xml.Linq.XElement?displayProperty=fullName> sınıfı.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [XElement Sınıfı Dinamik Özellikleri](../designers/xelement-class-dynamic-properties.md)
- [Değer](../designers/value-xattribute-dynamic-property.md)