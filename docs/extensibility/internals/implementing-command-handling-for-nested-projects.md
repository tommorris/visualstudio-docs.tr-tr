---
title: İç içe projeleri için işleme komutu uygulama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, implementing command handling
ms.assetid: 48a9d66e-d51c-4376-a95a-15796643a9f2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f3f02752fad6932bac90597d56f27257e78b84cd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129006"
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
 [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)