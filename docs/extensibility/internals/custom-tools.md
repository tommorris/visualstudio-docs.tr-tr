---
title: Özel Araçlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, custom tools
- tools [Visual Studio], custom
- custom tools
ms.assetid: d669f154-9b23-48b6-b9f6-7419c8dd61a6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5f215cfbd5113377e7a98439976a7f44215eee02
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31128890"
---
# <a name="custom-tools"></a>Özel Araçlar
*Özel Araçlar* bir aracı projesinde bir öğesiyle ilişkilendirme ve dosya kaydedilmiş olduğunda bu aracı olanak tanır. Belirli özel araçlar bazen olarak bilinir *tek dosya oluşturucuları*, sık verilerden ve kod oluşturma çevirmenler uygulamak için kullanılır. Örneğin, tek dosya oluşturucuları oluşturma [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] kaynak kodu .settings ve .resx dosyaları dışında. Oluşturulan kaynak kodu .settings ve .resx dosyaları verilerde kesin türü belirtilmiş erişmenizi sağlar. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] Ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] proje türleri destek özel araçları; [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] proje türleri desteklemez. Kendi proje türleri özel araçlar da destekler.  
  
 Özel araçlardır uygulamak kayıtlı bileşenler `IVsSingleFileGenerator` arabirimi.  
  
 Özel araçlar ile ilişkili bir `ProjectItem` arabirim nesne ve tasarımcıları ve editörler gibi. Özel bir araç tarafından temsil edilen dosyayı alır bir `ProjectItem` olarak giriş ve dosya adı tarafından sağlanan yeni bir dosya Yazar `DefaultExtension` yöntemi.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Tek Dosya Oluşturucular Ekleme](../../extensibility/internals/implementing-single-file-generators.md)  
 Nasıl kullanılacağını açıklar <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator> özel bir araç uygulamak için arabirim.  
  
 [Tek Dosya Oluşturucuları Kaydetme](../../extensibility/internals/registering-single-file-generators.md)  
 Tüm kayıt defteri girişleri için açıklamalar için özel bir araç sağlar.  
  
 [Türleri Görsel Tasarımcıların Kullanımına Sunma](../../extensibility/internals/exposing-types-to-visual-designers.md)  
 Nasıl proje sistemleri için destek oluşturulan erişim sınıfları ve türleri olan görsel tasarımcılar geçici taşınabilir yürütülebilir (PE) dosyalar ile sağlayabilirsiniz açıklanmaktadır.  
  
 [Proje Öğesinin Özelliğini Kalıcı Yapma](../../extensibility/persisting-the-property-of-a-project-item.md)  
 Proje dosyasında bir kaynak dosyanın yazarı gibi bir proje öğesi özelliği kalıcı gösterilmektedir.  
  
## <a name="reference"></a>Başvuru  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>  
 Hakkında ayrıntılar sağlar <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>, hangi dönüştüren tek bir giriş dosyası tek bir çıktı dosyasına derlenmiş veya bir projeye eklendi.  
  
 <xref:EnvDTE.ProjectItem>  
 Açıklar `ProjectItem` proje bir öğeyi temsil eden arabirim.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.DefaultExtension%2A>  
 Hakkında ayrıntılar sağlar `DefaultExtension` çıkış dosyasının adı verilen dosya adı uzantısını alır yöntemi.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Projeleri Genişletme](../../extensibility/extending-projects.md)  
 Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projeler ve çözümler kod dosyaları ve kaynak dosyaları ve kaynak denetimi nasıl düzenlemek için.