---
title: Hata ayıklayıcı olayları çağırma | Microsoft Docs
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
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 86c48d072baa53cf3f8ba0a6d903021e6c396afa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684465"
---
# <a name="calling-debugger-events"></a>Hata Ayıklayıcısı Olaylarını Çağırma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklayıcısı olaylarını çağırma](https://docs.microsoft.com/visualstudio/extensibility/debugger/calling-debugger-events).  
  
Hata ayıklama oturumları, olayları belirli bir sırayla oluşur.  
  
## <a name="discussion"></a>Tartışma  
 Hata ayıklama altyapısı (DE) ve oturum hata ayıklama Yöneticisi (SDM) arasındaki çağrıların desenini anlamak için tipik hata ayıklama oturumunda gerçekleşen olaylara arama sırası şunları gösterir:  
  
1.  [Ekleme ve programdan ayırma](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Hata ayıklayıcı başlatılıyor](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Program sonlandırma](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Bir kesme noktası oluşturma](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Ne zaman bir kesme noktası bağlar veya ilişkisiz olma](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Kesme noktası hataları](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Kesme noktasına ulaşma](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Kesme noktasını silme](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Kesme moduna girme](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Kesme modunda Adımlama](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Kesme modunda ifade değerlendirme](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Özel durum işleme](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)

