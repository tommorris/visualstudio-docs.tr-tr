---
title: "İç içe projeleri için işleme komutu uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a71da10ee4473f3fb542e0ce0e03891d60b75d34
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-command-handling-for-nested-projects"></a>İç içe geçmiş projeleri için işleme komutu uygulama
IDE geçirilecek komutları geçirebilirsiniz <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> iç içe geçmiş projeleri veya üst projeleri arabirimlerine filtreleyebilir veya komutlarını geçersiz kıl.  
  
> [!NOTE]
>  Normalde üst projesi tarafından işlenen komutları filtrelenebilir. Gibi komutlar **yapı** ve **dağıtma** tarafından işlenen IDE filtrelenemez.  
  
 Aşağıdaki adımlar komut işleme uygulamaya yönelik işlem açıklar.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-implement-command-handling"></a>Komut işleme uygulamak için  
  
1.  Kullanıcı bir iç içe proje ya da bir düğüm iç içe geçmiş bir projede seçtiğinde:  
  
    1.  IDE çağrıları <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> yöntemi.  
  
     — veya —  
  
    1.  Komut bir hiyerarşi penceresinde, Çözüm Gezgini'nde, bir kısayol menü komutu gibi geldiyse IDE çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A> projenin üst yöntemi.  
  
2.  Ana proje geçirilecek parametreler inceleyebilirsiniz `QueryStatus`, gibi `pguidCmdGroup` ve `prgCmds`ana proje komutları filtre olup olmadığını belirlemek için. Komutları filtrelemek için ana proje uygulanmışsa ayarlamanız gerekir:  
  
    ```  
    prgCmds[0].cmdf = OLECMDF_SUPPORTED;  
    // make sure it is disabled  
    prgCmds[0].cmdf &= ~MSOCMDF_ENABLED;  
    ```  
  
     Ana proje döndürmelidir sonra `S_OK`.  
  
     Ana proje komutu filtre uygulamadığında varsa, bunu yalnızca döndürmelidir `S_OK`. Bu durumda, IDE otomatik olarak alt projeye komutu yönlendirir.  
  
     Alt projeye komutu yönlendirmek ana proje yok. IDE bu görevi gerçekleştiren...  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>   
 [Komutları, menüleri ve araç çubukları](../../extensibility/internals/commands-menus-and-toolbars.md)   
 [İç içe geçme projeleri](../../extensibility/internals/nesting-projects.md)