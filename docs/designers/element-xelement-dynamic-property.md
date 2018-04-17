---
title: Öğe (XElement dinamik özellik) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 14078873184e4b1068f4eed931105e2e2e29dcfc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>   
 [Dinamik özellikler XElement sınıfı](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)