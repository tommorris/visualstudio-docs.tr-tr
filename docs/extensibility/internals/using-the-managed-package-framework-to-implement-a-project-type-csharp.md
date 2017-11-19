---
title: "Yönetilen paket Framework için bir proje türü (C#) kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], creating with MPF
- MPF projects
- managed package framework, creating projects
ms.assetid: 926de536-eead-415b-9451-f1ddc8c44630
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 16e1d301e5a3977f656c52f9c97eb43ee216075f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-the-managed-package-framework-to-implement-a-project-type-c"></a>Proje türü (C#) uygulamak için yönetilen paket çerçevesini kullanarak
Yönetilen paket Framework (MPF) kullanabilir veya kendi proje türleri uygulamak için devralınmalıdır C# sınıflar sağlar. MPF Visual Studio sağlamak için bir proje türü bekliyor arabirimleri birçoğu, proje türü gerçekleştirilebilir uygulanmasına yoğunlaşmak boş bırakarak uygular.  
  
## <a name="using-the-mpf-project-source-code"></a>MPF proje kaynak kodu kullanma  
 Paket çerçevesi ile yönetilen projelerinin (MPFProj) oluşturmak ve yeni proje sistemini yönetmek için yardımcı sınıfları sağlar. MPF diğer sınıfları, proje sınıfları Visual Studio ile birlikte gelen derlemelerde dahil edilmez. Bunun yerine, kaynak kodu olarak proje sınıfları sağlanan [MPF projeleri 2013 için](http://mpfproj12.codeplex.com).  
  
 Bu proje VSPackage çözümünüze eklemek için aşağıdakileri yapın:  
  
1.  MPFProj dosyaları karşıdan *MPFProjectDir*.  
  
2.  İçinde *MPFProjectDir*\Dev10\Src\CSharp\ProjectBase.file, aşağıdaki bloğu değiştirin:  
  
```  
<!-- Provide a default value for $(ProjectBasePath) -->  
  <PropertyGroup>  
    <ProjectBasePath >MPFProjDir\Dev10\Src\CSharp</ProjectBasePath>  
  </PropertyGroup>  
```  
  
1.  VSPackage projesi oluşturun.  
  
2.  VSPackage proje kaldırın.  
  
3.  Diğer önce aşağıdaki blok ekleyerek VSPackage .csproj dosyasını düzenleyin `<Import>` engeller:  
  
```  
<Import Project="MPFProjectDir\Dev10\Src\CSharp\ProjectBase.files" />  
  <PropertyGroup>  
    <!--To specify a different registry root to register your package, uncomment the TargetRegistryRoot tag and specify a registry root in it.  
    <TargetRegistryRoot></TargetRegistryRoot>-->  
    <RegisterOutputPackage>true</RegisterOutputPackage>  
    <RegisterWithCodebase>true</RegisterWithCodebase>  
  </PropertyGroup>  
```  
  
1.  Projeyi kaydedin.  
  
2.  VSPackage çözümü kapatıp yeniden açın.  
  
3.  VSPackage projeyi yeniden açın. ProjectBase adlı yeni bir dizin görmeniz gerekir.  
  
4.  Aşağıdaki başvuru VSPackage projeye ekleyin:  
  
     Microsoft.Build.Tasks.4.0  
  
5.  Projeyi oluşturun.  
  
## <a name="hierarchy-classes"></a>Hiyerarşi sınıfları  
 Aşağıdaki tabloda Proje hiyerarşileri destek MPFProj sınıflarda özetler. Daha fazla bilgi için bkz: [hiyerarşileri ve seçim](../../extensibility/internals/hierarchies-and-selection.md).  
  
|Sınıf adı|  
|----------------|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|  
|`Microsoft.VisualStudio.Package.ProjectNode`|  
|`Microsoft.VisualStudio.Package.ProjectContainerNode`|  
|`Microsoft.VisualStudio.Package.FileNode`|  
|`Microsoft.VisualStudio.Package.FolderNode`|  
|`Microsoft.VisualStudio.Package.ReferenceContainerNode`|  
|`Microsoft.VisualStudio.Package.ReferenceNode`|  
|`Microsoft.VisualStudio.Package.ProjectReferenceNode`|  
|`Microsoft.VisualStudio.Package.ComReferenceNode`|  
|`Microsoft.VisualStudio.Package.AssemblyReferenceNode`|  
|`Microsoft.VisualStudio.Package.BuildDependency`|  
  
## <a name="document-handling-classes"></a>Belge işleme sınıfları  
 Aşağıdaki tabloda belge işleme desteği MPF sınıflarda listeler. Daha fazla bilgi için bkz: [açma ve kaydetme proje öğeleri](../../extensibility/internals/opening-and-saving-project-items.md).  
  
|Sınıf adı|  
|----------------|  
|`Microsoft.VisualStudio.Package.DocumentManager`|  
|`Microsoft.VisualStudio.Package.FileDocumentManager`|  
  
## <a name="configuration-and-output-classes"></a>Yapılandırma ve çıktı sınıfları  
 Aşağıdaki tabloda, hata ayıklama ve yayın ve proje çıktı koleksiyonları gibi birden çok yapılandırmayı destekleyen proje türleri izin MPF sınıflarda listeler. Daha fazla bilgi için bkz: [yönetme yapılandırma seçenekleri](../../extensibility/internals/managing-configuration-options.md).  
  
|Sınıf adı|  
|----------------|  
|`Microsoft.VisualStudio.Package.ConfigProvider`|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|  
|`Microsoft.VisualStudio.Package.BuildableProjectConfig`|  
|`Microsoft.VisualStudio.Package.OutputGroup`|  
|`Microsoft.VisualStudio.Package.ProjectElement`|  
  
## <a name="automation-support-classes"></a>Otomasyon destek sınıfları  
 Aşağıdaki tabloda Otomasyon destekler ve böylece kullanıcılar, proje türü eklentileri yazabilirsiniz MPF sınıflarda listeler.  
  
|Sınıf adı|  
|----------------|  
|`Microsoft.VisualStudio.Package.Automation.OAProject`|  
|`Microsoft.VisualStudio.Package.Automation.OANavigableProjectItems`|  
|`Microsoft.VisualStudio.Package.Automation.OAProjectItems`|  
|`Microsoft.VisualStudio.Package.Automation.OAProjectItem`|  
|`Microsoft.VisualStudio.Package.Automation.OANestedProjectItem`|  
  
## <a name="properties-classes"></a>Özellikler sınıfları  
 Aşağıdaki tabloda Proje türleri izin MPF sınıflarda kullanıcılar göz atın ve bir özellik tarayıcıda değiştirme özellikleri ekleyin.  
  
|Sınıf adı|  
|----------------|  
|`Microsoft.VisualStudio.Package.LocalizableProperties`|  
|`Microsoft.VisualStudio.Package.NodeProperties`|  
|`Microsoft.VisualStudio.Package.FileNodeProperties`|  
|`Microsoft.VisualStudio.Package.ProjectNodeProperties`|  
|`Microsoft.VisualStudio.Package.FolderNodeProperties`|  
|`Microsoft.VisualStudio.Package.ReferenceNodeProperties`|