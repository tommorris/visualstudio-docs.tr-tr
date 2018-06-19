---
title: VSCodeWindow nesne | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- VSCodeWindow
helpviewer_keywords:
- views [Visual Studio SDK], VSCodeWindow object
- VsCodeWindow object
ms.assetid: cf5fe926-e784-4098-bc01-cac49c7c55c6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c2b1d85eea974e67ae37f8d4d5bfd7aa0069e92b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138648"
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