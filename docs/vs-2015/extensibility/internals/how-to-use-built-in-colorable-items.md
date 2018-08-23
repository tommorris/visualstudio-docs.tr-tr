---
title: 'Nasıl yapılır: yerleşik renklendirilebilir öğeleri kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 20ed9b5424363eceec8cf4c3c5275a3a937a7003
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629215"
---
# <a name="how-to-use-built-in-colorable-items"></a>Nasıl yapılır: yerleşik renklendirilebilir öğeleri kullanma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: yerleşik renklendirilebilir öğeleri kullanma](https://docs.microsoft.com/visualstudio/extensibility/internals/how-to-use-built-in-colorable-items).  
  
Yerleşik renklendirilebilir öğeleri kullanmadan önce öncelikle tümleşik geliştirme ortamı (IDE), bu durumda, kendi özel renklendirilebilir öğeler sağlamıyorsunuz sinyal gerekir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> nesneleri. Dil hizmeti bir kayıt defteri anahtarını ayarlayarak bunu yapabilirsiniz.  
  
### <a name="to-use-built-in-colorable-items"></a>Yerleşik renklendirilebilir öğeleri kullanmak için  
  
1.  HKEY_LOCAL_MACHINE\VisualStudio altında\\*X.Y*\Languages\Language Hizmetleri\\*dil adı*burada *X.Y* sürümüdür[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ve *dil adı* adı adlı bir DWORD kayıt defteri girdisinin değeri, dili, oluşturma `RequestStockColors`.  
  
2.  Ayarlama `RequestStockColors` kayıt defteri girdisinin değeri 1.  
  
     Kayıt defteri girişinin, uygulamanızın Renklendirici oluşturduktan sonra <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> yöntemi üyelerinin kullanabilir <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> renk öznitelikleri ' Düzenleyicisi tarafından kullanılmak üzere bir dizi doldurmak için sabit listesi.  
  
    > [!NOTE]
    >  Özel renklendirilebilir öğeler sağlıyorsanız bu kayıt defteri girdisi ayarlamayın. Daha fazla bilgi için [özel renklendirilebilir öğeler](../../extensibility/internals/custom-colorable-items.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel düzenleyicilerde söz dizimi renklendirmesi](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [Eski dil hizmetinde söz dizimi renklendirmesi](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [Söz dizimi renklendirmesi uygulama](../../extensibility/internals/implementing-syntax-coloring.md)   
 [Özel renklendirilebilir öğeler](../../extensibility/internals/custom-colorable-items.md)   
 [Eski dil hizmeti kaydediliyor](../../extensibility/internals/registering-a-legacy-language-service2.md)

