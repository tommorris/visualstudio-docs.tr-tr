---
title: "Çağrı ağacı görünümü - örnekleme verileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sampling profiling method,Call Tree view
- Call Tree view
ms.assetid: 5c4e8ec3-d0d3-485a-93bd-9060df4eb739
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3759133ef7a2be2a7c4c7d04d1b2d444269b7005
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="call-tree-view---sampling-data"></a>Çağrı ağacı görünümü - örnekleme verileri
Çağrı ağacı görünümü profili uygulamada geçiş işlevi yürütme yollarını görüntüler.  
  
> [!NOTE]
>  Gelişmiş güvenlik özellikleri Windows 8 ve Windows Server 2012 Visual Studio profil oluşturucu bu platformlarda toplar şekilde önemli değişiklikler gerekmiştir. UWP uygulamalar için yeni koleksiyon teknikler de gerekir. Bkz: [Windows 8 ve Windows Server 2012 uygulamaların performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
 Ağaç kök uygulama veya bileşenin giriş noktasıdır. Her işlevi düğüm tüm adlı işlevleri ve bu işlev çağrıları hakkında performans verilerini listeler.  
  
 Çağrı ağacı görünümü çağrısı ağacında üst işlevi tarafından çağrılan işlev örnekleri için değerler. Yüzde değerleri, profil oluşturma çalıştırma örnekleri toplam sayısı işlevi örneği değerine karşılaştırarak hesaplanır.  
  
## <a name="highlighting-the-execution-hot-path"></a>Yürütme etkin yolunuzda vurgulama  
 Çağrı ağacı görünümü genişletin ve işlem ya da en sık örneklenen işlevi yürütme yolunu vurgulayın. En etkin yol görüntülemek için işlem veya işlevi sağ tıklayın ve ardından **genişletin etkin yolunuzda**.  
  
## <a name="setting-the-call-tree-root-node"></a>Çağrı ağacı kök düğümü ayarlama  
 Profil oluşturma Çalıştır her işlem, bir kök düğümü olarak görüntülenir. Çağrı ağacı görünümü başlangıç düğümünün ayarlamak için seçin ve başlangıç düğümü olarak ayarlamak istediğiniz düğümünü sağ tıklatın **ayarlamak kök**.  
  
 Kök düğüm kümesi olduğunda, Seçili düğümün alt ağacı dışında görünümünden diğer tüm girişleri kaldırın. Kök düğüm özgün düğüme geri sıfırlamak için çağrı ağacı Görünümü penceresinde sağ tıklatın ve seçin **sıfırlama kök**.  
  
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
|**Düzeyi**|Bu işlev çağrısı ağacında derinliği. Yalnızca [VSPerfReport](../profiling/vsperfreport.md) komut satırı raporlar.|  
|**Özel örnekleri**|Çağrı ağacı üst işlevinde tarafından çağrıldığında, bu işlevde toplanan örnek sayısı. Bu sayı işlev tarafından adı veriliyordu işlevlerinde toplanan örnekleri içermez.|  
|**Özel örnekleri %**|Üst işlev çağrısı ağacında tarafından çağrıldığında, bu işlevin özel örnekleri olan tüm örneklerini profil çalıştırmada yüzdesi.|  
|**Kapsayıcı örnekleri**|Çağrı ağacı üst işlevinde tarafından çağrıldığında, bu işlevde toplanan örnek sayısı. Bu sayı işlev tarafından adı veriliyordu işlevleri toplanan örnekleri içerir.|  
|**Kapsayıcı örnekleri %**|Üst işlev çağrısı ağacında tarafından çağrıldığında, bu işlevin kapsayıcı örnekleri olan tüm örneklerini profil çalıştırmada yüzdesi.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [Çağrı ağacı görünümü - profil oluşturucu örnekleme verileri](../profiling/call-tree-view-sampling-data.md)   
 [Çağrı ağacı görünümü - örnekleme](../profiling/call-tree-view-dotnet-memory-sampling-data.md)   
 [Çağrı ağacı görünümü - izleme](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-instrumentation-data.md)