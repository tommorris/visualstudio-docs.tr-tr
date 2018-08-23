---
title: Öznitelik (XElement dinamik özelliği) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8440fc7d-b3b4-4726-8ec8-492e6af79642
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 750e84a386360880cf30e76fc0157145820c654c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684415"
---
# <a name="attribute-xelement-dynamic-property"></a>Öznitelik (XElement dinamik özelliği)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [öznitelik (XElement dinamik özelliği)](https://docs.microsoft.com/visualstudio/designers/attribute-xelement-dynamic-property).  
  
Belirtilen genişletilmiş adı için karşılık gelen öznitelik örneği almak için kullanılan bir dizin oluşturucuyu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
elem.Attribute[{namespaceName}attribName]  
```  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bir dizin oluşturucu türü `XAttribute Item(String expandedName)`. Bu dizin oluşturucu, belirtilen öznitelik genişletilmiş adını alır ve buna karşılık gelen döndürür <xref:System.Xml.Linq.XAttribute>, veya `null` varsa belirtilen ada sahip bir öznitelik yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik değerine eşdeğer olan <xref:System.Xml.Linq.XElement.Attribute%2A> yöntemi <xref:System.Xml.Linq.XElement?displayProperty=fullName> sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>   
 [XElement sınıfı dinamik özellikleri](../designers/xelement-class-dynamic-properties.md)   
 [Değer](../designers/value-xattribute-dynamic-property.md)



