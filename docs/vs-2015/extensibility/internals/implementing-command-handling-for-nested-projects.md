---
title: İç içe projeler için işleme komutunu uygulama | Microsoft Docs
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
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea27ea6f1b1ef49174b555fb9b1aae0d4c54dd23
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690026"
---
# <a name="implementing-command-handling-for-nested-projects"></a>İç içe Projeler için Komut İşlemesi Uygulama
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [uygulama komutu işlenirken iç içe projeler için](https://docs.microsoft.com/visualstudio/extensibility/internals/implementing-command-handling-for-nested-projects).  
  
IDE geçirilecek komutları geçirebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> iç içe projeler veya üst projelere arabirimleri filtreleyebilir veya komutları geçersiz kılar.  
  
> [!NOTE]
>  Normalde ana proje tarafından işlenen komutları filtrelenebilir. Gibi komutlar **derleme** ve **Dağıt** tarafından işlenen IDE filtrelenemez.  
  
 Aşağıdaki adımlar komut işleme uygulama işlemi açıklanmaktadır.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-implement-command-handling"></a>Komut işleme uygulamak için  
  
1.  Kullanıcı bir iç içe proje ya da bir düğüm iç içe geçmiş bir projede seçtiğinde:  
  
    1.  IDE çağrıları <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi.  
  
     — veya —  
  
    1.  Çözüm Gezgini'nde, bir kısayol menü komutu gibi bir hiyerarşi penceresinde komut geldiyse IDE çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> projenin üst yöntemi.  
  
2.  Ana proje geçirilecek parametreler inceleyebilirsiniz `QueryStatus`, gibi `pguidCmdGroup` ve `prgCmds`, ana proje komutları filtre olup olmadığını belirlemek için. Ana proje komutları filtrelemek için uygulanmışsa ayarlamanız gerekir:  
  
    ```  
    prgCmds[0].cmdf = OLECMDF_SUPPORTED;  
    // make sure it is disabled  
    prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;  
    ```  
  
     Ana proje döndürmelidir sonra `S_OK`.  
  
     Ana proje komutu filtrelemez varsa, yalnızca döndürmelidir `S_OK`. Bu durumda, IDE alt projeye komutu otomatik olarak yönlendirir.  
  
     Komut alt projeye yönlendirmek ana proje yok. IDE, bu görevi gerçekleştiren...  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Komutlar, menüler ve araç çubukları](../../extensibility/internals/commands-menus-and-toolbars.md)   
 [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)

