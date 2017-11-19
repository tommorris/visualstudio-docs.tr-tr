---
title: "Nasıl yapılır: metin işaretçileri kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - using text markers
ms.assetid: 76eed51c-eecb-4579-823e-13df2f0526b9
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1070a88f1bae27b9ff10fedbf6a383ec30c1ed0e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-text-markers"></a>Nasıl yapılır: metin işaretçileri kullanın
Metin işaretçileri düzenlemek için uygulanabilir bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBuffer> nesnesi.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-apply-text-markers"></a>Metin işaretçileri uygulamak için  
  
1.  Bir örneği elde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> sınıfı.  
  
    > [!NOTE]
    >  Çekirdek Düzenleyici standart metin işaretçileri düzenlemekte olan herhangi bir belgeye otomatik olarak uygular. ve standart metin işaretçileri açıkça uygulamak gerekli olmamalıdır.  
  
2.  Bir işaretçi türü kimliği, ilgilendiğiniz çağırarak işaret elde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> yöntemiyle `GUID` çalışmak istediğiniz metin işaretin.  
  
    > [!NOTE]
    >  Kullanmayın `GUID` VSPackage veya metin işaretçisi sağlayan hizmet.  
  
3.  İşaret türü kimliği elde çağırarak kullanım <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager.GetRegisteredMarkerTypeID%2A> yöntemi çağırmak için bir parametre olarak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> yöntemi veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metnin belirli bir bölgedeki bir metin işaretçisi uygulanacak yöntemi.  
  
#### <a name="to-add-features-to-text-markers"></a>Metin işaretçileri özellikleri eklemek için  
  
1.  Bir metin işaretçisi araç ipuçları, özel bağlam menüsü veya işleyici gibi özel durumlar için ek özellikler eklemek için sahip olması istenebilir. Bunu yapmak için:  
  
2.  Bir nesne uygulama oluşturma <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> arabirimi.  
  
3.  Ek işlevsellik isterseniz, uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientEx>ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClientAdvanced> arabirimlerini uygular aynı nesne üzerinde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> arabirimi.  
  
4.  Geçirmek <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient> çağrısına oluşturma arabirimi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines.CreateLineMarker%2A> yöntemi veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextStream.CreateStreamMarker%2A> metin işaretçisi metnin belirli bir bölgedeki uygulamak için kullanılan yöntem.  
  
5.  Bağlam menüsü destek bir metin işaretçisi bölgeye eklerken menü oluşturmak gereklidir.  
  
     Bir bağlam menüsü bakın oluşturma hakkında daha fazla bilgi için [bağlam menülerini](../extensibility/context-menus.md).  
  
6.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ortam çağırır sağlanan arabirim yöntemleri gibi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.GetTipText%2A> yöntemini veya <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerClient.ExecMarkerCommand%2A> gerektiğinde yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Metin işaretçileri eski API ile kullanma](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Nasıl yapılır: standart metin işaretleyicileri ekleyin](../extensibility/how-to-add-standard-text-markers.md)   
 [Nasıl yapılır: özel metin işaretçileri oluşturma](../extensibility/how-to-create-custom-text-markers.md)   
 [Nasıl yapılır: uygulama hata işaretçileri](../extensibility/how-to-implement-error-markers.md)