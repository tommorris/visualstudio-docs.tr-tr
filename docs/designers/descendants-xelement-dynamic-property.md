---
title: "Alt öğeleri (XElement dinamik özellik) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-designers
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9611d00f-23bf-444b-ab0c-f30701bfc13d
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0a70d56be83a824c8bfd950ea148fe68e6ffa43b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="descendants-xelement-dynamic-property"></a>Alt öğeleri (XElement dinamik özellik)
Belirtilen genişletilmiş adı ile eşleşen tüm alt öğeleri geçerli öğenin almak için kullanılan bir dizin oluşturucu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
elem.Descendants[{namespaceName}localName]  
```  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bir dizin oluşturucu türü `IEnumerable<XElement> Item(String expandedName)`. Bu dizin oluşturucu genişletilmiş adının belirtilen alt öğelerinin alıp eşleşen alt öğeleri döndüren bir <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` koleksiyonu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik eşdeğerdir <xref:System.Xml.Linq.XContainer.Descendants(System.Xml.Linq.XName)?displayProperty=fullName> yöntemi <xref:System.Xml.Linq.XContainer> sınıfı.  
  
 Döndürülen koleksiyonundaki XML kaynak belge düzeninde öğelerdir.  
  
 Bu özellik, ertelenmiş yürütme kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dinamik özellikler XElement sınıfı](../designers/xelement-class-dynamic-properties.md)   
 [Elements](../designers/elements-xelement-dynamic-property.md)