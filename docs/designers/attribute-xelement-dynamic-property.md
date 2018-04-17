---
title: Öznitelik (XElement dinamik özellik) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: be9be11767e57123e7c06ea736608bf58396bce4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>   
 [Dinamik özellikler XElement sınıfı](../designers/xelement-class-dynamic-properties.md)   
 [Değer](../designers/value-xattribute-dynamic-property.md)