---
title: 'Nasıl yapılır: yerleşik Colorable öğelerini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a6cf51516677aeca71dba269bcdd132e0830b6b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129689"
---
# <a name="how-to-use-built-in-colorable-items"></a>Nasıl yapılır: yerleşik Colorable öğelerini kullanma
Yerleşik colorable öğeleri kullanmadan önce ilk tümleşik geliştirme ortamı (IDE), bu durumda, kendi özel colorable öğeler sağlama değil sinyal gerekir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> nesneleri. Dil hizmeti için bir kayıt defteri girdisi ayarlayarak bunu yapabilirsiniz.  
  
### <a name="to-use-built-in-colorable-items"></a>Yerleşik colorable öğeleri kullanmak için  
  
1.  HKEY_LOCAL_MACHINE\VisualStudio altında\\*X.Y*\Languages\Language Hizmetleri\\*dil adı*, burada *X.Y* sürümü[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve *dil adı* adı olarak adlandırılan bir DWORD kayıt defteri girdisinin değeri, dilinin oluşturmak `RequestStockColors`.  
  
2.  Ayarlama `RequestStockColors` kayıt defteri girdisinin değeri 1.  
  
     Kayıt defteri girdisi, Renklendirici 's oluşturduktan sonra <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> yöntemi üyelerini kullanma <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> Düzenleyicisi tarafından kullanılacak renk öznitelikleri dizisi doldurmak için numaralandırması.  
  
    > [!NOTE]
    >  Özel colorable öğeler sağlıyorsanız, bu kayıt defteri girdisi ayarlı değil. Daha fazla bilgi için bkz: [özel Colorable öğeleri](../../extensibility/internals/custom-colorable-items.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sözdizimi özel düzenleyicilerde renklendirme](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Eski dil hizmetinde renklendirme sözdizimi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Sözdizimi renklendirmesi uygulama](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Özel Colorable öğeler](../../extensibility/internals/custom-colorable-items.md)   
 [Eski dil hizmeti kaydetme](../../extensibility/internals/registering-a-legacy-language-service2.md)