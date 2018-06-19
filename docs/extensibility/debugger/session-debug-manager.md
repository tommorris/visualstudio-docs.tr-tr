---
title: Oturum Yöneticisi hata ayıklama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- session debug manager, unifying session views
- session debug manager, broadcasting
- debugging [Debugging SDK], session debug manager
- session debug manager
- session debug manager, debug engine multiplexing
- session debug manager, delegating
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 001c0b954cd47b9825a6982f2474d6fd6d415e23
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31126239"
---
# <a name="session-debug-manager"></a>Oturum hata ayıklama Yöneticisi
Oturum hata ayıklama Yöneticisi'ni (SDM) herhangi bir sayıda makineler herhangi bir sayıda birden çok işlemi programlarında hata ayıklamayı debug motorları (DE) herhangi bir sayıda yönetir. Hata ayıklama altyapısı çoğaltıcı olmanın yanı sıra SDM IDE hata ayıklama oturumu birleşik bir görünümünü sağlar.  
  
## <a name="session-debug-manager-operation"></a>Oturum hata ayıklama Yöneticisi işlemi  
 Oturum hata ayıklama Yöneticisi'ni (SDM) DE yönetir. Aynı anda bir makinede çalışan birden fazla hata ayıklama altyapısı olabilir. DEs çoğullamalısınız için SDM DEs arabirimlerinden sayısı sarmalar ve bunları tek bir arabirim olarak IDE kullanıma sunar.  
  
 Performansı artırmak için bazı arabirimler arttıkça değil. Bunun yerine, doğrudan DE kullanılır ve bu arabirimleri çağrıları SDM geçmemektedir. Özel yönerge, bellek veya belirli bir program tarafından özel SE hata ayıklaması belgede başvurduğundan Örneğin, bellek, kod ve belge bağlamları kullanılan arabirimleri, arttıkça değil. Diğer bir DE iletişim o düzeyde söz konusu olması gerekir.  
  
 Bu tüm bağlamları doğru değil. İfade değerlendirme bağlamı arabirimi çağrıları SDM gidin. İfade değerlendirme sırasında SDM sarmalar [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) ifade değerlendirildiğinde olabilir aynı işlem programlarında hata ayıklama birden çok DEs gerektirebilir bulunduğundan IDE verir arabirimi aynı iş parçacığı üzerinde çalışıyor.  
  
 SDM genellikle bir temsilci seçme düzeneğini davranır, ancak bir yayın mekanizması olarak hareket. Örneğin, ifade değerlendirme sırasında SDM bunlar belirtilen bir iş parçacığı üzerinde kod çalıştırabilir tüm DEs bildirmek için bir yayın mekanizması olarak görev yapar. Benzer şekilde, SDM durdurma olayı aldığında, tüm programlar bunlar çalıştıran durması gerektiğini yayınlar. Bir adımı çağrıldığında SDM tüm programlar çalışmaya devam ettiğini yayınlar. Kesme noktaları ayrıca her DE yayınlanır.  
  
 SDM geçerli program, iş parçacığı veya yığın çerçevesi izlemez. İşlem, program ve iş parçacığı bilgi SDM belirli hata ayıklama olayları ile birlikte gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)   
 [Hata Ayıklayıcı Bağlamları](../../extensibility/debugger/debugger-contexts.md)