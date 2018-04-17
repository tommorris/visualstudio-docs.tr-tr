---
title: Diller bulunan | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: bbf2c63a66ba76b65d1caec2c5eed006d57fca0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="contained-languages"></a>Kapsanan dilleri

*Bulunan diller* diğer diller tarafından bulunan diller. Örneğin, HTML biçiminde [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sayfalar içerebilir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] komut dosyaları. HTML ve komut dosyası dili için IntelliSense, renklendirme ve diğer düzenleme özellikleri sağlamanın .aspx dosyası Düzenleyicisi'ni çift dil mimari gereklidir.

## <a name="implementation"></a>Uygulama

Kapsanan diller için uygulamak için gereken en önemli arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirimi. Bu arabirim, birincil dili içinde barındırılan herhangi bir dil tarafından uygulanır. Dil hizmetin Renklendirici, metin Görünümü Filtresi ve birincil dili hizmeti kimliği için erişim sağlar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> Oluşturmanızı sağlayan bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirimi. Aşağıdaki adımlar bir kapsanan dil uygulamak nasıl gösterir:

1.  Kullanım `QueryService()` dil hizmeti kimliği ve arabirim Kimliğini almak için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.

2.  Oluşturmak için bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirim, çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> yöntemi. Geçirmek bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> arabirimi, bir veya daha fazla [kimlikleri öğesi](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>)ve bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> arabirimi.

3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> Metin arabelleği Düzenleyicisi nesnedir, arabirimi ikincil dil arabellek birincil dosyasında konumlara eşlemek için gereken temel hizmetleri sağlar.

     Örneğin, bir tek .aspx dosyası birincil dosya ASP, HTML ve içerdiği tüm kodu içerir. Ancak, ikincil arabellek ikincil arabellek geçerli kod dosyası yapmak için bir sınıf tanımları birlikte yalnızca kapsanan kod içerir. Arabellek Düzenleyici bir arabellek düzenlemeleri diğer Eşgüdümleme işini gerçekleştirir.

4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> Birincil dili olan yöntemi hangi metin arabelleğini içinde karşılık gelen metin ikincil arabelleği eşlenmiş arabellek Düzenleyicisi söyler.

     İçinde bir dizi dil geçirir <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> şu anda yalnızca bir birincil ve ikincil bir aralık içeren yapısı.

5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> Yöntemi ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> yöntem birincil ikincil arabellek ve tersi yönde eşlemesinden sağlar.