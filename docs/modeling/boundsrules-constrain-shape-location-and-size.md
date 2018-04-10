---
title: BoundsRules şekli konumunu ve boyutunu sınırlamak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: c672cbc25c28bf4d74f01160212584875b51ba1a
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>BoundsRules Şekil Konumunu ve Boyutunu Kısıtlamama
A *sınırları kural* sınırları boyutu ve şekli konumunu tanımlayan bir sınıftır. Bir kullanıcı bir şekli veya köşeleri ya da bir şekli yanlarından sürükleme sırasında sürekli olarak adlandırılan bir yöntem sağlar.  
  
 Aşağıdaki örnekte, sabit boyutlu, yatay veya dikey çubuk olarak dikdörtgen kısıtlar. Kullanıcı köşeleri ya da yanlara sürüklendiğinde anahattı iki izin verilen yapılandırmaları yükseklik ve genişlik arasında çevirir.  
  
 Bir sınıf türetilir sınırları kural <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>. Kural örneği şeklinde oluşturulur:  
  
```  
using Microsoft.VisualStudio.Modeling.Diagrams; ...  
public partial class BarShape  
{  
  /// <summary>  
  /// Rule invoked when the user is resizing a shape.  
  /// </summary>  
  public override BoundsRules BoundsRules  
  { get { return new BarBoundsRule(); } }  
}  
/// <summary>  
/// Rule invoked when the user is changing a shape's outline.  
/// Provides real-time mouse rubber-band feedback, so must work fast.  
/// </summary>  
public class BarBoundsRule: BoundsRules  
{   
  public override RectangleD GetCompliantBounds   
     (ShapeElement shape, RectangleD proposedBounds)  
  {  
    double thickness = 0.1;  
    if (proposedBounds.Height > proposedBounds.Width)  
    {  
      // There is a minimum width for a shape; the width  
      // will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
            new SizeD(thickness, proposedBounds.Height));  
    }  
    else  
    {  
      // There is a minimum height for a shape; the   
      // height will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
         new SizeD(proposedBounds.Width, thickness));  
} } }  
```  
  
 İsterseniz konum ve boyut kısıtlanabilir dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [Değişikliklere Yanıt Verme ve Değişiklikleri Yayma](../modeling/responding-to-and-propagating-changes.md)