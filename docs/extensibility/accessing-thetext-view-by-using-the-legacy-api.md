---
title: Eski API kullanarak getirip metin görünümü erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text view
ms.assetid: 8f751f72-c972-4be3-84ee-19c281e02e25
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7aa879847e87b1a0372e2a8e9a3a6ec712041a56
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="accessing-thetext-view-by-using-the-legacy-api"></a>Eski API kullanarak getirip metin görünümü erişme
Metni metin arabelleğinde depolanan metin sunumu görülmektedir. Metin görünümü aşağıdaki bölümde gösterildiği gibi eski API kullanarak erişebilirsiniz.

## <a name="text-view-object"></a>Metin görünümü nesnesi
 Her görünüm kendi metin arabelleğini ilişkilendirilir ve görünüm veri arabelleği bir penceredir. Aşağıdaki diyagramda tarafından temsil edilen metin görünüm nesnenin anahtar arabirimler gösterilir <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>.

 ![Visual Studio metin görünümü nesnesi](../extensibility/media/vstextview.gif "vstextview") metin görünümü nesnesi

 Görünüm metni arabellekte sunan bir yoludur. Görünümde gördüğünüz metin arabelleği tam bir temsili olmaması sözcük kaydırma ve anahat gibi özellikler içerir.

 Diğer hizmetlerin veya gelen komutları kesecek ve görünüm üzerlerinde davranır önce bunları üzerinde hareket işlemleri bir görünümünü sağlar. Bunu yapmak için en yaygın hizmeti bir dil hizmetidir. Bir dil hizmeti, örneğin, özel girintileme işlemi hakkındaki diğer davranışını veya araç ipuçları sağlamak ENTER tuşuna komutu müdahale gerekebilir.

## <a name="adding-functionality-to-the-text-view"></a>Metin görünümü işlevsellik ekleme
 Belirli tuş vuruşları işleyerek metin görünümü davranışını özelleştirebilirsiniz. Tuş vuruşları kesmeye uygulamanız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter> , nesne üzerinde ve komut hedefi sağlayın (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) İzleyici ve ıntercept komutları.

 Metin görünümü için komut filtreleri sıralı mimarisi kullanır. Yeni komut filtreleri (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> nesneleri) için dizisi çağrılarak eklenir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> yöntemi.

 Metin görünümü için olay bildirimini kullanarak sağlanır <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewEvents> arabirimi. Metin görünümü değişiklikler bildirim almak için istemci nesneniz üzerinde bu arabirimi uygular. Metin görünümü bu arabirime kullanarak kullanıma <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> görünümden değişikliklerle ilgili bildirim almak için metin görünümü arabirimde.

## <a name="see-also"></a>Ayrıca Bkz.

- [Eski API kullanarak görünüm ayarlarını değiştirme](../extensibility/changing-view-settings-by-using-the-legacy-api.md)
- [Genel ayarları izlemek için metin Yöneticisi'ni kullanma](../extensibility/using-the-text-manager-to-monitor-global-settings.md)