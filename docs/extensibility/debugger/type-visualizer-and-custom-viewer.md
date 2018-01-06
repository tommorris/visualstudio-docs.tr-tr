---
title: "Görselleştirici ve özel Görüntüleyicisi yazın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 91aa122c96230c7fd34ce2b65925b9166883def6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="type-visualizer-and-custom-viewer"></a>Türü Görselleştirici ve özel Görüntüleyicisi
Türü Görselleştirici çok belirli bir biçimde veri parçası görüntüleyen bir bileşenidir. Bu biçim tamamen Görselleştirici uygulayan kadar son kullanıcı veya bir üçüncü taraf sağlayıcısına görselleştiriciler olabilir.  
  
 Özel bir Görüntüleyici veri parçası çok belirli bir biçimde görüntüler bir özel ifade değerlendiricisi parçasıdır. Tamamen biçimi (EE) ifade değerlendiricisi uygulayan kadar anlamına gelir özel Görüntüleyicisi uygulayan kadar bu biçimidir.  
  
## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>Bir ifade değerlendiricisi içinde türü Görselleştiriciler desteği  
 Bir EE görselleştiriciler için erişilebilir arabirimleri kümesi destekleyerek türü görselleştiriciler destekleyebilir: gibi arabirimleri [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) ve [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md). Ancak, EE türü Görselleştirici uygulamak için sorumlu olmadığını unutmayın: EE yalnızca dış görselleştiriciler türü bilgilerini erişime izin. Bu tür görselleştiriciler EE birlikte sevk ve Visual Studio, son kullanıcı tarafından bile veya başka bir üçüncü taraf satıcı tarafından sağlanan uygun bir yerinde yüklenir.  
  
## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>Bir ifade değerlendiricisi özel izleyicilerin desteği  
 Bir EE EE veri türü görüntülemek için kod sağlayan özel görüntüleyiciler de destekler. Özel bir Görüntüleyici uygulayan [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) verileri ne olursa olsun biçiminde gösteren, tüm görevleri işleme arabirimi istenen; Görüntüleyici görüntü üzerinde tam denetime sahiptir ve değiştirilecek veri bile izin verebilirsiniz. Ürün gönderildiğinde EE tarafından sağlanan herhangi bir özel görüntüleyiciler EE ile gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bileşenleri](../../extensibility/debugger/debugger-components.md)   
 [İfade değerlendirici](../../extensibility/debugger/expression-evaluator.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)   
 [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)   
 [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)