---
title: Öğeleri (XElement dinamik özellik) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-designers
ms.topic: conceptual
apiname:
- XElement.Elements
apitype: Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7c68611dc8377d9fc32f6eedbbfd0114959cf08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="elements-xelement-dynamic-property"></a>Öğeleri (XElement dinamik özellik)
Belirtilen genişletilmiş adı ile eşleşen geçerli öğenin alt öğeleri almak için kullanılan bir dizin oluşturucu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bir dizin oluşturucu türü `IEnumerable<XElement> Item(String expandedName)`. Bu dizin oluşturucu öğeleri istenen alt genişletilmiş adını alır ve eşleşen alt öğeleri döndürür bir <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` koleksiyonu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik eşdeğerdir <xref:System.Xml.Linq.XContainer.Elements(System.Xml.Linq.XName)?displayProperty=fullName> yöntemi <xref:System.Xml.Linq.XContainer> sınıfı.  
  
 Döndürülen koleksiyonundaki XML kaynak belge düzeninde öğelerdir.  
  
 Bu özellik, ertelenmiş yürütme kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dinamik özellikler XElement sınıfı](../designers/xelement-class-dynamic-properties.md)   
 [Öğesi](../designers/element-xelement-dynamic-property.md)   
 [Alt öğeleri](../designers/descendants-xelement-dynamic-property.md)