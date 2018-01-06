---
title: "Komut yönlendirme algoritmasını | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, routing
- command routing
ms.assetid: 998b616b-bd08-45cb-845f-808efb8c33bc
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e1463fe22d4b08933112ca1ad0cf28f38a4e102c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="command-routing-algorithm"></a>Komut yönlendirme algoritması
Visual Studio komutları bir dizi farklı bileşen tarafından işlenir. Komutları geçerli seçime göre en içteki bağlamdan en dıştaki (genel olarak da bilinir) bağlamına yönlendirilir. Daha fazla bilgi için bkz: [kullanılabilirlik](../../extensibility/internals/command-availability.md).  
  
## <a name="order-of-command-resolution"></a>Komut çözümleme sırasını  
 Komutları aşağıdaki komut bağlam düzeylerini geçirilir:  
  
1.  Eklentiler: Ortam önce var olan eklentileri komutuna sunar.  
  
2.  Öncelik komutlar: Bu komutları kullanarak kayıtlı <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>. Bunlar her komutu Visual Studio için çağrılır ve kayıtlı olan sırada çağrılır.  
  
3.  Bağlam menüsü komutları: bağlam menüsünde bulunan bir komut varsayılan tipik yönlendirme için bağlam menüsüne ve bundan sonra sağlanan komut hedefi için sunulur.  
  
4.  Araç komut hedefleri ayarlayın: Bu komut hedefleri çağırdığınızda kayıtlı <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell4.SetupToolbar2%2A>. `pCmdTarget` Parametresi `null`. Değilse `null`, bu komut hedefi ayarladığınız araç çubuğunda bulunan herhangi bir komut güncelleştirmek için kullanılır. Kabuk araç ayarı sonra pencere çerçevesi olarak geçirir `pCmdTarget` komutlarını araç akışınız pencere çerçevesi aracılığıyla yapılan tüm güncelleştirmeler bile böylece olmadığı odakta.  
  
5.  Araç penceresi: Aracı genellikle uygulama windows <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> arabirimi, aynı zamanda uygulamalıdır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> böylece araç penceresi etkin pencereyi olduğunda Visual Studio komut hedefi alabilir arabirim. Ancak, araç penceresi, odak ise **proje** penceresi, sonra komutu için yönlendirilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> seçili öğeleri ortak üst arabirimi. Bu seçim birden çok proje yayılırsa komutu yönlendirilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution> hiyerarşisi. <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> Arabirimi içeren <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A> sunucuda karşılık gelen komutları benzer yöntemleri <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi.  
  
6.  Belge penceresine: komut, .vsct dosyasında ayarlanan RouteToDocs bayrağı varsa, Visual Studio komut hedefi da belge görünüm nesnesi üzerinde örneği arar bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> arabirimi veya belge bir nesne örneği (genellikle bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>arabirimi veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> arabirimi). Belge görünüm nesnesi komutu desteklemiyorsa, Visual Studio komutu yönlendirir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> döndürüldü arabirim. (İsteğe bağlı bir arabirim belge veri nesneleri için budur.)  
  
7.  Geçerli hiyerarşi: geçerli hiyerarşi etkin belge penceresini veya seçili hiyerarşi sahibi proje olabilir **Çözüm Gezgini**. Visual Studio arar <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> geçerli ya da etkin hiyerarşide uygulanan arabirim. Hiyerarşi bir proje öğesi, belge penceresine odağa sahip olsa bile hiyerarşi etkin olduğunda, geçerli olan komutlar desteklemelidir. Ancak, yalnızca geçerli komutları **Çözüm Gezgini** sahip odak gerekir desteklenir kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> arabirimi ve kendi <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>yöntemleri.  
  
     **Kesme**, **kopya**, **Yapıştır**, **silmek**, **yeniden adlandırma**, **girin**ve **DoubleClick** komutları özel işleme gerektirir. Nasıl yönetileceği hakkında bilgi için **silmek** ve **kaldırmak** hiyerarşileri komutlarda bkz <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler> arabirimi.  
  
8.  Genel: bir komut tarafından yukarıda açıklanan bağlamları işlenmiş değil, Visual Studio uygulayan bir komut sahip VSPackage yönlendirmek çalışır <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi. VSPackage zaten yüklü değil, Visual Studio çağırdığında yüklenmez <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi. Yalnızca VSPackage yüklenen <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> yöntemi çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Komut Tasarımı](../../extensibility/internals/command-design.md)