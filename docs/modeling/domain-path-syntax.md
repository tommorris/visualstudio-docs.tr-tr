---
title: "Etki alanı yolu sözdizimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, domain path
ms.assetid: 945994f9-72b9-42e0-81b2-e5fb3d0e282d
caps.latest.revision: "25"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: d32cef09adef982f22aa46a72ab71cd1e7ec8568
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="domain-path-syntax"></a>Etki Alanı Yolu Sözdizimi
DSL tanımları XPath benzeri bir sözdizimi bir modelde belirli öğeleri bulmak için kullanın.  
  
 Normalde bu sözdizimi ile doğrudan çalışmak zorunda değildir. DSL ayrıntıları veya özellikleri penceresinde göründüğü aşağı oka tıklayın ve yolu Düzenleyicisi'ni kullanın. Ancak, düzenleyici kullandıktan sonra yol bu alanın formda görüntülenir.  
  
 Bir etki alanı yolu aşağıdaki biçimdedir:  
  
 *RelationshipName.PropertyName/! Rolü*  
  
 ![CommentReferencesSubjects başvuru ilişkisi](../modeling/media/dsl_reference.png "dsl_reference")  
  
 Sözdizimi ağacı modelinin erişir. Örneğin, etki alanı ilişkisinin **CommentReferencesSubjects** Yukarıdaki çizimde sahip bir **konuları** rol. Yol kesimi **/! Subjectt** yolu üzerinden erişilen öğelerde tamamlandığını belirtir **konuları** rol.  
  
 Her segmentinde bir etki alanı ilişkisinin adıyla başlar. Geçişi arasında bir ilişki öğeden ise, yol kesimi olarak görünür *Relationship.PropertyName*. Atlama bir öğeye bir bağlantıdan ise, yol kesimi olarak görünür *ilişki /! RoleName*.  
  
 Eğik bir yolu sözdizimi ayırın. Her yol kesimi ya da bir atlama bir bağlantı (bir ilişki örneği) için bir öğe veya öğenin bağlantısını ' dir. Yol kesimleri sık çiftler halinde görüntülenir. Bir yol kesimi bir atlama bir öğeyi bağlantısını temsil eder ve sonraki kesimini bir atlama bağlantıdan diğer uçtaki öğesine temsil eder. (Herhangi bir bağlantıyı de kaynak veya hedef bir ilişkinin olabilir).  
  
 Öğe bağlantı atlaması için kullandığınız adı rolün değeri `Property Name`. Link öğesi atlaması için kullandığınız adı hedef rol adı değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anlama modelleri, sınıflar ve ilişkiler](../modeling/understanding-models-classes-and-relationships.md)