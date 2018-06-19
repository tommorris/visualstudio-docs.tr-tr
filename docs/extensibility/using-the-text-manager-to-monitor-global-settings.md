---
title: Genel ayarları izlemek için metin Yöneticisi'ni kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e6c61a6859a2e8d359b2185ce959aa941944380f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31141678"
---
# <a name="using-the-text-manager-to-monitor-global-settings"></a>Genel ayarları izlemek için metin Yöneticisi'ni kullanma
Bir çekirdek Düzenleyici uygularsanız, bu değişiklikleri Düzenleyicisi örneğiniz etkileyebilecek çünkü genel ayarlarına yapılan değişiklikleri izlemeniz gerekir. Metin Yöneticisi tarafından başlatılan olayları dinleyerek değişiklikleri izleyebilirsiniz. Örneğin, çekirdek düzenleyicisinde, kendi belge veri nesnesi gibi bir bileşen davranışını veya görünümünü için genel bir tercih belirttiğinizde metin Yöneticisi bu bilgileri depolar ve tüm etkilenen istemcilere iletişim kurar.  
  
## <a name="text-manager-functions"></a>Metin Yöneticisi işlevleri  
 Metin Yöneticisi ayarları, aşağıdakiler de dahil olmak üzere çeşitli olayları başlatır:  
  
-   Arabellek kaynak kodu denetimi altında olup olmadığı  
  
-   Dosya değişikliği bildirimleri için kaydetme  
  
-   Görünümleri belirli arabelleklerinin ilişkili izlemek nasıl  
  
-   Metin renklendirme tercihleri  
  
-   Alanı Tercihler karşı sekmesi  
  
 Belirli bir dile benzersiz Tercihler metin Yöneticisi tarafından yönetilmeyen. Bu ayarların her dil hizmeti tarafından yönetiliyor olması gerekir.  
  
 Metin Yöneticisi için olay bildirimi tarafından sağlanan <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> arabirimi. Bu arabirimi uygulayan istemciniz üzerinde olayları işlemek için nesne metin Yöneticisi gerçekleşti. Kullanarak bu olayları kaydetme <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> metin Yöneticisi arabiriminde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İçinde çekirdek Düzenleyicisi](../extensibility/inside-the-core-editor.md)   
 [Düzenleyicisi özellikleri](http://msdn.microsoft.com/en-us/bdac940d-1f14-4019-a01f-fd0bb3dc7198)