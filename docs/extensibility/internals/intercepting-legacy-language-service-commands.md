---
title: Eski dil hizmeti komutları kesintiye uğratan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 38f025e9dab6f93d87660a59421cbd778c92165a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="intercepting-legacy-language-service-commands"></a>Kesintiye uğratan eski dil hizmeti komutları
İle [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], metin görünümü başka türlü işleyebilirsiniz dil hizmeti ıntercept komutları olabilir. Metin görünümü değil yönetiyor dile özgü davranışı için kullanışlıdır. Bir veya daha fazla komut filtre metni görünümüne dil hizmetinizden ekleyerek bu komutları ele geçirebilir.  
  
## <a name="getting-and-routing-the-command"></a>Komut Yönlendirme ve alma  
 Bir komut filtresi bir <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> belirli karakter dizileri veya anahtar komutları izler nesnesi. Birden fazla komut filtresi bir tek bir metin görünümü ile ilişkilendirebilirsiniz. Her metin görünümü komuta zincirini filtreleri tutar. Yeni bir komut filtre oluşturduktan sonra uygun metin görünümü için zinciri için filtresini ekleyin.  
  
 Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> yöntemi <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> zincire komutu filtre eklemek için. Çağırdığınızda <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A>, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] komutu filtre işlemiyor komutları geçirmek başka bir komut filtre döndürür.  
  
 Komut işleme için aşağıdaki seçenekler vardır:  
  
-   Komutu işlemek ve ardından sonraki komut filtresi açın komut zincirinde geçirin.  
  
-   Komut işleme ve komut sonraki komut filtresi açın geçmeyin.  
  
-   Komutunu işleyemez, ancak sonraki komut filtresi açın komutu geçirin.  
  
-   Komut yoksay. Geçerli filtre işlemez ve sonraki filtre açın geçmeyin.  
  
 Dil hizmetinizin hangi komutları hakkında tanıtıcı bilgi için bkz: [dil hizmeti filtreleri için önemli komutları](../../extensibility/internals/important-commands-for-language-service-filters.md).