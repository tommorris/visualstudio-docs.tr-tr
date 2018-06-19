---
title: Otomasyon seçenekleri sayfaları desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], automation support
- automation [Visual Studio SDK], creating Tools Options pages
ms.assetid: 0b25b82c-7432-4e0a-9e84-350269ba8260
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d27ad706d4203a3573a734a1cd11b19e3c9df6a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128578"
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
 [Proje Nesnelerini Kullanıma Sunma](../../extensibility/internals/exposing-project-objects.md)