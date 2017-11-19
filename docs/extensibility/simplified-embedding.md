---
title: "Katıştırma Basitleştirilmiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], custom - simple view embedding
ms.assetid: f1292478-a57d-48ec-8c9e-88a23f04ffe5
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4315a55b74d938576572b0630f5dca553643a24
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="simplified-embedding"></a>Basitleştirilmiş katıştırma
Basitleştirilmiş katıştırma etkin bir düzenleyicide kendi belge görünüm nesnesi (diğer bir deyişle, yapılmış bir alt) için üst öğe zaman [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane> arabirimi onun penceresi komutları işlemek için uygulanır. Basitleştirilmiş katıştırma düzenleyicileri etkin denetimleri barındıramaz. Basitleştirilmiş katıştırma ile bir düzenleyici oluşturmak için kullanılan nesneler aşağıdaki çizimde gösterilmektedir.  
  
 ![Basitleştirilmiş katıştırılmış Düzenleyici grafiği](../extensibility/media/vssimplifiedembeddingeditor.gif "vsSimplifiedEmbeddingEditor")  
Basitleştirilmiş katıştırma ile Düzenleyicisi  
  
> [!NOTE]
>  Bu çizimde, yalnızca nesnelerin `CYourEditorFactory` nesne bir standart dosya tabanlı Düzenleyicisi oluşturmak için gereklidir. Özel bir düzenleyici oluşturuyorsanız, uygulamanız gerekmez <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>, düzenleyicinizi olasılıkla özel Kalıcılık mekanizması vardır. İçin özel olmayan düzenleyicileri, ancak bunu yapmanız gerekir.  
  
 Basitleştirilmiş katıştırma ile bir düzenleyici oluşturmak için uygulanan tüm arabirimler bulunan `CYourEditorDocument` nesnesi. Ancak, birden çok belge veri görünümleri desteklemek için ayrı veri ve görünüm nesneler üzerine arabirimler aşağıdaki tabloda gösterildiği gibi bölün.  
  
|Arabirim|Arabirim konumu|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|---------------|---------------------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Görüntüle|Üst pencere bağlantı sağlar.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Görüntüle|Komutları işler.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>|Görüntüle|Durum çubuğu güncelleştirmeleri sağlar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxUser>|Görüntüle|Etkinleştirir **araç** öğeleri.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEvents>|Veri|Dosya değişiklik olduğunda bildirim gönderir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Veri|Bir dosya türü için Farklı Kaydet özelliğini etkinleştirir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2>|Veri|Belge kalıcılığını etkinleştirir.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDocDataFileChangeControl>|Veri|Yeniden yükleme tetikleme gibi dosya değişikliği olaylar gizleme sağlar.|