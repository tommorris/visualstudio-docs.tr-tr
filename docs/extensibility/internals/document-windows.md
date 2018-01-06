---
title: Belge Windows | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio SDK, document windows
ms.assetid: 50081d48-987f-43db-8bf9-51b7cf76e9c0
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 03e61b80aaf4c5c8b0e25f5b2a4a42f13d75d305
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="document-windows"></a>Belge pencereleri
Visual Studio'da bir *belge penceresine* birden çok belge arabirimi (MDI) penceresi ile ilişkili bir Çerçeveli alt penceredir. Belge pencereleri tipik olarak görüntü ve kaynak kodu ya da metin değişikliği için kullanılır, ancak diğer işlev türleri de barındırabilir. Belge pencereleri:  
  
-   Böylece aynı anda birden çok dosya görüntülenebilir MDI üst ayrı yatay veya dikey sekme gruplarındaki düzenlenebilir.  
  
-   MDI üst herhangi bir sırada yerleştirilmiş.  
  
-   Ücretsiz olarak kaydırılmış.  
  
-   Diğer MDI pencereleri sekmesinde sırada bağlanır.  
  
 Komutları gruplandırma için bir belge penceresinde sekme kısayol menüsünde yerleşen ve kayan bulunabilir.  
  
 Visual Studio'da pencere davranış hakkında daha fazla bilgi için bkz: [pencere düzenlerini özelleştirme](../../ide/customizing-window-layouts-in-visual-studio.md).  
  
## <a name="document-window-implementation"></a>Belge penceresi uygulama  
 Belge pencereleri bir düzenleyici uygulayarak oluşturulur. <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> Arabirimi belge pencereleri bir düzenleyici örneği bir parçası olarak oluşturur. Daha fazla bilgi için bkz: [eski arabirimleri Düzenleyicisi'nde](../../extensibility/legacy-interfaces-in-the-editor.md).  
  
> [!NOTE]
>  Geriye doğru sağlamak ve bir penceresinde gezinme noktaları iletmek için uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsBackForwardNavigation> arabirimi. Metin düzenleyici metin işaretçileri belgesinde gezinme noktalarını tanımlamak için kullanır.  
  
## <a name="the-running-document-table"></a>Çalışan belge tablosu  
 IDE çalışan belge tablosu (RDT) her belge penceresine durumunu izlemek için kullanır. RDT aracılığıyla hangi belge windows olayları gibi bir çözüm kapatıldığında veya bir dosya düzenlendiğinde, bildirilir mekanizmadır. Daha fazla bilgi için bkz: [çalıştıran Belge tablosu](../../extensibility/internals/running-document-table.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Belge Yüklemesi](../../extensibility/internals/delayed-document-loading.md)