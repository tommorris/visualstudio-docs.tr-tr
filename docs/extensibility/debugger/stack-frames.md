---
title: "Yığın çerçeveleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- stack frames, debugging
- debugging [Debugging SDK], stack frames
- stack frames
ms.assetid: b5e439d4-1e9d-4e13-9cad-bb8b136d4ca8
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 110a68d737ac2f194c7a318c41d05801d69511c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="stack-frames"></a>Yığın çerçeveleri
Hata ayıklayıcı mimarisi bakımından bir **yığın çerçevesi**:  
  
-   Bir iş parçacığı yürütme bağlamı sağlayan yığının bir soyutlamadır. Bir iş parçacığı her zaman bir işlev içinde yürütür. Yığın çerçevesi işlev bağımsız değişkenleri ve yerel değişkenler için tutar. Visual Studio ile hata ayıklama için dil veya ayıklanacak ortamında yığın çerçeveleri desteklemesi gerekir.  
  
-   İçin her ikisini de tanımlamak ve kendisini açıklar ve ilişkili iş parçacığı geri dönebilirsiniz. Yığın çerçevesi aynı zamanda geçerli yönerge işaretçisi yanı sıra ilişkili belgeleri temsil eden kod bağlamını ve ifade değerlendirme bağlamı geri dönebilirsiniz.  
  
-   Adını, türünü ve değerini yerel değişkenleri ve bağımsız değişkenler açıklayan ve çeşitli IDE hata ayıklama pencerelerinde görüntüleneceği özelliklere sahiptir.  
  
-   Tarafından temsil edilen bir [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md) arabirimi, genellikle bir hata ayıklama altyapısı (DE) veya bir iş parçacığının gruplarındaki sonucu olarak sanal makine tarafından oluşturulmuş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı bağlamları](../../extensibility/debugger/debugger-contexts.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [IDebugStackFrame2](../../extensibility/debugger/reference/idebugstackframe2.md)