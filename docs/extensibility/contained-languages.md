---
title: Diller bulunan | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8adf63eed436b5724fcdb32d86ffc7bfb2c1a40
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="contained-languages"></a>Kapsanan dilleri
*Bulunan diller* diğer diller tarafından bulunan diller. Örneğin, HTML biçiminde [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] sayfalar içerebilir [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] komut dosyaları. HTML ve komut dosyası dili için IntelliSense, renklendirme ve diğer düzenleme özellikleri sağlamanın .aspx dosyası Düzenleyicisi'ni çift dil mimari gereklidir.  
  
## <a name="implementation"></a>Uygulama  
 Kapsanan diller için uygulamak için gereken en önemli arabirim <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirimi. Bu arabirim, birincil dili içinde barındırılan herhangi bir dil tarafından uygulanır. Dil hizmetin Renklendirici, metin Görünümü Filtresi ve birincil dili hizmeti kimliği için erişim sağlar <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> Oluşturmanızı sağlayan bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirimi. Aşağıdaki adımlar bir kapsanan dil uygulamak nasıl gösterir:  
  
1.  Kullanım `QueryService()` dil hizmeti kimliği ve arabirim Kimliğini almak için <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.  
  
2.  Çağrı <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> yöntemi oluşturmak için bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> arabirimi. Geçirmek bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> arabirimi, bir öğe kimliği (bir veya daha fazlasının <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_NIL>, <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>, veya <xref:Microsoft.VisualStudio.VSConstants.VSITEMID_SELECTION>) ve bir <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> arabirimi.  
  
3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> Metin arabelleği Düzenleyicisi nesnedir, arabirimi ikincil dil arabellek birincil dosyasında konumlara eşlemek için gereken temel hizmetleri sağlar.  
  
     Örneğin, bir tek .aspx dosyası birincil dosya ASP, HTML ve içerdiği tüm kodu içerir. Ancak, ikincil arabellek ikincil arabellek geçerli kod dosyası yapmak için bir sınıf tanımları birlikte yalnızca kapsanan kod içerir. Arabellek Düzenleyici bir arabellek düzenlemeleri diğer Eşgüdümleme işini gerçekleştirir.  
  
4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> Birincil dili olan yöntemi hangi metin arabelleğini içinde karşılık gelen metin ikincil arabelleği eşlenmiş arabellek Düzenleyicisi söyler.  
  
     İçinde bir dizi dil geçirir <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> şu anda yalnızca bir birincil ve ikincil bir aralık içeren yapısı.  
  
5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> Yöntemi ve <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> yöntem birincil ikincil arabellek ve tersi yönde eşlemesinden sağlar.