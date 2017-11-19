---
title: "Öznitelik (XElement dinamik özellik) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0fd01945c2a33f3929f59e66a02a1d08a39c3cc7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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