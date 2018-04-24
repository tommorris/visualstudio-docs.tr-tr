---
title: Öznitelik (XElement dinamik özellik)
ms.date: 11/04/2016
ms.technology: vs-ide-designers
ms.topic: reference
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9378a7649a3e99a0327586ab2e9f7234b66615f4
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
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