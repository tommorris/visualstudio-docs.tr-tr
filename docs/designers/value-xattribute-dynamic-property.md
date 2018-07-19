---
title: Değer (XAttribute dinamik özelliği)
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
ms.openlocfilehash: 6c31179d33467f6be440882bce6f6cd9559d9a00
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080830"
---
# <a name="value-xattribute-dynamic-property"></a>Değer (XAttribute dinamik özelliği)

Alır veya XML öznitelik değerini ayarlar.

## <a name="syntax"></a>Sözdizimi

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>Özellik değeri/dönüş değeri

A <xref:System.String> içeren bu özniteliğin değeri.

## <a name="exceptions"></a>Özel Durumlar

|Özel durum türü|Koşul|
|--------------------|---------------|
|<xref:System.ArgumentNullException>|Ayarlarken `value` olduğu `null`.|

## <a name="remarks"></a>Açıklamalar

Bu özellik değerine eşdeğer olan <xref:System.Xml.Linq.XAttribute.Value%2A> özelliği <xref:System.Xml.Linq.XAttribute?displayProperty=fullName> sınıfı, ancak bu dinamik özellik de değişiklik bildirimleri destekler.

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [XAttribute sınıfı dinamik özellikleri](../designers/xattribute-class-dynamic-properties.md)
- [Özniteliği](../designers/attribute-xelement-dynamic-property.md)