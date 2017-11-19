---
title: Programlar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], programs
- programs, debugging
ms.assetid: e1f955d8-95da-493b-837e-e97741a26d7e
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e34dbcf9c19b5e8e7a16d2f409159597670cb8cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="programs"></a>Programlar
Hata ayıklayıcı mimarisi bakımından bir **program**:  
  
-   Bir modül kümesini ve iş parçacığı kümesi için bir kapsayıcıdır. Bir program yok tek benzerleme Windows işletim sisteminde vardır.  
  
     Bir program, alt türüdür. Örneğin, bir Web sitesi ayıklarken bir komut dosyası bir program olarak görülebilir. Bir komut dosyası komut dosyası altyapısı işleminde çalışırken, diğer komutlar bağımsız Ayrıca kendi iş parçacığı kümesini içerir. Hata ayıklama altyapısı (DE), bir programa ve bir işlem veya bir iş parçacığı ekler.  
  
-   Kendisi ve çalışır durumda ve gelen ayrılmış ve, varsa oluşturulan DE açıklamak için bağlı işlemi tanımlayabilirsiniz. Bir program yürütme, durdurmak, devam etmek ve sonlandırılacak.  
  
-   Tüm iş parçacıklarının sıralayabilirsiniz. Bir program kendi ayrıştırılmış akışı aynı zamanda sağlayabilir ve verilen belgedeki konumlarından tüm kod bağlamları sıralayabilirsiniz.  
  
-   Tarafından temsil edilen bir [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md) program bağlanmadan önce veya uygulamaya bağlı olarak attach işleminin bir parçası olarak oluşturulan arabirimi. Program bir işlem olarak bir bağlantı noktası sıralar, her bir program karşılık gelen uygun olarak oluşturulduğunda [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) arabirimi geçirilen bağımsız değişken olarak [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Hata ayıklama motorları da oluştururken `IDebugProgram2` arabirimleri programları, bu programlar göstermek için bir program düğümü uygun şekilde oluşturulmadı. `IDebugProgramNode2` SE tarafından oluşturulan arabirimleri kullanılan gerçek hata ayıklama için bağlantı noktası tarafından oluşturulanlar yalnızca bir işlemde çalışan hangi programlar keşfetmek için kullanılırken.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlemler](../../extensibility/debugger/processes.md)   
 [Program düğümler](../../extensibility/debugger/program-nodes.md)   
 [Modülleri](../../extensibility/debugger/modules.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [Belge konumu](../../extensibility/debugger/document-position.md)   
 [Kod bağlamı](../../extensibility/debugger/code-context.md)   
 [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)