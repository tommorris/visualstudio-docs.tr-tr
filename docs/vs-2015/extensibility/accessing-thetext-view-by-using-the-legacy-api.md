---
title: Eski API'yi kullanarak erişimcisinde görünümü erişme | Microsoft Docs
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
- editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9a65dcf8c67169e26fa508dfa7043717ea919df7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694815"
---
# <a name="accessing-thetext-view-by-using-the-legacy-api"></a>Eski API'yi kullanarak erişen erişimcisinde görüntüle
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [eski API'yi kullanarak erişimcisinde görünümü erişme](https://docs.microsoft.com/visualstudio/extensibility/accessing-thetext-view-by-using-the-legacy-api).  
  
Metin arabelleğinde depolanan metin metin görünümünü gösterir. Aşağıdaki bölümde gösterildiği gibi eski API'yi kullanarak metin görünümünü erişebilirsiniz.  
  
## <a name="text-view-object"></a>Metin görünümü nesnesi  
 Her görünüm kendi metin arabelleği ile ilişkilendirilir ve görünüm arabellekteki veriler üzerinde bir penceredir. Aşağıdaki diyagram tarafından temsil edilen metin view nesnesinin anahtar arabirimler gösterilir <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>.  
  
 ![Visual Studio metin View nesnesinin](../extensibility/media/vstextview.gif "vstextview")  
Metin görünümü nesnesi  
  
 Görünüm arabellekteki metni sunan bir yoludur. Görünümü'nde gördüklerinizi arabellekteki metni tam bir temsilini olmaması sözcük kaydırma ve anahat gibi özellikler içerir.  
  
 Diğer hizmetler ve gelen komutları kesecek ve görünümü üzerinde çalışır önce bunlar üzerinde harekete işlemlerin bir görünüm sağlar. Bunu yapmak için en yaygın hizmeti, bir dil hizmetidir. Dil hizmeti, örneğin, girintilendirme özel davranış veya araç ipuçları sağlamak ENTER tuşuna komutunu ıntercept gerekebilir.  
  
## <a name="adding-functionality-to-the-text-view"></a>Metin görünümü işlevsellik ekleme  
 Özel tuş vuruşları işleyerek metin görünümü davranışını özelleştirebilirsiniz. Tuş vuruşları kesmeye uygulamanız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> , nesneniz üzerinde ve bir komut hedefi belirtin (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) İzleyici ve ıntercept komutları.  
  
 Metin görünümünü komut filtreleri için sıralı mimarisi kullanır. Yeni komut filtreleri (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> nesneleri) çağırarak sıraya eklenen <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> yöntemi.  
  
 Olay bildirimi için metin görünümünü kullanarak sağlanan `T:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents` arabirimi. Metin görünümünü değişiklikleri bildirim almak için istemci nesneniz üzerinde bu arabirimi uygulayın. Bu arabirim için metin görünümü kullanılarak sunan <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> görünümden değişiklikleri bildirim almak için metin görünümü arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski API'yi kullanarak görünüm ayarlarını değiştirme](../extensibility/changing-view-settings-by-using-the-legacy-api.md)   
 [Genel ayarlar izlemek için metin Yöneticisi'ni kullanma](../extensibility/using-the-text-manager-to-monitor-global-settings.md)

