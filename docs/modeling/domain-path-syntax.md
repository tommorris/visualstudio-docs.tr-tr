---
title: Etki alanı yolu sözdizimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, domain path
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 3bac81f79b2639a7b1b4f93055855981d4c30786
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
 [Modelleri, Sınıfları ve İlişkileri Anlama](../modeling/understanding-models-classes-and-relationships.md)