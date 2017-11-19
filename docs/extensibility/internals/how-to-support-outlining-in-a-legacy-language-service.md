---
title: "Nasıl yapılır: Destek eski dil hizmetinde anahat oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], collapse to definitions command
- language services, supporting Collapse to Definitions command
- hidden text, Collapse to Definitions command
ms.assetid: bb6e74c3-93e4-4ef7-afc7-1c9b342f083b
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e08ca6d5a670bb2c1a0f0073920c753add50322c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-support-outlining-in-a-legacy-language-service"></a>Nasıl yapılır: Destek eski dil hizmetinde anahat oluşturma
Anahat oluşturma genişletmek veya metnin farklı bölgelerde daraltmak için kullanılır. Anahat oluşturma yolu kullanılır farklı diller tarafından farklı şekilde tanımlanabilir. Daha fazla bilgi için bkz: [anahat](../../ide/outlining.md).  
  
 Eski dil hizmetler bir VSPackage bir parçası olarak uygulanır, ancak dil hizmet özellikleri uygulamak için daha yeni MEF uzantıları kullanmak için bir yoludur. Anahat oluşturma uygulamak için yeni yolu hakkında daha fazla bilgi için bkz: [izlenecek yol: anahat oluşturma](../../extensibility/walkthrough-outlining.md).  
  
> [!NOTE]
>  Yeni Düzenleyicisi API mümkün olan en kısa sürede kullanmaya başlamanızı öneriyoruz. Bu dil hizmetinizin performansını ve yeni Düzenleyicisi özelliklerden yararlanmak sağlar.  
  
 Bu komut için dil Hizmetinizi desteklemek nasıl gösterir.  
  
### <a name="to-support-outlining"></a>Anahat oluşturma desteklemek için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage> dil hizmeti nesnesi üzerinde.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> yeni anahat bölgeler eklemek için anahat geçerli oturum nesnesi üzerinde.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Bir kullanıcı seçtiğinde **Daralt için tanımları** üzerinde **anahat** menüsü, IDE çağrıları <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningCapableLanguage.CollapseToDefinitions%2A> dil hizmetinizi üzerinde.  
  
 Bu yöntem çağrıldığında, IDE içinde başarılı bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines> işaretçisi (gösteren bir işaretçi bir metin arabelleği) ve bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession> (geçerli anahat oturum için bir işaretçi).  
  
 Çağırabilirsiniz <xref:Microsoft.VisualStudio.TextManager.Interop.IVsOutliningSession.AddOutlineRegions%2A> yöntemi bu bölgelerde belirterek birden çok anahat bölgeler için `rgOutlnReg` parametresi. `rgOutlnReg` Parametresi bir <xref:Microsoft.VisualStudio.TextManager.Interop.NewOutlineRegion> yapısı. Bu işlem belirli bir bölgenin genişletilmiş veya daraltılmış olduğunu gibi gizli bölge farklı özelliklerini belirtmenize olanak sağlar.  
  
> [!NOTE]
>  Yeni satır karakterlerini gizleme hakkında dikkatli olun. Gizli metni ilk satırını başından son son yeni satır karakteri görünür bırakarak son satırın bir bölümde karakter genişletmeniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: eski dil hizmetindeki gizli metin desteği sağlar](../../extensibility/internals/how-to-provide-hidden-text-support-in-a-legacy-language-service.md)   
 [Nasıl yapılır: eski dil hizmetindeki genişletilmiş anahat desteği sağlar](../../extensibility/internals/how-to-provide-expanded-outlining-support-in-a-legacy-language-service.md)