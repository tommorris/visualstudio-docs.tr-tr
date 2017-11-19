---
title: "Özel Araçlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7c198065c72f1e6eaa0722de562abe6079f88aa1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="custom-tools"></a>Özel Araçlar
*Özel Araçlar* bir aracı projesinde bir öğesiyle ilişkilendirme ve dosya kaydedilmiş olduğunda bu aracı olanak tanır. Belirli özel araçlar bazen olarak bilinir *tek dosya oluşturucuları*, sık verilerden ve kod oluşturma çevirmenler uygulamak için kullanılır. Örneğin, tek dosya oluşturucuları oluşturma [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] kaynak kodu .settings ve .resx dosyaları dışında. Oluşturulan kaynak kodu .settings ve .resx dosyaları verilerde kesin türü belirtilmiş erişmenizi sağlar. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] Ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] proje türleri destek özel araçları; [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] proje türleri desteklemez. Kendi proje türleri özel araçlar da destekler.  
  
 Özel araçlardır uygulamak kayıtlı bileşenler `IVsSingleFileGenerator` arabirimi.  
  
 Özel araçlar ile ilişkili bir `ProjectItem` arabirim nesne ve tasarımcıları ve editörler gibi. Özel bir araç tarafından temsil edilen dosyayı alır bir `ProjectItem` olarak giriş ve dosya adı tarafından sağlanan yeni bir dosya Yazar `DefaultExtension` yöntemi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Tek dosya oluşturucuları uygulama](../../extensibility/internals/implementing-single-file-generators.md)  
 Nasıl kullanılacağını açıklar <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> özel bir araç uygulamak için arabirim.  
  
 [Tek dosya oluşturucuları kaydetme](../../extensibility/internals/registering-single-file-generators.md)  
 Tüm kayıt defteri girişleri için açıklamalar için özel bir araç sağlar.  
  
 [Görsel tasarımcılar türlerine gösterme](../../extensibility/internals/exposing-types-to-visual-designers.md)  
 Nasıl proje sistemleri için destek oluşturulan erişim sınıfları ve türleri olan görsel tasarımcılar geçici taşınabilir yürütülebilir (PE) dosyalar ile sağlayabilirsiniz açıklanmaktadır.  
  
 [Bir proje öğesi özelliği kalıcı yapma](../../extensibility/persisting-the-property-of-a-project-item.md)  
 Proje dosyasında bir kaynak dosyanın yazarı gibi bir proje öğesi özelliği kalıcı gösterilmektedir.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>  
 Hakkında ayrıntılar sağlar <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, hangi dönüştüren tek bir giriş dosyası tek bir çıktı dosyasına derlenmiş veya bir projeye eklendi.  
  
 <xref:EnvDTE.ProjectItem>  
 Açıklar `ProjectItem` proje bir öğeyi temsil eden arabirim.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>  
 Hakkında ayrıntılar sağlar `DefaultExtension` çıkış dosyasının adı verilen dosya adı uzantısını alır yöntemi.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Projeleri genişletme](../../extensibility/extending-projects.md)  
 Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projeler ve çözümler kod dosyaları ve kaynak dosyaları ve kaynak denetimi nasıl düzenlemek için.