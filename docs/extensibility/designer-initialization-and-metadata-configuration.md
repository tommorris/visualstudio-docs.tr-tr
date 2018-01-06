---
title: "Tasarımcı başlatma ve meta veri yapılandırması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- designers [Visual Studio SDK], initializing
- designers [Visual Studio SDK], configuring metadata
ms.assetid: f7fe9a7e-f669-4642-ad5d-186b2e6e6ec9
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 61624d9926f4d984386f1a8b3fe8a575ce465331
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="designer-initialization-and-metadata-configuration"></a>Tasarımcı başlatma ve meta verileri yapılandırma
Bir tasarımcı veya Tasarımcısı bileşen ile ilişkili meta verileri ve filtre öznitelikleri işlenmesini hangi araçların farklı işlemek için belirli bir tasarımcı tarafından kullanılan tanımlamak üzere uygulamalar için bir mekanizma sağlar <xref:System.Type> nesne (örneğin, veri yapıları sınıfları veya grafik varlıklar), Tasarımcı kullanılabilir olduğunda ve Visual Studio IDE designer'ı desteklemek üzere nasıl yapılandırılır (örnek hangi **araç** kategori veya sekmesinde kullanılabilir).  
  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Tasarımcısı veya tasarımcı bileşenin başlatma denetimi ve meta verilerini bir VSPackage tarafından işlenmesini kolaylaştırmak için çeşitli mekanizmalar sağlar.  
  
## <a name="initializing-metadata-and-configuration-information"></a>Meta verileri ve yapılandırma bilgilerini başlatma  
 İsteğe bağlı olarak yüklenen olduklarından, VSPackages tarafından yüklenmiş olabilir değil [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] bir tasarımcı oluşturmada önce ortamı. VSPackages standart mekanizmasını Tasarımcısı veya Tasarımcısı bileşen yönetmektir oluşturma özelliğini yapılandırmak için bu nedenle, kullanamazsınız bir <xref:System.ComponentModel.Design.IDesignerEventService.DesignerCreated> olay. Bunun yerine, bir VSPackage örneği uygulayan <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> arabirim ve kendisini tasarım yüzeyi uzantıları olarak başvurulan özelleştirmeleri sağlamak için kaydeder.  
  
### <a name="customizing-initialization"></a>Başlatma özelleştirme  
 Bir tasarımcı, bir bileşeni ya da bir tasarımcı yüzeyine özelleştirme içerir:  
  
1.  Tasarımcı meta verileri değiştirme ve etkili bir şekilde belirli bir nasıl değiştirme <xref:System.Type> erişilen veya dönüştürülür.  
  
     Bu genellikle aracılığıyla yapılır <xref:System.Drawing.Design.UITypeEditor> veya <xref:System.ComponentModel.TypeConverter> mekanizmaları.  
  
     Örneğin, <xref:System.Windows.Forms>-tabanlı tasarımcıları başlatılır, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ortam değiştirir <xref:System.Drawing.Design.UITypeEditor> için <xref:System.Web.UI.WebControls.Image> dosya sistemi yerine bit eşlemler elde etmek üzere Kaynak Yöneticisi'ni kullanma tasarımcı ile birlikte kullanılan nesneleri.  
  
2.  Ortam ile Örneğin, olaylara abone olma ya da proje yapılandırma bilgilerini alma tümleştirme. Proje yapılandırma bilgilerini edinmek ve elde ederek olaylarına abone olma <xref:System.ComponentModel.Design.ITypeResolutionService> arabirimi.  
  
3.  Uygun etkinleştirme tarafından kullanıcı ortamını değiştirilmesini **araç** kategorileri veya örneği uygulayarak tasarımcının Uygulanabilirlik kısıtlayarak <xref:System.ComponentModel.ToolboxItemFilterAttribute> tasarımcıya sınıfı.  
  
### <a name="designer-initialization-by-a-vspackage"></a>Bir VSPackage tarafından Tasarımcı başlatma  
 Bir VSPackage tarafından Tasarımcı başlatma işlemesi gerekir:  
  
1.  Bir nesne uygulama oluşturma <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> sınıfı.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> Sınıf hiçbir zaman uygulanan aynı nesne üzerinde <xref:Microsoft.VisualStudio.Shell.Package> sınıfı.  
  
2.  Uygulayan sınıf kaydetmek <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> örneklerini uygulayarak VSPackage'nın Tasarımcısı uzantıları için destek sağlayan olarak <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtensionAttribute>, <xref:Microsoft.VisualStudio.Shell.ProvideObjectAttribute> ve <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> VSPackage'nın uygulaması sağlama sınıfına <xref:Microsoft.VisualStudio.Shell.Package> .  
  
 Herhangi bir tasarımcı veya Tasarımcısı bileşen oluşturulduğunda [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ortamı:  
  
1.  Her kayıtlı tasarım yüzeyi uzantısı Sağlayıcısı'na erişir.  
  
2.  Oluşturur ve her tasarım yüzeyi uzantısı sağlayıcısının bir örneğini başlatır <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> nesnesi  
  
3.  Her tasarım yüzeyi uzantısı sağlayıcının çağırır <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension.OnDesignerCreated%2A> yöntemi veya <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension.OnComponentCreated%2A> yöntemi (gerektiği gibi).  
  
 Uygularken <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> nesne bir VSPackage bir üyesi olarak anlamak önemlidir:  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Ortam hangi meta verileri üzerinden herhangi bir denetimi sağlamaz veya diğer yapılandırma ayarları belirli bir `DesignSurfaceExtension` sağlayıcının değiştirir. İki veya daha fazla mümkündür `DesignSurfaceExtension` aynı Tasarımcı özellik çakışan yollarla kesin olan son değişikliğe sahip değiştirme sağlayıcıları. Hangi değişiklik son uygulanan da belirsiz.  
  
2.  Açıkça uygulaması kısıtlamak mümkündür <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> örneklerini uygulayarak belirli tasarımcıları nesnesine <xref:System.ComponentModel.ToolboxItemFilterAttribute> bu uygulama için. Daha fazla bilgi için **araç** öğesi filtreleme için bkz: <xref:System.ComponentModel.ToolboxItemFilterAttribute> ve <xref:System.ComponentModel.ToolboxItemFilterType>.  
  
## <a name="additional-metadata-provisioning"></a>Ek meta veri sağlama  
 Bir VSPackage Tasarımcısı veya dışında Tasarımcısı Bileşen Yapılandırması tasarım zamanında değiştirebilirsiniz.  
  
 <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> Sınıfı programlı olarak kullanılabilir veya bir tasarımcı sağlayan bir VSPackage uygulanması.  
  
 Örneği <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> sınıfı bir tasarım yüzeyine oluşturulan bileşenleri meta verilerini değiştirmek için kullanılır. Örneğin, biri tarafından kullanılan varsayılan özellik tarayıcısı değiştirme <xref:System.Windows.Forms.CommonDialog> nesnelerle bir özel özellik tarayıcısı.  
  
 Bir örneği tarafından sağlanan değişiklikler <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> VSPackage'nın uygulaması için uygulanan <xref:Microsoft.VisualStudio.Shell.Package> iki kapsamların biri olabilir:  
  
-   Global--için belirli bir bileşenin tüm yeni örnekleri  
  
-   Yerel--geçerli VSPackage tarafından sağlanan bir tasarım yüzeyi oluşturulan bileşen örneği için yalnızca ilgili.  
  
 `IsGlobal` Özelliği <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> VSPackage'nın uygulaması için uygulanan örneği <xref:Microsoft.VisualStudio.Shell.Package> bu kapsamı belirler.  
  
 Öznitelik uygulaması için uygulama <xref:Microsoft.VisualStudio.Shell.Package> ile <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute.IsGlobal%2A> özelliği <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> nesne kümesine `true`, tüm tarayıcı olarak aşağıdaki değişiklikleri [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ortamı:  
  
 `[ProvideDesignerMetadata(typeof(Color), typeof(CustomBrowser),`   `IsGlobal=true`  `)]`  
  
 `internal class MyPackage : Package {}`  
  
 Genel bayrağı ayarlanmışsa `false`, meta veri değişikliği geçerli VSPackage tarafından desteklenen geçerli Tasarımcısı için yerel ise:  
  
 `[ProvideDesignerMetadata(typeof(Color), typeof(CustomBrowser),`   `IsGlobal=false`  `)]`  
  
 `internal class MyPackage : Package {}`  
  
> [!NOTE]
>  Mevcut zaman tasarım yüzeyine yalnızca oluşturma bileşenleri destekler ve bu nedenle yalnızca bileşenleri yerel meta verileri olabilir. Yukarıdaki örnekte, biz bir özelliği değiştirmek çalıştığınız `Color` bir nesnenin özelliği. Varsa `false` için genel bayrağı, geçirilen `CustomBrowser` Tasarımcı aslında hiç bir örneği oluşturduğundan hiçbir zaman görüneceği `Color`. Genel bayrağını ayarlamak `false` denetimleri, zamanlayıcılar ve iletişim kutuları gibi bileşenleri için kullanışlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension>   
 <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtensionAttribute>   
 <xref:System.ComponentModel.ToolboxItemFilterType>   
 [Tasarım zamanı desteği genişletme](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)