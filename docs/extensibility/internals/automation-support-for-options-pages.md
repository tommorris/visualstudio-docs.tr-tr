---
title: "Otomasyon seçenekleri sayfaları desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8ca9031e623ec7009d4f489931871f093f4c05d5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="automation-support-for-options-pages"></a>Seçenekler sayfaları için Otomasyon desteği
VSPackages özel sağlayabilir **seçenekleri** iletişim kutuları için **Araçları** (Araçlar Seçenekler sayfaları) menüde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ve bunları otomasyon modeli için kullanılabilir hale getirebilirsiniz.  
  
## <a name="tools-options-pages"></a>Araçlar Seçenekler sayfaları  
 Oluşturmak için bir **Araçlar Seçenekler** sayfasında, bir VSPackage VSPackage'nın uygulaması aracılığıyla ortamına döndürülen bir kullanıcı denetimi uygulama sağlamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> yöntemi (veya yönetilen kod için <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> yöntem).  
  
 İsteğe bağlı, ancak bu yeni sayfa otomasyon modeli aracılığıyla erişmesine izin vermek için kesinlikle önerilir. Aşağıdaki adımlarda size bunu yapabilirsiniz:  
  
1.  Genişletme <xref:EnvDTE._DTE.Properties%2A> IDispatch türetilmiş nesnenin uygulama nesnesi.  
  
2.  Uygulaması dönmek <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> yöntemi (veya yönetilen kod için <xref:Microsoft.VisualStudio.Shell.Package.GetAutomationObject%2A> yöntemi) IDispatch türetilmiş nesne için.  
  
3.  Bir Otomasyon tüketici çağırdığında <xref:EnvDTE._DTE.Properties%2A> özel bir yöntemi **seçeneği** özellik sayfası, ortam kullanan <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetAutomationObject%2A> özel elde etmek için yöntemi **Araçlar Seçenekler** sayfanın Otomasyon uygulaması.  
  
4.  VSPackage Otomasyon nesnesinin sonra her sağlamak için kullanılan <xref:EnvDTE.Property> tarafından döndürülen <xref:EnvDTE._DTE.Properties%2A>.  
  
 Özel Araçlar Seçenekler sayfası uygulayan bir örnek için bkz: [VSSDK örnekleri](http://aka.ms/vs2015sdksamples).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje nesneleri gösterme](../../extensibility/internals/exposing-project-objects.md)