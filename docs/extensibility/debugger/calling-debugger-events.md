---
title: Hata ayıklayıcı olayları çağırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3960d464b1a6d44fb77eba23cd518fea1f2e5a39
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100033"
---
# <a name="calling-debugger-events"></a>Arama hata ayıklayıcı olayları
Hata ayıklama oturumları, olayları belirli bir sırada oluşur.  
  
## <a name="discussion"></a>Tartışma  
 Hata ayıklama altyapısı (DE) ve oturum hata ayıklama Yöneticisi'ni (SDM) arasındaki aramaları desenini anlamak için tipik bir hata ayıklama oturumunda meydana gelen olayları arama sırasını şunları gösterir:  
  
1.  [Ekleme ve bir programa ayırma](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Hata ayıklayıcıyı başlatma](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Program sonlandırma](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Bir kesme noktası oluşturma](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Ne zaman bir kesme noktası bağlar veya ilişkisiz olma](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Kesme noktası hataları](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Bir kesme noktası çıkma](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Bir kesme noktası siliniyor](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Kesme modu girme](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Kesme modunda Adımlama](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Kesme modunda ifade değerlendirme](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Özel durum işleme](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)