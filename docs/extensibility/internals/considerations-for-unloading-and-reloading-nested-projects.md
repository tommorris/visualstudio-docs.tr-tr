---
title: "Yüklemeyi kaldırma ve yeniden değerlendirmeleri iç içe projeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf34a3fe708a6ecab200262224da395b9fa37ecb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Yüklemeyi kaldırma ve yeniden iç içe geçmiş projeleri için ilgili önemli noktalar
İç içe proje türleri uyguladığınızda, kaldırma ve projeleri yeniden ek adımları gerçekleştirmeniz gerekir. Çözüm olayları dinleyicileri doğru şekilde bildirmek için doğru şekilde yükseltmeniz gerekir `OnBeforeUnloadProject` ve `OnAfterLoadProject` olaylar.  
  
 Bu şekilde bu olayları oluşturma gerekir nedenlerinden biri olan kaynak kodu denetimi öğeleri sunucudan silmek ve varsa bunları geri bir şey yeni ekleyin (SCC) istiyor musunuz bir `Get` SCC işlemi. Bu durumda, yeni bir dosya SCC dışında yüklenir ve kaldırma ve farklı olması durumunda tüm dosyaları yeniden yüklemek zorunda. SCC çağrıları `ReloadItem`. Projeyi silin ve yeniden uygulayarak yeniden oluşturmak için uygulamanız bu çağrının olan `IVsFireSolutionEvents` çağırmak için `OnBeforeUnloadProject` ve `OnAfterLoadProject`. Bu uygulama gerçekleştirdiğinizde, SCC proje geçici olarak silinmiş ve yeniden eklenmesi, bilgilendirilir. Bu nedenle, projeyi gerçekte sunucudan silinir ve yeniden eklenmesi gibi SCC projede çalışmaz.  
  
## <a name="reloading-projects"></a>Projeleri yeniden yükleme  
 İç içe geçmiş projeleri yeniden yükleme desteklemek için uygulamanız <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> yöntemi. Uygulamanızda `ReloadItem`, iç içe geçmiş projeleri kapatın ve sonra yeniden oluşturun.  
  
 Genellikle bir projeyi yeniden yüklendiğinde, IDE başlatır <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> ve `M:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject(Microsoft.VisualStudio.Shell.Interop.IVsHierarchy,Microsoft.VisualStudio.Shell.Interop.IVsHierarchy)` olaylar. Ancak, silinir ve yeniden iç içe geçmiş projeleri için ana proje IDE işlemi başlatır. Ana proje çözümü olayları oluşturmaz ve IDE başlatma işleminin hakkında hiçbir bilgi olduğundan olayları oluşmaz.  
  
 Bu işlem, ana proje çağrıları işlemek için `QueryInterface` üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> kapalı arabirim <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> arabirimi. `IVsFireSolutionEvents`yükseltmek için IDE söyleyin işlevleri sahip `OnBeforeUnloadProject` iç içe proje kaldırın ve ardından yükseltmek için olay `OnAfterLoadProject` olay aynı projeyi yeniden yükleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 [İç içe geçme projeleri](../../extensibility/internals/nesting-projects.md)