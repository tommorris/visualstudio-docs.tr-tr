---
title: "Program düğümleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6deae60a8e7863e19ec0624ff6452bf41816070
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="program-nodes"></a>Program düğümler
Hata ayıklayıcı mimarisi bakımından bir **program düğümü**:  
  
-   Basit bir program açıklamasıdır.  
  
-   Kendisi ve çalışır durumda ve gelen ayrılmış ve, varsa oluşturulan hata ayıklama altyapısı (DE) açıklamak için bağlı işlemi tanımlayabilirsiniz.  
  
-   Tarafından temsil edilen bir [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) arabirimi, genellikle bir DE veya bağlantı noktası tarafından oluşturuldu. Program düğümleri, bir bağlantı noktasına çağrılarak eklenir [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Bir program düğüme bir bağlantı noktasına eklendiğinde, bu program düğümün temsil ettiği programı içeren işlem eklenir.  
  
 Süre bir hata ayıklama oturumu, hata ayıklama paket uygulama bağlı olarak başlatıldıktan sonra program düğümleri karşılık gelen programlar oluşturmak için kullanılır. Bir işlem için programları sorgulandığında programları numaralandırılır, her program düğümü için bir tane.  
  
 Bir program iliştirildiği önce IDE basit açıklaması program gerekir. Bu bilgi programı düğümden elde edilebilir. Program için bağlandıktan sonra programda çalışan tüm iş parçacıklarının listesi gibi daha ayrıntılı bilgileri görüntülemek IDE gerekir. Bu bilgiler programından elde edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [İşlemler](../../extensibility/debugger/processes.md)   
 [Altyapısı hata ayıklama](../../extensibility/debugger/debug-engine.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)