---
title: "Proje ve yapılandırma özellikleri için destek | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project properties, supporting with Visual Studio SDK
- configuration properties, suppporting with Visual Studio SDK
ms.assetid: 9fcfaa0f-7b41-4b68-82ec-7a151dca5d7e
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e31f4feda55469d2740b32b0eac5d9cfba286d0c
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="support-for-project-and-configuration-properties"></a>Proje ve yapılandırma özellikleri için destek
**Özellikleri** penceresinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE), proje ve yapılandırma özelliklerini görüntüleyebilirsiniz. Kullanıcının, uygulamanın özelliklerini ayarlayıp böylece kendi proje türü için özellik sayfası sağlayabilir.  
  
 Proje düğümünde seçerek **Çözüm Gezgini** ve ardından **özellikleri** üzerinde **proje** menüsünde Proje ve yapılandırmasını içeren bir iletişim kutusunu açabilirsiniz Özellikler. İçinde [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]ve proje sekmeli sayfası olarak bu iletişim kutusu görünür bu dillerden türetilmiş türler [genel, ortam, Seçenekler iletişim kutusu](../../ide/reference/general-environment-options-dialog-box.md). Daha fazla bilgi için bkz: [yapı içinde değil: izlenecek yol: Proje gösterme ve yapılandırma özellikleri (C#)](http://msdn.microsoft.com/en-us/d850d63b-25e2-4505-9f3d-eb038d7c1d0e).  
  
 Paket çerçevesi ile yönetilen projelerinin (MPFProj) oluşturmak ve yeni proje sistemini yönetmek için yardımcı sınıfları sağlar. Kaynak kodu ve derleme yönergeleri bulabilirsiniz [MPF projeleri - Visual Studio 2013 için](http://mpfproj12.codeplex.com/).  
  
## <a name="persistence-of-project-and-configuration-properties"></a>Proje ve yapılandırma özelliklerini kalıcılığı  
 Örneğin proje türüyle ilişkili dosya adı uzantısı, .csproj, .vbproj ve .myproj sahip bir proje dosyasında proje ve yapılandırma özelliklerini kalıcıdır. Dil projeleri, bir şablon dosyası genellikle proje dosyası oluşturmak için kullanın. Ancak, proje türleri ve şablonları ilişkilendirmek için gerçekten birkaç yolu vardır. Daha fazla bilgi için bkz: [şablon dizin açıklaması (. Vsdir) dosyaları](../../extensibility/internals/template-directory-description-dot-vsdir-files.md).  
  
 Proje ve yapılandırma özelliklerini şablon dosyasına öğeleri ekleyerek oluşturulur. Bu özellikleri daha sonra bu şablonu kullanan proje türü kullanılarak oluşturulan herhangi bir projesi için kullanılabilir. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]Projeler ve her ikisini de kullanmanız MPFProj [yapı içinde değil: MSBuild genel bakış](http://msdn.microsoft.com/en-us/b588fd73-a45b-4706-908f-cc131bccfbde) şablon dosyalarını için şema. Bu dosyaları her yapılandırma için bir PropertyGroup bölümü vardır. Proje özellikleri genellikle bir yapılandırma bağımsız değişkeni boş bir dize belirlenmiş olan ilk PropertyGroup bölümünde, kalıcıdır.  
  
 Aşağıdaki kod bir temel MSBuild proje dosyası başlangıcını gösterir.  
  
```  
<Project MSBuildVersion="2.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
    <Name>SomeProjectSix</Name>  
    <SchemaVersion>2.0</SchemaVersion>  
  </PropertyGroup>  
  <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
    <Optimize>false</Optimize>  
  </PropertyGroup>  
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
    <Optimize>true</Optimize>  
```  
  
 Bu proje dosyasındaki `<Name>` ve `<SchemaVersion>` proje özellikleri ve `<Optimize>` yapılandırma özelliğidir.  
  
 Proje dosyası proje ve yapılandırma özelliklerini kalıcı hale getirmek için proje sorumluluğundadır.  
  
> [!NOTE]
>  Bir proje Kalıcılık varsayılan değerlerine farklı kalıcı yalnızca özelliği değerlere göre en iyi duruma getirebilirsiniz.  
  
## <a name="support-for-project-and-configuration-properties"></a>Proje ve yapılandırma özellikleri için destek  
 `Microsoft.VisualStudio.Package.SettingsPage` Sınıfı proje ve yapılandırması özellik sayfaları uygular. Varsayılan uygulaması `SettingsPage` bir kullanıcıya bir genel özellik kılavuzunda ortak özellikler sunar. `Microsoft.VisualStudio.Package.HierarchyNode.GetPropertyPageGuids` Yöntemini seçerse türetilmiş sınıfları `SettingsPage` proje özellik kılavuzları için. `Microsoft.VisualStudio.Package.ProjectNode.GetConfigPropertyPageGuids` Yöntemini seçerse türetilmiş sınıfları `SettingsPage` yapılandırması özellik kılavuzları için. Proje türüne uygun özellik sayfaları seçmek için bu yöntemleri geçersiz kılmalısınız.  
  
 `SettingsPage` Sınıfı ve `Microsoft.VisualStudio.Package.ProjectNode` sınıfı proje ve yapılandırma özelliklerini kalıcı hale getirmek için bu yöntemleri sunar:  
  
-   `Microsoft.VisualStudio.Package.ProjectNode.GetProjectProperty`ve `Microsoft.VisualStudio.Package.ProjectNode.SetProjectProperty` proje özellikleri kalır.  
  
-   `Microsoft.VisualStudio.Package.SettingsPage.GetConfigProperty`ve `Microsoft.VisualStudio.Package.SettingsPage.SetConfigProperty` yapılandırma özellikleri kalır.  
  
    > [!NOTE]
    >  Uygulamaları `Microsoft.VisualStudio.Package.SettingsPage` ve `Microsoft.VisualStudio.Package.ProjectNode` sınıfları kullanım `Microsoft.Build.BuildEngine` almak ve proje dosyasından proje ve yapılandırma özelliklerini ayarlamak için (MSBuild) yöntemleri.  
  
 Öğesinden türetilen sınıf `SettingsPage` uygulamalıdır `Microsoft.VisualStudio.Package.SettingsPage.ApplyChanges` ve `Microsoft.VisualStudio.Package.SettingsPage.BindProperties` proje dosyası proje veya yapılandırma özelliklerini kalıcı hale getirmek için.  
  
## <a name="provideobjectattribute-and-registry-path"></a>ProvideObjectAttribute ve kayıt defteri yolu  
 Türetilmiş sınıflar `SettingsPage` VSPackages paylaşılmak üzere tasarlanmıştır. Türetilmiş bir sınıf oluşturmak bir VSPackage için mümkün kılmak için `SettingsPage`, ekleme bir `Microsoft.VisualStudio.Shell.ProvideObjectAttribute` türetilmiş bir sınıf için `Microsoft.VisualStudio.Shell.Package`.  
  
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_1.cs)]
 [!code-vb[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_1.vb)]  
  
 Öznitelik iliştirildiği VSPackage önemli değildir. Ne zaman bir VSPackage kayıtlı ile [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], oluşturulabilmesi için herhangi bir nesnenin sınıf kimliği (CLSID) kayıtlı böylece yapılan bir çağrı <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry.CreateInstance%2A> oluşturabilirsiniz.  
  
 Kayıt defteri yolunu oluşturulabilmesi için bir nesnenin birleştirerek belirlenir <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, word, CLSID ve nesne türü GUID. Varsa `MyProjectPropertyPage` sınıfı bir GUID {3c693da2-5bca-49b3-bd95-ffe0a39dd723} sahiptir ve UserRegistryRoot HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp olan ve ardından kayıt defteri yolunu HKEY_CURRENT_USER\Software\Microsoft\VisualStudio olacaktır \8.0Exp\CLSID\\{3c693da2-5bca-49b3-bd95-ffe0a39dd723}.  
  
## <a name="project-and-configuration-property-attributes-and-layout"></a>Proje ve yapılandırma özelliği özniteliklerini ve düzeni  
 <xref:System.ComponentModel.CategoryAttribute>, <xref:System.ComponentModel.DisplayNameAttribute>, Ve <xref:System.ComponentModel.DescriptionAttribute> öznitelikleri belirlemek düzeni, etiketleme ve genel özellik sayfası, proje ve yapılandırma özelliklerini açıklaması. Bu öznitelikler kategori belirlemek için ad ve açıklama seçeneğinin sırasıyla görüntüler.  
  
> [!NOTE]
>  Eşdeğer öznitelikleri, SRCategory, LocDisplayName ve SRDescription, yerelleştirme için dize kaynaklarını kullanın ve içinde tanımlanan [MPF projeleri - Visual Studio 2013 için](http://mpfproj12.codeplex.com/).  
  
 Aşağıdaki kod parçası göz önünde bulundurun:  
  
 [!code-vb[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_2.vb)]
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_2.cs)]  
  
 `MyConfigProp` Yapılandırma özelliği görünür Yapılandırma özelliği sayfasında **My Yapılandırma özelliği** kategorisinde **My kategori**. Seçeneğini belirlediyseniz, açıklama **My açıklama**, açıklama panelinde görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ekleme ve kaldırma özellik sayfaları](../../extensibility/adding-and-removing-property-pages.md)   
 [Projeleri](../../extensibility/internals/projects.md)   
 [Şablon Dizin Açıklaması (.Vsdir) Dosyaları](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)
