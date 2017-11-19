---
title: "Kaynak denetim paketleri için model | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], model
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a8dacc0a3dfc230085c7575960238711d16d1ef8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="model-for-source-control-packages"></a>Kaynak denetim paketleri için modeli
Aşağıdaki modeli kaynak denetim uygulaması örneği temsil eder. Modeldeki uygulamanız gereken arabirimleri ve çağırmalısınız Ortam Hizmetleri bakın. Tüm hizmetler gibi gerçekten hizmeti aracılığıyla elde belirli bir arabirim yöntemleri çağırın. Sınıf adları, kaynak denetimi nasıl gerçekleştirildiği görmeyi kolaylaştırmak için tanımlanır.  
  
 ![SCC &#95; TUP örnekler](../../extensibility/internals/media/scc_tup.gif "SCC_TUP")  
Örnek kaynak denetimi projesi  
  
## <a name="interfaces"></a>Arabirimler  
 Aşağıdaki tabloda gösterilen arabirimleri listesini kullanarak Visual Studio'da yeni proje türlerinizi için kaynak denetimi uygulayabilirsiniz.  
  
|Arabirim|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|---------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Projeler ve bunlar kaydedin veya değiştirme (olumsuz) dosyaları önce düzenleyiciler tarafından çağrılır. Bu arabirim kullanılarak erişilir <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> hizmet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|Projeleri ekleyin, kaldırın veya bir dosya veya dizin yeniden adlandırma izni istemek için tarafından çağrılır. Bu arabirim, onaylanmış bir Ekle kaldırdığınızda veya eylem yeniden adlandırmak ortamı tamamlandıktan bildirmek için göre projeleri olarak da adlandırılır. Kullanılarak erişilir <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> hizmet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|Projeleri eklediğinizde bildirilmesi kaydeder herhangi bir varlık tarafından uygulanan, yeniden adlandırın veya bir dosya veya dizin kaldırın. Olay bildirimi için kaydolmaya çağrısı <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Kaynak denetimi paketiyle kaydetmek ve kaynak denetimi durumu hakkında bilgi edinmek için projeler tarafından çağrılır. Bu arabirim kullanılarak erişilir <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> hizmet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Proje dosyaları hakkında bilgi için kaynak denetimi isteklere yanıt verecek şekilde ve kaynak proje dosyası için gerekli denetim ayarlarını almak için tarafından uygulanır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 [Kaynak denetimi destekleme](../../extensibility/internals/supporting-source-control.md)