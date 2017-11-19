---
title: "Genel ayarları izlemek için metin Yöneticisi'ni kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9687e4f0be16fb42f13c6f9dd20a2cb39be50cd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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