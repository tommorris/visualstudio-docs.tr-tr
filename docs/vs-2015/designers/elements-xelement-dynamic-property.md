---
title: Öğeler (XElement dinamik özelliği) | Microsoft Docs
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
- XElement.Elements
api_type:
- Assembly
ms.assetid: 3d5737f2-d2ed-410a-821c-349dbb2b574f
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 75cb7f8f6a5259151679ecee84bbeb5db336782f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676187"
---
# <a name="elements-xelement-dynamic-property"></a>Öğeler (XElement dinamik özelliği)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [öğeler (XElement dinamik özelliği)](https://docs.microsoft.com/visualstudio/designers/elements-xelement-dynamic-property).  
  
Geçerli öğenin belirtilen Genişletilmiş adı ile eşleşen alt öğeleri almak için kullanılan bir dizin oluşturucuyu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
elem.Elements[{namespaceName}localName]   
```  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Bir dizin oluşturucu türü `IEnumerable<XElement> Item(String expandedName)`. Bu dizin oluşturucu genişletilmiş adının istenen alt öğeleri alır ve eşleşen alt öğeleri döndürür bir <xref:System.Collections.IEnumerable> `<` <xref:System.Xml.Linq.XElement> `>` koleksiyonu.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu özellik değerine eşdeğer olan <xref:System.Xml.Linq.XContainer.Elements%28System.Xml.Linq.XName%29?displayProperty=fullName> yöntemi <xref:System.Xml.Linq.XContainer> sınıfı.  
  
 İade edilen koleksiyon içinde XML kaynak belge düzeninde öğeleridir.  
  
 Bu özellik, ertelenmiş yürütme kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XElement sınıfı dinamik özellikleri](../designers/xelement-class-dynamic-properties.md)   
 [Öğesi](../designers/element-xelement-dynamic-property.md)   
 [Alt öğeleri](../designers/descendants-xelement-dynamic-property.md)



