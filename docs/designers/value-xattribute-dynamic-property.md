---
title: Değer (XAttribute dinamik özellik) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-designers
ms.tgt_pltfrm: ''
ms.topic: article
apiname:
- XAttribute.Value
apitype: Assembly
ms.assetid: 019733d2-e050-4120-b537-831cd3fc008e
caps.latest.revision: 2
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4807a84b9e1de5186e72cbe138f0f54e2f33525e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
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