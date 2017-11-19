---
title: "Aşağı açılan çubuğu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - drop-down bar
ms.assetid: 4bb621bd-72f5-43d5-916f-9f66617da049
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2f5da476bb9b54b536cb296112d578574822e410
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="drop-down-bar"></a>Aşağı açılan çubuğu
Aşağı açılan çubuğu kod penceresinin en üstünde sağlanır ve iki açılan listeleri içerir.  
  
## <a name="drop-down-bar-interfaces"></a>Aşağı açılan çubuğu arabirimleri  
 İçinde [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)], örneğin, aşağı açılan çubuğu için listeleri içerir [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] öğeleri ve [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] öğeleri üye işlevleri aşağıdaki resimde gösterildiği gibi.  
  
 ![Açılan &#45; aşağı çubukları](../extensibility/media/vsdropdown_bar.gif "vsDropdown_bar")  
Aşağı açılan çubuğu  
  
 Aşağı açılan çubuğu uygularken, birincil önem dört arabirimi vardır:  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient>  
  
     Aşağı açılan çubuğu içerik yerleştirmek için bu arabirimi uygular. Her bir açılan birleşimini düz metin veya Süslü metin içerebilir (kalın, alt çizgi veya italik), pencere metin yazı tipi renklendirme veya çıkışı gri yazı tipi renklendirme olabilir ve isteğe bağlı olarak küçük bir bit eşlem açılan öğesinin yanındaki sağlayabilir. Benzer şekilde <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> arabirimi, bit eşlem görüntüleri görüntü listelerinde sağlanır. Her açılan birleşimi farklı resim listesi olabilir; Bununla birlikte, her görüntü listesi aynı yükseklikte görüntülerini içermesi gerekir. Ayrıca, kullanarak <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarClient.GetComboTipText%2A> yöntemi, her birleşim için bir araç ipucu sağlayabilir.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager>  
  
     Bu arabirim oluşturmak veya kod penceresi açılır çubuğu yok etmek için çağırın. Bu arabirim, aşağı açılan çubuğu zaten bir kod penceresine çağırarak ekli olup olmadığını belirlemek için de kullanılabilir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> yöntemi. Çağrı <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> gelen <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBar>  
  
     Bu arabirim aşağı açılan çubuğunda doğrudan iletişim kurmak için çağırın. Bu arabirim açılan yenilemeye zorlamak için kullanabileceğiniz içeriği çubuk veya liste kutuları birinde seçimini değiştirmek için.  
  
-   <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents>  
  
     Kayıtlı olmadığını `ShowDropdownBarOption` ardından kod Pencere Yöneticisi dil hizmeti kayıt defteri anahtarında, aşağı açılan çubuğu görüntülenip görüntülenmeyeceğini ilgili kullanıcı tercihlerini ile eşitlemek için bu olay izlemeniz gerekir. Bu seçenek Dil hizmeti anahtarınızı kaydetmez sonra açılan çubuğunu gösterme veya gizleme seçeneğini devre dışı bırakıldı **seçenekleri** menüsü.  
  
## <a name="attaching-a-drop-down-bar-to-a-code-window"></a>Aşağı açılan çubuğu kod penceresine ekleme  
 Oluşturulduğunda açılan çubuğu kod penceresine eklemek için bir dil hizmeti açılır menüsünü iliştirin çubuk ne zaman <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager.AddAdornments%2A> yöntemi çağrılır. Çağrı, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.GetDropdownBar%2A> yöntemi gösteren açılan çubuğu zaten var, çağrı sonra olduğunu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager.AddDropdownBar%2A>. Erişim için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsDropdownBarManager> arabirim, çağrı <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> gelen <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow> işaretçi döndürdü, ne zaman, <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager> uygulama bağlı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski API'sini kullanarak kod Windows özelleştirme](../extensibility/customizing-code-windows-by-using-the-legacy-api.md)   
 [Eski dil hizmeti gezinti çubuğunda desteği](../extensibility/internals/support-for-the-navigation-bar-in-a-legacy-language-service.md)