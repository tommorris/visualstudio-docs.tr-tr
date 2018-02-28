---
title: "Nasıl yapılır: bağlantılı geri alma Yönetimi'ni kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - linked undo management
ms.assetid: af5cc22a-c9cf-45b1-a894-1022d563f3ca
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7a025cdfc14eb39dad7ea2bc72a69f1f260fb583
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-linked-undo-management"></a>Nasıl yapılır: bağlantılı geri alma Yönetimi'ni kullanın
Bağlantılı geri alma aynı anda birden çok dosya aynı düzenlemeleri geri olanak tanır. Örneğin, bir üst bilgi dosyası ve bir Visual C++ dosyası gibi birden çok program dosyaları arasında eşzamanlı metin değişiklikleri, bir bağlantılı geri alma işlemi olur. Bağlantılı geri alma özelliği, geri alma yöneticisi ortamı uygulamasına oluşturulur ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager> , bu özellik işlemek olanak tanır. Bağlantılı geri alma birlikte tek geri birim olarak kabul edilmesi için ayrı geri yığınları bağlayabilirsiniz bir ana geri birim tarafından uygulanır. Kullanarak bağlantılı geri alma yordamı aşağıdaki bölümde ayrıntılı olarak gösterilmiştir.  
  
### <a name="to-use-linked-undo"></a>Bağlantılı geri alma kullanmak için  
  
1.  Çağrı `QueryService` üzerinde `SVsLinkedUndoManager` gösteren bir işaretçi almak için `IVsLinkedUndoTransactionManager`.  
  
2.  Çağırarak ilk ana bağlantılı geri alma birim oluşturun <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.OpenLinkedUndo%2A>. Bu bağlantılı geri alma yığınlar halinde gruplandırılır için geri alma yığınlarının kümesi için başlangıç noktası ayarlar. İçinde `OpenLinkedUndo` yöntemi de gerekir katı veya kesin olmayan bağlantılı geri alma isteyip istemediğinizi belirtin. Kesin olmayan bağlantılı geri alma davranışını bağlantılı geri alma eşdüzey belgelerle bazılarını kapatın ve hala diğer bağlı bırakın geri kendi yığınları üzerinde Eşdüzey anlamına gelir. Tüm bağlantılı geri alma eşdüzey yığınları birlikte ya da hiç geri olmak zorunda katı bağlantılı geri alma davranışını belirtir. Sonraki bağlı geri yığınları çağırarak eklemek [IOleUndoManager::Add](http://msdn.microsoft.com/library/windows/desktop/ms680135) yöntemi.  
  
3.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager.CloseLinkedUndo%2A> geri dönmek için tüm biri olarak bağlantılı geri alma birimleri yedekleyin.  
  
    > [!NOTE]
    >  Bir düzenleyicide bağlantılı geri alma Yönetimi uygulamak için geri alma yönetim ekleyin. Bağlantılı geri alma yönetimini uygulama ile ilgili daha fazla bilgi için bkz: [nasıl yapılır: uygulama geri Yönetim](../extensibility/how-to-implement-undo-management.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>   
 [IOleParentUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms682151)   
 [IOleUndoUnit](http://msdn.microsoft.com/library/windows/desktop/ms678476)   
 [Nasıl yapılır: uygulama geri alma yönetimi](../extensibility/how-to-implement-undo-management.md)