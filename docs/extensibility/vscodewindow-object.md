---
title: VSCodeWindow nesne | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2de0998a3d89c1af3e18fa60aa3f8511716f6165
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="vscodewindow-object"></a>VSCodeWindow nesnesi
Bir kod, bir veya daha fazla metin görünümü, genellikle dahil edebileceğiniz bir özelleştirilmiş belge penceresidir <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> nesnesi.  
  
 Mimari, kod içinde bir pencere çerçevesi olan bir belge penceresidir. İşlevsellik, kod yalnızca bir belge ek özelliklerle penceresidir. Birden çok belge arabirimi (MDI) modunda kod penceresi MDI alt çerçevesidir. Daha fazla bilgi için bkz: [eski API'yi kullanarak kod Windows özelleştirme](../extensibility/customizing-code-windows-by-using-the-legacy-api.md).  
  
 Aşağıdaki tablo arabirimler içerir <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow> nesnesi.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>|Bir genel benzersiz tanımlayıcı (GUID) tanımlayan bir hizmeti bulmak için bir genel erişim mekanizma sağlar.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Bir veya daha fazla kod görünümleri içeren birden çok belge arabirimi (MDI) alt temsil eder.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|Pencere çerçevesi doldurur.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>   
 [Şekiller Düzenle](http://msdn.microsoft.com/en-us/f08872bd-fd9c-4e36-8cf2-a2a2622ef986)