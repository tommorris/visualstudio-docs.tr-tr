---
title: 'Nasıl yapılır: durum çubuğunda güncelleştirme | Microsoft Docs'
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
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 97b96023682d1acfda5aa0c47c07169b558c7569
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686286"
---
# <a name="how-to-update-the-status-bar"></a>Nasıl yapılır: durum çubuğunda güncelleştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: durum çubuğunda güncelleştirme](https://docs.microsoft.com/visualstudio/extensibility/how-to-update-the-status-bar).  
  
**Durum çubuğu** bir denetim çubuğuna bir veya daha fazla durum metin satırlarını ya da göstergeleri içeren pek çok uygulama penceresi sonunda bulunur.  
  
### <a name="to-update-the-status-bar"></a>Durum çubuğu güncelleştirmek için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> düzenleyiciniz sağlayan bir form görünümü ve kod görünümü gibi her tek görünüm nesnesinde (DocView).  
  
2.  IDE çağırdığında <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>, bilgilerini **durum çubuğu** yöntemleri çağırarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>.  
  
    > [!NOTE]
    >  IDE çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> yalnızca belge penceresinin başlangıçta etkinleştirildiğinde. Belge penceresinin etkin olduğu süre kalanı için güncelleştirmeniz gerekir **durum çubuğu** Düzenleyicisi değişikliklerinizi durumu bilgileri.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 A **durum çubuğu** dört ayrı alanları içerir:  
  
-   Durum metni  
  
-   İlerleme çubuğu  
  
-   Animasyonlu simgesi  
  
-   Düzenleyici bilgileri  
  
 Daha fazla bilgi için [durum çubukları](http://msdn.microsoft.com/library/fcbc5029-1aab-4e14-adf7-419038a4935e).  
  
 IDE otomatik olarak çağıran <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> yöntemi, <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> belge penceresinin etkinleştirildiğinde, uygulama.  
  
 VSPackage'ı uygulayan, durum çubuğundaki durum metni güncelleştirmekten sorumludur. Durum metin alanı boş metin olarak ayarlanmışsa "Hazır" Bu dizeye IDE sıfırlar ("") boşta kalma zaman.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Durum Çubukları](http://msdn.microsoft.com/library/fcbc5029-1aab-4e14-adf7-419038a4935e)

