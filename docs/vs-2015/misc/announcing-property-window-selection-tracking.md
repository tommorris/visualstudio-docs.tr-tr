---
title: Özellik penceresi seçimi izleme ile tanışın | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], property pages support
- property pages, tracking selection
- Properties window, tracking selection
- selection, tracking
- editors [Visual Studio SDK], Properties window support
ms.assetid: a7536f82-afd7-4894-9a60-84307fb92b7e
caps.latest.revision: 13
manager: douge
ms.openlocfilehash: bb2f2ceb7ed7faa3165f2346a0e0d14de1371166
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688329"
---
# <a name="announcing-property-window-selection-tracking"></a>İzleme özelliği pencere seçimi ile tanışın
Çalışmak istiyorsanız **özellikleri** penceresi veya **özelliği** , örneğin, form, metin ve istediğiniz özelliklerini görmek nasıl eksiksiz bilinmesini olmalıdır sonra bir seçim sayfaları, Seçimi koordine edin. Örneğin, tek bir seçim veya birden çok seçimin sahip olup olmadığını bilmeniz gerekir. Daha sonra IDE kullanarak seçimi türünüzü (tek veya birden çok) duyurmaktan gerek <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection> arabirimi. Bu arabirim tarafından gerekli olan bilgileri sağlar **özellikleri** penceresi.  
  
### <a name="to-announce-selection-to-the-environment"></a>Seçimi ortamına duyurmaktan  
  
1.  Çağrı `QueryInterface` için <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>.  
  
    1.  Bunu yapmak için site işaretçiyi oluşturulduğunda görünüme iletilen kullanın.  
  
    2.  Çağrı `QueryService` için görünümünden `SID_STrackSelection` hizmeti.  
  
         Bu bir işaretçi döndürür <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> seçiminizi her değiştiğinde yöntemi ve uygulayan bir nesne işaretçisi geçişine <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer>.  
  
     Seçimi kapsayıcı nesne tek veya birden çok seçimin kullanabilirsiniz ve seçim bilgileri içeren bir `IDispatch` nesne. Çağırma <xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection.OnSelectChange%2A> yöntemi **özellikleri** seçimi değiştirildi penceresi. **Özellikleri** penceresi ardından kullanan nesneler üzerinde <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer> tek veya birden çok seçimin olup oluşmuş ve gerçek nesnenin seçimleri nelerdir belirlemek için.  
  
     Bir çoklu seçim belirtirseniz sonra **özellikleri** penceresini nesneler için ortak özellikler arasında kesişimini bulur. Bir tek nesne seçimi belirtirseniz sonra **özellikleri** penceresi tüm bir nesne için özellikleri görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellikleri genişletme](../extensibility/internals/extending-properties.md)   
 [Özellik Sayfaları](../extensibility/internals/property-pages.md)