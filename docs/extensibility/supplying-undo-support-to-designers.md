---
title: Geri alma tasarımcıları için destek sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- designers [Visual Studio SDK], undo support
ms.assetid: 43eb1f14-b129-404a-8806-5bf9b099b67b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5fc289426c2560e978819efcd8eaf17e56b224a8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144888"
---
# <a name="supplying-undo-support-to-designers"></a>Tasarımcılar geri alma desteği sağlama
Tasarımcıları, düzenleyiciler gibi genellikle böylece kullanıcılar kendi son değişiklikler code öğesi değiştirirken çevirebilirsiniz geri alma işlemleri desteklemesi gerekir.  
  
 Visual Studio'da uygulanan çoğu tasarımcıları otomatik olarak ortamı tarafından sağlanan geri desteğine sahip.  
  
 Geri alma özelliğini desteklemek için gereken Tasarımcı uygulamaları:  
  
-   Özet temel sınıf uygulayarak geri yönetimi sağlar <xref:System.ComponentModel.Design.UndoEngine>  
  
-   Sağlar kalıcılığını ve CodeDOM destek uygulayarak <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService> ve <xref:System.ComponentModel.Design.IComponentChangeService> sınıfları.  
  
 Kullanarak tasarımcıları yazma hakkında daha fazla bilgi için [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], bkz: [genişletme tasarım zamanı desteği](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Varsayılan geri alma altyapısı tarafından sağlar:  
  
-   Sağlama, Yönetim uygulamaları aracılığıyla geri <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> ve <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit> sınıfları.  
  
-   Kalıcılığı ve varsayılan CodeDOM desteğini sağladığını <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> ve <xref:System.ComponentModel.Design.IComponentChangeService> uygulamaları.  
  
## <a name="obtaining-undo-support-automatically"></a>Geri alma desteği otomatik olarak alma  
 Oluşturulan Tasarımcısı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otomatik ve tam geri alma desteği olan ise, Tasarımcı:  
  
-   Kullanır bir <xref:System.Windows.Forms.Control> sınıfı için kendi kullanıcı arabirimi tabanlı.  
  
-   Standart CodeDOM tabanlı kod oluşturma ve ayrıştırma sistem kod oluşturma ve kalıcılığı için kullanır.  
  
     Visual Studio CodeDOM desteği ile çalışma hakkında daha fazla bilgi için bkz: [dinamik kaynak kodu oluşturma ve derleme](/dotnet/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation)  
  
## <a name="when-to-use-explicit-designer-undo-support"></a>Açık Tasarımcı geri alma desteği kullanma zamanı  
 Biri tarafından sağlanan dışında bir görünüm bağdaştırıcısı olarak adlandırılan bir grafik kullanıcı arabirimi kullanıyorsanız, tasarımcıları kendi geri alma yönetim sağlamanız gerekir <xref:System.Windows.Forms.Control>.  
  
 Bir grafik tasarımı web tabanlı arabirimi ürün bunun bir örneğini oluşturma yerine bir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] grafik arabirim tabanlı.  
  
 Böyle durumlarda, bu görünüm bağdaştırıcısı ile kaydetmek ihtiyacım var [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] kullanarak <xref:Microsoft.VisualStudio.Shell.Design.ProvideViewAdapterAttribute>ve açık geri yönetim sağlar.  
  
 CodeDOM ve kalıcılığı desteği olmayan kullanırsanız sağlamanız gereken tasarımcıları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sağlanan kod oluşturma modeli <xref:System.CodeDom> ad alanı.  
  
## <a name="undo-support-features-of-the-designer"></a>Tasarımcı desteği özelliklerini geri al  
 Varsayılan uygulamaları sağlamak için gereken arabirimlerin geri kullanmıyorsa tasarımcıların kullanılabilir Destek ortamı SDK'sı sağlar <xref:System.Windows.Forms.Control> kullanıcı arabirimlerini veya standart CodeDOM ve kalıcılığı modeli için sınıflar temel.  
  
 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> Sınıfı türer [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] <xref:System.ComponentModel.Design.UndoEngine> uygulaması kullanarak sınıfı <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager> yönetmek için sınıf işlemleri geri al.  
  
 Visual Studio Tasarımcı geri alma için aşağıdaki özellik sağlar:  
  
-   Birden çok tasarımcıları arasında bağlantılı geri alma işlevselliği.  
  
-   Bir tasarımcı içinde alt birimler etkileşim kurabilir ile üst uygulayarak <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit> üzerinde <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>.  
  
 Ortamı SDK'sı sağlayarak CodeDOM ve kalıcılığı desteği sağlar:  
  
-   <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> bir uygulamaları olarak <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>  
  
 A <xref:System.ComponentModel.Design.IComponentChangeService> tarafından sağlanan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]'' tasarım ana bilgisayar.  
  
## <a name="using-the-environment-sdk-features-to-supply-undo-support"></a>Geri alma desteği sağlamak için ortamı SDK özellikleri kullanma  
 Geri alma destek almak için bir tasarımcı uygulayan bir nesne gerekir:  
  
-   Örneği ve örneği başlatılamıyor <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> geçerli bir sınıfla <xref:System.IServiceProvider> uygulaması.  
  
-   Bu <xref:System.IServiceProvider> sınıfı aşağıdaki hizmetleri sağlar:  
  
    -   <xref:System.ComponentModel.Design.IDesignerHost>.  
  
    -   <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>  
  
         Kullanarak tasarımcıları [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] CodeDOM serileştirme kullanmayı seçebilir <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> ile sağlanan [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] kendi uygulaması olarak <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>.  
  
         Bu durumda, <xref:System.IServiceProvider> sınıfı için sağlanan <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> Oluşturucusu uygulaması bu nesneyi döndürmelidir <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService> sınıfı.  
  
    -   <xref:System.ComponentModel.Design.IComponentChangeService>  
  
         Varsayılan kullanılarak tasarımcıları <xref:System.ComponentModel.Design.DesignSurface> tarafından sağlanan [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] tasarım konak bir varsayılan uygulaması olması garanti edilir <xref:System.ComponentModel.Design.IComponentChangeService> sınıfı.  
  
 Uygulama tasarımcıları bir <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> tabanlı geri alma mekanizması, değişiklikleri otomatik olarak izler:  
  
-   Özellik değişiklikleri aracılığıyla yapılır <xref:System.ComponentModel.TypeDescriptor> nesnesi.  
  
-   <xref:System.ComponentModel.Design.IComponentChangeService> geri alınamaz bir değişiklik işlendiğinde olayları el ile oluşturulur.  
  
-   Tasarımcı değişikliği bağlamı içinde oluşturulduğu bir <xref:System.ComponentModel.Design.DesignerTransaction>.  
  
-   Açıkça kullanarak geri alma birimleri bir uygulama tarafından sağlanan standart geri birim oluşturmak Tasarımcı seçer <xref:System.ComponentModel.Design.UndoEngine.UndoUnit> veya Visual Studio özgü uygulama <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>, den türetilen <xref:System.ComponentModel.Design.UndoEngine.UndoUnit> ve ayrıca sağlar bir her ikisi de uyarlamasını <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit> ve <xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ComponentModel.Design.UndoEngine>   
 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>   
 [Tasarım zamanı desteği genişletme](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)