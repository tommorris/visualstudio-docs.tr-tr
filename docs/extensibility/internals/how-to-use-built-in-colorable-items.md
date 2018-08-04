---
title: 'Nasıl yapılır: yerleşik renklendirilebilir öğeleri kullanma | Microsoft Docs'
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
ms.openlocfilehash: 658b024a57912bf96a7988363f2bf363e9cb1f0a
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2018
ms.locfileid: "39512622"
---
# <a name="how-to-use-built-in-colorable-items"></a>Nasıl yapılır: yerleşik renklendirilebilir öğeleri kullanma
Yerleşik renklendirilebilir öğeleri kullanmadan önce öncelikle tümleşik geliştirme ortamı (IDE), bu durumda, kendi özel renklendirilebilir öğeler sağlamıyorsunuz sinyal gerekir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> nesneleri. Dil hizmeti bir kayıt defteri anahtarını ayarlayarak bunu yapabilirsiniz.  
  
## <a name="to-use-built-in-colorable-items"></a>Yerleşik renklendirilebilir öğeleri kullanmak için  
  
1.  Altında **HKEY_LOCAL_MACHINE\VisualStudio\\< X.Y > \Languages\Language Hizmetleri\\< dil adı\>** burada \<X.Y > sürümüdür [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve \<Dil adı > adı adlı bir DWORD kayıt defteri girdisinin değeri, dili, oluşturma **RequestStockColors**.  
  
2.  Ayarlama **RequestStockColors** için kayıt defteri girdisinin değeri *1*.  
  
     Kayıt defteri girişinin, uygulamanızın Renklendirici oluşturduktan sonra <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> yöntemi üyelerinin kullanabilir <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> renk öznitelikleri ' Düzenleyicisi tarafından kullanılmak üzere bir dizi doldurmak için sabit listesi.  
  
    > [!NOTE]
    >  Özel renklendirilebilir öğeler sağlıyorsanız bu kayıt defteri girdisi ayarlamayın. Daha fazla bilgi için [özel renklendirilebilir öğeler](../../extensibility/internals/custom-colorable-items.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Özel düzenleyicilerde söz dizimi renklendirmesi](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Eski dil hizmetinde söz dizimi renklendirmesi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Söz dizimi renklendirmesi uygulama](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Özel renklendirilebilir öğeler](../../extensibility/internals/custom-colorable-items.md)   
 [Eski dil hizmeti kaydedin](../../extensibility/internals/registering-a-legacy-language-service2.md)