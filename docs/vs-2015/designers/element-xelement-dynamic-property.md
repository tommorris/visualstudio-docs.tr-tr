---
title: Öğe (XElement dinamik özelliği) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
api_name:
- XElement.Element
api_type:
- Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 56689506db04ee2aedd484093506db4a4fc7453d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691347"
---
# <a name="element-xelement-dynamic-property"></a>Öğe (XElement dinamik özelliği)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [öğe (XElement dinamik özelliği)](https://docs.microsoft.com/visualstudio/designers/element-xelement-dynamic-property).  
  
Alt almak için kullanılan bir dizin oluşturucu, belirtilen Genişletilmiş adı için karşılık gelen öğe örneğini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
elem.Element[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bir dizin oluşturucu türü `XElement Item(String expandedName)`. Bu dizin oluşturucu genişletilmiş adı bir parametre alır ve buna karşılık gelen döndürür <xref:System.Xml.Linq.XElement>, veya `null` varsa belirtilen ada sahip bir öğe yok.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik değerine eşdeğer olan <xref:System.Xml.Linq.XContainer.Element%2A> yöntemi <xref:System.Xml.Linq.XContainer?displayProperty=fullName> sınıfı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>   
 [XElement sınıfı dinamik özellikleri](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)



