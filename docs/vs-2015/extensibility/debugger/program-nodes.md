---
title: Program düğümleri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- program nodes, debugging context
- debugging [Debugging SDK], program nodes
- program nodes, adding
- program nodes, superceding
ms.assetid: 1c5a5c13-c14d-42c3-af11-4c63f1032c8d
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: caff608b85dc8fc563ace8f5d582dba1cba427c0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693382"
---
# <a name="program-nodes"></a>Program Düğümleri
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Program düğümleri](https://docs.microsoft.com/visualstudio/extensibility/debugger/program-nodes).  
  
Hata ayıklayıcı mimarisi bakımından bir **program düğüm**:  
  
-   Basit bir program açıklamasıdır.  
  
-   Kendisi ve çalıştığı ve öğesinden ayrıldı ve, varsa oluşturulan hata ayıklama altyapısı (DE) tanımlamak için bağlı işlemi tanımlayabilirsiniz.  
  
-   Tarafından temsil edilen bir [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) arabirimi, genellikle DE veya bağlantı noktası tarafından oluşturulur. Program düğümleri çağırarak bir bağlantı noktasına eklenir [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md). Bir program düğüm bir bağlantı eklendiğinde bu programı bu düğümün temsil ettiği program içeren işleme eklenir.  
  
 Süre bir hata ayıklama oturumu, hata ayıklama paketi bağlı olarak uygulama başlatıldıktan sonra program düğümleri karşılık gelen programlar oluşturmak için kullanılır. Bir işlem için programları sorgulandığında programları numaralandırılır, program her düğüm için bir tane.  
  
 Bir program iliştirildiği önce IDE program basit bir açıklamasını gerekir. Bu bilgi programı düğümden elde edilebilir. Program için bağlandıktan sonra programdaki tüm iş parçacıkları listesi gibi daha ayrıntılı bilgi görüntülemek IDE gerekir. Bu bilgiler programından elde edilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Programlar](../../extensibility/debugger/programs.md)   
 [İşlemler](../../extensibility/debugger/processes.md)   
 [Hata ayıklama altyapısı](../../extensibility/debugger/debug-engine.md)   
 [Hata ayıklayıcı kavramları](../../extensibility/debugger/debugger-concepts.md)   
 [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)

