---
title: Geri arama işlevleri IDE tarafından uygulanan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, callback functions
- callback functions, source control plug-ins
ms.assetid: 4a8833f0-6ac0-4ea7-9400-8275aa991468
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ffdcc7d92770f486f9a345acf14e12e14214a2b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109694"
---
# <a name="callback-functions-implemented-by-the-ide"></a>IDE tarafından uygulanan geri arama işlevleri
Bir birleşik son kullanıcı deneyimi sağlamak için ve mümkün olduğunca sorunsuz olarak tümleşik geliştirme ortamı (IDE) ile tümleştirme yapmak için kaynak denetim eklentisi IDE tarafından uygulanan geri arama işlevleri kullanabilirsiniz. Eklenti bu işlevler IDE bilgi aktarmak için bir kaynak denetimi işlemi sırasında uygun zamanlarda çağırabilirsiniz; IDE yerel kullanıcı Arabiriminde katıştırılmış öğeleri olarak bu bilgiler daha sonra görüntüleyebilirsiniz. Kullanıcı Bu senaryoda eklenti kendi UI işe varsa daha az parçalanmış deneyimi sahip değil.  
  
 Gerekli üstbilgisi scc.h dosyasıdır. Varsayılan konumu \Program Files\VSIP 8.0\EnvSDK\common\inc:\\. Ayrıca \Program Files\VSIP 8.0\MSSCCI kaynak denetim Eklentisi örneği olan VSIP klasörü olarak\\.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [LPTEXTOUTPROC](../extensibility/lptextoutproc.md)  
 Tarafından kullanılan geri çağırma işlevini açıklar [SccOpenProject](../extensibility/sccopenproject-function.md) IDE'yi eklenti kaynak denetiminden iletileri görüntülemek için.  
  
 [POPLISTFUNC](../extensibility/poplistfunc.md)  
 Tarafından kullanılan geri çağırma işlevini açıklar [SccPopulateList](../extensibility/sccpopulatelist-function.md) IDE sahip olmadığında yalnızca eklenti sürüm denetimi kapsamındaki dosyaları tam bir listesi gibi kaynak denetimi kullanılabilir bilgi tam erişim.  
  
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)  
 Tarafından kullanılan geri çağırma işlevini açıklar [SccQueryChanges](../extensibility/sccquerychanges-function.md) işlemi.  
  
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)  
 Tarafından kullanılan geri çağırma işlevini açıklar [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) işlemi.  
  
 [OPTNAMECHANGEPFN](../extensibility/optnamechangepfn.md)  
 Açıklayan bir çağrı tarafından ayarlanan geri çağırma işlevi [SccSetOption](../extensibility/sccsetoption-function.md) eklentisinin ad değişiklikleri geri IDE iletişim kurmak için kaynak denetimi sağlar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [SccOpenProject](../extensibility/sccopenproject-function.md)  
 Bir proje açar.  
  
 [SccPopulateList](../extensibility/sccpopulatelist-function.md)  
 Bunların geçerli durum için dosyaları listesi inceler. Ayrıca, kullanır `pfnPopulate` işlevi çağıran bir dosya için ölçüt eşleşmediğinde bildirmek için `nCommand`.  
  
 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)  
 Dizinler ve dosyalar bir proje veya kaynak denetimi altında olan projeler listesini inceler. Bulunan her dizin ve dosya adı için bir geri çağırma işlevini geçirilir.  
  
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)  
 Dosyaların listesini görmek için yapılan ad değişiklikleri inceler. Her dosya adı bir geri çağırma işlevini Değiştir durumunu birlikte geçirilir.  
  
 [SccSetOption](../extensibility/sccsetoption-function.md)  
 Çok çeşitli seçenekler ayarlar. Her seçeneği ile başlayan `SCC_OPT_xxx` ve kendi tanımlanan değerleri kümesi vardır.  
  
 [Kaynak Denetimi Eklentileri](../extensibility/source-control-plug-ins.md)  
 Kaynak Denetim eklentisi SDK'sı başvurusu bölümü içeriğini açıklar.