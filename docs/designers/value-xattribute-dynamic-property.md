---
title: Değer (XAttribute dinamik özellik)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 19808b10c64b469d3d9191fa2e4fc282d7696c5f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31923597"
---
# <a name="value-xattribute-dynamic-property"></a>Değer (XAttribute dinamik özellik)

Alır veya XML özniteliğinin değerini ayarlar.

## <a name="syntax"></a>Sözdizimi

```
attrib.Value
```

## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

A <xref:System.String> bu öznitelik değerini içeren.

## <a name="exceptions"></a>Özel Durumlar

|Özel durum türü|Koşul|
|--------------------|---------------|
|<xref:System.ArgumentNullException>|Ayarlarken, `value` olan `null`.|

## <a name="remarks"></a>Açıklamalar

Bu özellik eşdeğerdir <xref:System.Xml.Linq.XAttribute.Value%2A> özelliği <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> sınıfı, ancak bu dinamik özellik de değişiklik bildirimleri destekler.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [XAttribute Sınıfı Dinamik Özellikleri](../designers/xattribute-class-dynamic-properties.md)
- [Özniteliği](../designers/attribute-xelement-dynamic-property.md)