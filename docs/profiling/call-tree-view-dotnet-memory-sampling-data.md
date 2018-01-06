---
title: "Çağrı ağacı görünümü - .NET bellek örnekleme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Call Tree view
ms.assetid: fbb6cb60-420b-4ca9-8306-2494f7d321fe
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 5c81f9b5ff7d0bad9c0a05bd4b43374ac9451cf1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="call-tree-view---net-memory-sampling-data"></a>Çağrı ağacı görünümü - .NET bellek örnekleme verileri
Çağrı ağacı görünümü profili uygulamada geçiş işlevi yürütme yollarını görüntüler. Ağaç kök uygulama veya bileşenin giriş noktasıdır. Her işlevi düğümü adlı tüm işlevleri ve bu işlev çağrıları hakkında .NET bellek ayırma verileri listeler.  
  
 Çağrı ağacı görünümü çağrısı ağacında üst işlevi tarafından çağrılan işlev örnekleri için değerler. Yüzde değerleri, toplam sayısı veya boyutu çalıştırmak profil ayırmalarının işlevi örneği değerini karşılaştırarak hesaplanır.  
  
## <a name="highlighting-the-execution-hot-path"></a>Yürütme etkin yolunuzda vurgulama  
 Çağrı ağacı görünümü genişletin ve işlem veya en büyük oluşturulan işlevi ya da çoğu bellek nesneleri yürütme yolu vurgulayın. En etkin yol görüntülemek için işlem veya işlevi sağ tıklayın ve ardından **genişletin etkin yolunuzda**.  
  
## <a name="setting-the-call-tree-root-node"></a>Çağrı ağacı kök düğümü ayarlama  
 Profil oluşturma Çalıştır her işlem, bir kök düğümü olarak görüntülenir. Çağrı ağacı görünümü başlangıç düğümünün farklı bir düğüme ayarlamak için seçin ve başlangıç düğümü olarak ayarlamak istediğiniz düğümünü sağ tıklatın **ayarlamak kök**.  
  
 Kök düğüm kümesi olduğunda, Seçili düğümün alt ağacı dışında görünümünden diğer tüm girişleri kaldırın. Kök düğüm görüntülemekte olduğunuz düğüme geri sıfırlayabilirsiniz; Çağrı ağacı Görünümü penceresinde sağ tıklayın ve **sıfırlama kök**.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**İşlem kimliği**|İşlemi çalıştırmak profil oluşturma kimliği (PID).|  
|**İşlem adı**|İşlemin adı.|  
|**Modül adı**|İşlevi içeren modülü adı.|  
|**Modül yolu**|İşlevi içeren modülü yolu.|  
|**Kaynak dosya**|Bu işlev için tanım içeriyor kaynak dosya.|  
|**İşlev adı**|İşlev tam adı.|  
|**İşlev satır numarası**|Bu işlev kaynak dosyadaki başlangıç satır sayısı.|  
|**İşlev adresi**|İşlev adresi.|  
|**Düzeyi**|Çağrı ağacı işlevinde derinliği.|  
|**Kapsayıcı ayırmaları**|Bu işlev çağrısı ağacında üst işlevi tarafından adı veriliyordu örnekler tarafından ayrılan nesnelerin sayısı. Bu sayı, alt işlevleri tarafından yapılan ayırmaları içerir.|  
|**Kapsayıcı ayırmaları %**|Profil çalıştırdığınızda oluşturulan tüm nesneler yüzdesi bu işlevin kapsayıcı ayırmaları yoktu.|  
|**Özel ayırmaları**|Bu işlev çağrısı ağacında üst işlevi tarafından adı veriliyordu örnekler tarafından ayrılan nesnelerin sayısı. Bu sayı, alt işlevleri tarafından yapılan ayırmaları içermez.|  
|**Özel ayırmaları %**|Profil çalıştırdığınızda oluşturulan tüm nesneler yüzdesi çağrısı ağacında üst işlevi tarafından çağrılan işlevi örneklerinin özel ayırmaları yoktu.|  
|**Kapsayıcı bayt**|Bu işlev çağrısı ağacında üst işlevi tarafından adı veriliyordu örnekler tarafından ayrılan belleği bayt sayısı. Bu sayı, alt işlevleri tarafından yapılan ayırmaları içerir.|  
|**Kapsayıcı bayt %**|Profil çalışmasını ayrılan tüm bayt bellek yüzdesi bu işlevin kapsayıcı ayırmaları yoktu.|  
|**Özel bayt sayısı**|Bu işlev çağrısı ağacında üst işlevi tarafından adı veriliyordu örnekler tarafından ayrılan belleği bayt sayısı. Bu sayı, alt işlevleri tarafından yapılan ayırmaları içermez.|  
|**Özel bayt %**|Profil çalışmasını ayrılan tüm bayt bellek yüzdesi bu işlevin özel ayırmaları yoktu.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çağrı ağacı görünümü - izleme](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [Çağrı ağacı görünümü](../profiling/call-tree-view-sampling-data.md)   
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-instrumentation-data.md)