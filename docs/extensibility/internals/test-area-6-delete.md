---
title: 'Test alanı 6: Sil | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], deleting items
- source control plug-ins, deleting items
ms.assetid: 6f2e872c-5ba2-4303-9f50-a90cef9a6225
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97fc6ab9746e7ef2188c78dc77ec357f7d415a42
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140235"
---
# <a name="test-area-6-delete"></a>Test alanı 6: Sil
Bu kaynak denetimi eklenti test alan silme eylemleri kapsar.  
  
 Kaynak denetimi yanıt eylemleri silmek için **Çözüm Gezgini**.  
  
 Aşağıda, silinebilir öğelerin bir listesi verilmiştir:  
  
-   Dosyalar  
  
-   Klasörleri  
  
-   Proje  
  
 Proje türüne bağlı olarak seçeneğine sahip olabilir **kaldırmak** (bırakır diskteki dosyaları) proje veya **silmek** projenin (diskteki dosyaları kaldırır). Her iki eylem proje veya öğesinden kaldırır **Çözüm Gezgini**.  
  
## <a name="expected-behavior"></a>Beklenen bir davranış  
 Delete test alanı test çalışmaları için beklenen davranıştır:  
  
-   Silinmiş Öğe içinde görünür olduğundan artık **Çözüm Gezgini**.  
  
-   Silinen proje veya öğenin üst (büyük olasılıkla bir istemiyle.) gerektiği gibi kullanıma  
  
-   Out kullanıma alınmış silin veya öğesi eklendikten sonra görünmez **Bekleyen İadeler** penceresi.  
  
-   Öğe hala kaynak denetim deposunu içinde silindikten sonra bile var olduğundan ve el ile temizlenmelidir.  
  
|Eylem|Test adımları|Doğrulamak için beklenen sonuçları|  
|------------|----------------|--------------------------------|  
|Bir istemci projesi silme|1.  Bir istemci projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Tüm proje çözümden Kaldır|Ortak beklenen davranıştır.|  
|Boş bir dosya silme|1.  Bir istemci projesi oluşturun.<br />2.  Sıfır bayt boyutunda bir dosya projeye ekleyin.<br />3.  Çözümü kaynak denetimine ekleyin.<br />4.  Dosyayı seçin ve onu silin.|Ortak beklenen davranıştır.|  
|Bir dosyayla bir klasörü silin|1.  Tek proje çözümü oluşturun.<br />2.  Bir klasör ekleyin.<br />3.  Bir dosya klasörüne ekleyin.<br />4.  Çözümü kaynak denetimine ekleyin.<br />5.  Önlemek için proje kullanıma ister.<br />6.  Klasörü silin.|Ortak beklenen davranıştır.|  
|Bir dosya sistemi Web projesi silme|1.  Bir dosya sistemi Web projesi (bir UNC yolu belirtmek için Gözat düğmesini kullanın) oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Tüm proje çözümden kaldırın.<br />4.  Yerel bir Web projesi için 1 ile 3 arasındaki adımları yineleyin (kodlarda farklı yollar uygular, ancak aynı dış arabirimi ve davranışı sahiptir).|Ortak beklenen davranıştır.|  
|Bir dosya sistemi Web projesinde dosya silme|1.  Bir dosya sistemi Web projesi oluşturun.<br />2.  Çözümü kaynak denetimine ekleyin.<br />3.  Bir dosyayı projeden silin.<br />4.  Yerel bir Web projesi için 1 ile 3 arasındaki adımları yineleyin (kodlarda farklı yollar uygular, ancak aynı dış arabirimi ve davranışı sahiptir).|Ortak beklenen davranıştır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentileri için Test Kılavuzu](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)