---
title: "Nasıl yapılır: Bul uygulamak ve değiştirme mekanizması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c971d4565c95cab23e683a1a4f20c75ebea81b8f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>Nasıl yapılır: Bul uygulamak ve mekanizmasını değiştirin
Visual Studio bulun ve değiştirin kullanmanın iki yolu sağlar. Bir metin görüntü kabuğa geçip arama, vurgulama ve değiştirerek metin işleyen çalışmasına izin yoludur. Bu, kullanıcıların birden çok metin yayılma belirtmesine izin verir. Alternatif olarak, VSPackage bu işlevselliği kontrol edebilirsiniz. Her iki durumda da Kabuğu olan geçerli hedefi ve tüm açık belgeleri hedefleri hakkında bildirmeniz gerekir.  
  
### <a name="to-implement-findreplace"></a>Bulma/değiştirme uygulamak için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> çerçeve özellikleri tarafından döndürülen nesne birini arabirimde <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> veya <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>. Özel bir düzenleyici oluşturuyorsanız, özel bir düzenleyici sınıfı bir parçası olarak bu arabirimi uygulamalıdır.  
  
2.  Kullanım <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> yöntemi düzenleyicinizi desteklediği seçenekleri belirtin ve görüntü metin arama uygulayan olup olmadığını belirtmek için.  
  
     Düzenleyicinizi görüntü metin arama destekliyorsa, uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.  
  
     Aksi takdirde uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.  
  
3.  Öğesini uygularsanız <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> yöntemler çağrılarak arama görevlerinizi basitleştirebilecek <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>