---
title: MSBuild kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, compiling with MSBuild
- MSBuild, extensibility
- packages, compiling with MSBuild
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4115d6f1b368734631acf3ee4395d71dbe418c07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-msbuild"></a>MSBuild kullanma
MSBuild proje öğeleri oluşturulması, derleme görevleri ve yapılandırmaları oluşturmak için tam olarak tanımlayan proje dosyalarını oluşturmak için bir iyi tanımlanmış, Genişletilebilir XML biçiminde sağlar.  
  
## <a name="general-msbuild-considerations"></a>Genel MSBuild konuları  
 MSBuild proje dosyalarını, örneğin, [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] .csproj ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] .vbproj dosyaları, derleme zamanında kullanılır, ancak tasarım zamanında kullanılan verileri de içerebilir verileri içerir. Derleme zamanı verileri dahil olmak üzere MSBuild temelleri kullanarak depolanan [öğe unsuru (MSBuild)](../../msbuild/item-element-msbuild.md) ve [özellik öğesi (MSBuild)](../../msbuild/property-element-msbuild.md). Proje türü ve tüm ilgili proje alt türleri için belirli veri olan tasarım zamanı verileri için ayrılmış serbest biçimli XML depolanır.  
  
 MSBuild yapılandırma nesneleri için yerel destek yok ancak özel yapılandırma verileri belirtmek için koşullu öznitelikler sağlar. Örneğin:  
  
```xml  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 Koşullu öznitelikler hakkında daha fazla bilgi için bkz: [koşullu yapıları](../../msbuild/msbuild-conditional-constructs.md).  
  
### <a name="extending-msbuild-for-your-project-type"></a>MSBuild proje türünüz için genişletme  
 MSBuild arabirimleri ve API tabidir değişiklik gelecekteki sürümlerinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Bu nedenle, yönetilen paket framework (MPF) sınıfları değişikliklere karşı koruma sağlamak için kullanılacak akıllıca olur.  
  
 Paket çerçevesi ile yönetilen projelerinin (MPFProj) oluşturmak ve yeni proje sistemini yönetmek için yardımcı sınıfları sağlar. Kaynak kodu ve derleme yönergeleri bulabilirsiniz [MPF projeleri - Visual Studio 2013 için](http://mpfproj12.codeplex.com/).  
  
 Proje özgü MPF sınıflar aşağıdaki gibidir:  
  
|örneği|Uygulama|  
|-----------|--------------------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement` MSBuild öğeleri için sarmalayıcı sınıftır.  
  
#### <a name="single-file-generators-vs-msbuild-tasks"></a>Tek dosya oluşturucuları vs. MSBuild Görevleri  
 Tek dosya oluşturucuları tasarım zamanında yalnızca erişilebilir, ancak Tasarım zamanı ve yapı saatte MSBuild görevleri kullanılabilir. Maksimum esneklik için bu nedenle, dönüştürme ve kodu oluşturmak için MSBuild görevleri kullanın. Daha fazla bilgi için bkz: [özel Araçlar](../../extensibility/internals/custom-tools.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../../msbuild/msbuild-reference.md)   
 [MSBuild](../../msbuild/msbuild.md)   
 [Özel Araçlar](../../extensibility/internals/custom-tools.md)