---
title: Eski API'sini kullanarak kod Windows özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - code windows
ms.assetid: 5328ab2f-55cb-4680-9744-ec79f55acd1b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8284985003415ef3e723fe735e64481c3666180a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109970"
---
# <a name="customizing-code-windows-by-using-the-legacy-api"></a>Eski API'sini kullanarak kod Windows özelleştirme
Bir veya daha fazla metin görünümlerini destekleyen bir belge pencere nesnesi bir kod penceredir. İlişkili dil hizmette kod penceresini tam özelliklerine bağlıdır. Birden çok belge arabirimi (MDI) modunda kod penceresi MDI alt çerçevesidir.  
  
 Kod windows dil Hizmetleri tarafından denetlenir ve kendi kod Pencere Yöneticisi her dil hizmeti sağlayabilir. Bu kod penceresini dalgalı çizgiler, renklendirme ve daha fazlası gibi kendi adornments eklemek dil hizmeti sağlar. Bir çekirdek penceresi oluşturma hakkında daha fazla bilgi için bkz: [çekirdek düzenleyici kullanarak eski API başlatmasını](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md).  
  
 Bir kod penceresi bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame> metin görünümü ve nesne tarihli adornments nesnesi. Düzenleyici, çekirdek örnek oluşturma sırasında koda oluşturduğunuzda, dil hizmetinizi iliştirebilirsiniz bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> kod penceresine olarak aşağıdaki çizimde gösterilir.  
  
 ![CodeWindow grafiği](../extensibility/media/vscodewindow.gif "vscodewindow")  
Kod penceresi  
  
 Dil hizmeti kodu Pencere Yöneticisi uygular ve açılan çubuğu gibi adornments yönetilmesinden sorumludur. Kod penceresini çağrıları <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> kod penceresini başlatma sırasında yöntemi. Bu çağrısı yapıldığında dil hizmeti açılan çubuğu düğme çubuğu ekleyebilir veya (<xref:Microsoft.VisualStudio.TextManager.Interop.IVsButtonBarClient>) kod penceresine.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 `Customizing Code Windows by Using the Legacy API`  
 Eski API'sini kullanarak kod windows özelleştirileceği açıklanmaktadır.  
  
 [Nasıl yapılır: başka bir düzenleyici bir düzenleyicide ana bilgisayar](../extensibility/how-to-host-an-editor-in-another-editor.md)  
 Bir düzenleyici penceresini içinde ikinci bir düzenleyici barındırmak açıklanmaktadır.  
  
 [Nasıl yapılır: yangın Düzenleyicisi odağı kaybettiğinde olayları](../extensibility/how-to-fire-events-when-the-editor-loses-focus.md)  
 Bir belge görünümü belge veri nesnesine eklenecek açıklanmaktadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsCodeWindow>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextBuffer>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView>   
 [Eski API kullanarak çekirdek Düzenleyici örneği](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)   
 [Eski API kullanarak getirip metin görünümü erişme](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)