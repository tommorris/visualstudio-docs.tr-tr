---
title: Mağaza Görüntüleyicisi'ni kullanarak hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 182b413004c6b6193ffa0e614fdad226d2012bdc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debugging-by-using-the-store-viewer"></a>Depo Görüntüleyiciyi Kullanarak Hata Ayıklama
Depolama Görüntüleyici ile durumunu inceleyebilirsiniz bir *depolamak* tarafından kullanılan [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]. Depolama Görüntüleyicisi tüm öğesi özellikler ve öğeler arasında bağlantılar ile birlikte belirli bir depolama alanında bulunan etki alanı model öğelerini görüntüler.  
  
## <a name="opening-store-viewer"></a>Açılış deposu Görüntüleyicisi  
 Uygulamasındayken [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] deneysel yapı, kodunuzu bir kesme noktasında deposu örneği model bilgileri, içerdiği durdurun. Ardından, aşağıdaki komutu yazarak deposu Görüntüleyicisi'ni açmak **hemen** penceresi:  
  
```  
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);  
```  
  
> [!NOTE]
>  Değiştirmeniz gereken `mystore` depo örneği adı. Ayrıca, ad alanı kodunuzu eklerseniz, tam ad deposu Görüntüleyicisi görüntülemek için komutu yazabilirsiniz:  
>   
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`  
>   
>  `...`  
>   
>  `StoreViewer.Show(mystore);`  
  
 `Show` Yöntemi birçok aşırı yüklemeye sahip. Bir mağazaya veya bir bölümünün bir örneği parametre olarak belirtebilirsiniz.  
  
 Alternatif olarak, depolama Görüntüleyicisi kodunuzda herhangi bir yere görüntüler kod satırı koyabilirsiniz olduğu için geçirdiğiniz parametre `Show` kapsamında bir yöntemdir. Kod satırı ile bir anlık görüntü deposu içeriğini yürüttüğünde Bu eylem depolamak Görüntüleyicisi'ni görüntüler.  
  
### <a name="using-store-viewer"></a>Mağaza Görüntüleyicisi'ni kullanma  
 Deposu Görüntüleyicisi'ni oturum açtığında, kalıcı olmayan bir Windows Forms penceresi, aşağıda gösterildiği gibi görünür.  
  
 ![](../modeling/media/storeviewer2.png "storeviewer2")  
Mağaza Görüntüleyicisi  
  
 Mağaza Görüntüleyicisi üç bölmesi vardır: sol bölmede, sağ üst bölmesi ve sağ alt bölmesi. Sol bölmede türlerini ağaç görünümünde olduğunu `DomainDataDirectory` mağaza üyesi. Bölüm düğümünü genişletin ve bir öğeyi tıklatın, öğenin özellikleri sağ üst bölmesinde görünür. Öğe diğer öğeleri bağlıysa, ek öğeler sağ alt bölmesinde görünür. Bir öğeyi sağ alt bölmesinde çift tıklarsanız, öğenin sol bölmede vurgulanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Kodunda Modeli Gezinme ve Güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)