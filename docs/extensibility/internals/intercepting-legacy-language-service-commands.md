---
title: "Eski dil hizmeti komutları kesintiye uğratan | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- commands, intercepting language service
- language services, intercepting commands
ms.assetid: eea69f03-349c-44bb-bd4f-4925c0dc3e55
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 73524ce47dfea2d30e44e51e97bf584a95a86482
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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