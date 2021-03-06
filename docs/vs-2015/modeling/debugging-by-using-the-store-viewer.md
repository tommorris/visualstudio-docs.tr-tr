---
title: Store görüntüleyiciyi kullanarak hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
ms.assetid: 0178db2e-ae99-4ed3-9b87-8620fa9fa8e4
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: d0955cae279ece70498ce05584d6b17d6e254f89
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692065"
---
# <a name="debugging-by-using-the-store-viewer"></a>Depo Görüntüleyiciyi Kullanarak Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Store görüntüleyiciyi kullanarak hata ayıklama](https://docs.microsoft.com/visualstudio/modeling/debugging-by-using-the-store-viewer).  
  
Store Görüntüleyici ile durumunu inceleyebilirsiniz bir *depolamak* tarafından kullanılan [!INCLUDE[dsl](../includes/dsl-md.md)]. Store Görüntüleyici öğesi özellikleri ve öğeleri arasında bağlantılar ile birlikte, belirli bir depolama alanında bulunan tüm etki alanı model öğeleri görüntüler.  
  
## <a name="opening-store-viewer"></a>Açılış Store Görüntüleyicisi  
 Uygulamasındayken [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Deneysel burada depolama örneği model bilgileri içeren kodunuz bir kesme noktasında durdurmak, oluşturun. Ardından, aşağıdaki komutu yazarak Store Görüntüleyicisi'ni açın **hemen** penceresi:  
  
```  
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);  
```  
  
> [!NOTE]
>  Değiştirmeniz gereken `mystore` deposu örneğinizin adı. Ayrıca, ad alanı kodunuza ekleyin, tam nitelikli ad Store Görüntüleyicisi'ni görüntülemek için komutu yazabilirsiniz:  
>   
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`  
>   
>  `…`  
>   
>  `StoreViewer.Show(mystore);`  
  
 `Show` Yöntemi olan çeşitli aşırı yükler. Bir mağaza veya bir bölümleme örneği parametre olarak belirtebilirsiniz.  
  
 Alternatif olarak, Store Görüntüleyicisi kodunuzdaki herhangi bir yere görüntüler kod satırının koyabilirsiniz burada geçirdiğiniz parametre `Show` kapsamda bir yöntemdir. Bu eylem, kod satırının bir anlık görüntüsünü deposunun içeriğini yürütüldüğünde Store Görüntüleyicisi'ni görüntüler.  
  
### <a name="using-store-viewer"></a>Store Görüntüleyicisi'ni kullanma  
 Store Görüntüleyicisi oturum açtığında, engelleyici olmayan bir Windows Forms pencere, aşağıdaki çizimde gösterildiği gibi görünür.  
  
 ![](../modeling/media/storeviewer2.png "storeviewer2")  
Store Görüntüleyicisi  
  
 Store Görüntüleyicisi üç bölme vardır: sol bölmesinde, sağ üst bölmesi ve sağ alt bölmesi. Sol bölmede türlerini ağaç görünümünde olduğunu `DomainDataDirectory` mağaza üyesi. Ve bölüm düğümünü genişletin ve bir öğeyi tıklatın, öğenin özellikler sağ üst bölmede görünür. Öğenin diğer öğelere bağlı ise, ek öğeler sağ alt bölmede görünür. Öğesi, öğenin sağ alt bölmede çift tıklarsanız, sol bölmede vurgulanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Kodunda Modeli Gezinme ve Güncelleştirme](../modeling/navigating-and-updating-a-model-in-program-code.md)



