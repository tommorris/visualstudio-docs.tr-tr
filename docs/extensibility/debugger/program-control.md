---
title: Program denetimi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], control of execution
ms.assetid: 6be80904-e66c-4cae-8891-1113b799fb01
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 244f6c2113aef3b3c3576288a0c403d702d8b17a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="program-control"></a>Program denetimi
Visual Studio'da hata ayıklama, tüm aşağıdaki atlama ve yordamları etmeden program düzeyinde gerçekleşir:  
  
-   Sonraki deyim ayarlama, diğer bir deyişle, bilgisayarınızı belirli çerçeve ortamında yürütülecek sonraki yönerge için ayarlama  
  
-   Yürütme, diğer bir deyişle, sürüm modundan çıkmak devam etme  
  
-   Sonraki yönerge Adımlama  
  
-   Geçerli sürüm modu ile devam etmeden  
  
-   Program tarafından bulunan iş parçacıklarını askıya alma  
  
-   Program tarafından bulunan iş parçacıklarını sürdürme  
  
> [!NOTE]
>  Çağrı yığını görüntüleme iş parçacığı düzeyinde uygulanır. Bir iş parçacığı için çağrı yığını görüntülerken çerçevesini bilgilerin numaralandırmak için tüm yöntemleri uygulamak [IEnumDebugFrameInfo2](../../extensibility/debugger/reference/ienumdebugframeinfo2.md) arabirimi.  
  
## <a name="methods-of-program-control"></a>Program denetim yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) , gerekir uygulanan en düşük düzeyde işlev hata ayıklama altyapısı (DE) ve yürütme denetimi için.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDebugProgram2::Execute](../../extensibility/debugger/reference/idebugprogram2-execute.md)|Durdurulmuş bir program tarafından bulunan tüm iş parçacığı çalışmaya devam eder. Yürütme denetimi için gereklidir.|  
|[IDebugProgram2::Continue](../../extensibility/debugger/reference/idebugprogram2-continue.md)|Durdurulmuş bir program tarafından bulunan tüm iş parçacığı çalışmaya devam eder. Yürütme denetimi için gereklidir.|  
|[IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md)|Bir adımı verilen iş parçacığı üzerinde gerçekleştirir. Program tarafından bulunan tüm diğer iş parçacığı çalışmaya devam eder. Yürütme denetimi için gereklidir.|  
  
 Birden çok iş parçacıklı programlar için aynı zamanda uygulamalıdır [IDebugProgram2::EnumThreads](../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) yöntemi ve tüm yöntemleri [IEnumDebugThreads2](../../extensibility/debugger/reference/ienumdebugthreads2.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yürütme Denetimi ve Durum Değerlendirmesi](../../extensibility/debugger/execution-control-and-state-evaluation.md)