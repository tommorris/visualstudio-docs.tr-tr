---
title: Değer (XAttribute dinamik özellik) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a0ca01f5d7aec5807343b98a3c402a89678fbe88
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>   
 [Dinamik özellikler XAttribute sınıfı](../designers/xattribute-class-dynamic-properties.md)   
 [Özniteliği](../designers/attribute-xelement-dynamic-property.md)