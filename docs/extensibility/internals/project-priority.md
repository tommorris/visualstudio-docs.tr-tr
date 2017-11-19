---
title: "Proje öncelik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: projects [Visual Studio SDK], opening items
ms.assetid: 9f707592-2fb6-4f75-9269-f6d4700a998e
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 51ed8cd351a306c3992b4b6c9fcc2231a90085f3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="project-priority"></a>Proje önceliği
Bir proje öğesi genellikle yalnızca bir proje çözümdeki üyesidir. Bu nedenle, IDE kolayca hangi proje öğesini açmak için kullanılan belirleyebilirsiniz. Ancak, bir madde birden fazla projesinin bir üyesi ise, IDE öğesini açmak için en iyi proje belirlemek için bir öncelik düzenini kullanır.  
  
 Aşağıdaki liste, proje Öncelik düzenini gösterir:  
  
-   IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject2.IsDocumentInProject%2A> belge proje üyesi olup olmadığını belirlemek için çözümdeki her proje için yöntem.  
  
-   Belge projesinin bir üyesi ise, proje önceliğine sahip, proje, bu belge işleme göre atar yanıt verir. Örneğin, bir dil proje kendi dil kaynak dosyaları için yüksek önceliğe sahip yanıt veriyor, ancak kendi derleme işleminin bir parçası kullanılmayan bir tanınmayan bir dosya türü için daha düşük bir öncelik verir.  
  
-   Bir belge için projeye özgü özel düzenleyiciler veya tasarımcıları sağlayın projeleri de yüksek bir öncelik alır.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.VSDOCUMENTPRIORITY> Numaralandırması öncelik değerleri belge sağlar.  
  
-   En yüksek öncelikli belirtir proje belgeyi açmak için bağlam verilir. İki proje önceliği eşittir değerler döndürürse, etkin proje tercih edilir. Belgeyi açabilir çözümdeki proje yanıt verirse, IDE belge çeşitli dosyalar projede koyar. Daha fazla bilgi için bkz: [çeşitli dosyaları proje](../../extensibility/internals/miscellaneous-files-project.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çeşitli dosyalar proje](../../extensibility/internals/miscellaneous-files-project.md)   
 [Nasıl yapılır: açık belgeler için düzenleyicileri açın](../../extensibility/how-to-open-editors-for-open-documents.md)   
 [Proje ve proje öğesi şablonları ekleme](../../extensibility/internals/adding-project-and-project-item-templates.md)