---
title: "Tek dosya oluşturucuları kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registration, custom tools
- custom tools, defining registry settings
ms.assetid: db7592c0-1273-4843-9617-6e2ddabb6ca8
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9c75258f24ba86b1ff8d2f3fcd4a16cc4faf5c1
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="registering-single-file-generators"></a>Tek dosya oluşturucuları kaydetme
Özel bir araç olarak kullanılabilir hale getirmek [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], bu nedenle kaydettirmelisiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] örneğini oluşturabilir ve belirli proje türü ile ilişkilendirir.  
  
### <a name="to-register-a-custom-tool"></a>Özel bir aracı kaydetmek için  
  
1.  Özel araç DLL ya da kayıt içinde [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] yerel kayıt defteri veya sistem defterinde HKEY_CLASSES_ROOT altında.  
  
     Örneğin, kayıt bilgileri ile birlikte gelen yönetilen MSDataSetGenerator özel aracı, işte [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\CLSID\{E76D53CC-3D4F-40A2-BD4D-4F3419755476}]  
    @="COM+ class: Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"  
    "InprocServer32"="C:\\WINDOWS\\system32\\mscoree.dll"  
    "ThreadingModel"="Both"  
    "Class"="Microsoft.VSDesigner.CodeGenerator.TypedDataSourceGenerator.DataSourceGeneratorWrapper"  
    "Assembly"="Microsoft.VSDesigner, Version=14.0.0.0, Culture=Neutral, PublicKeyToken=b03f5f7f11d50a3a"  
    ```  
  
2.  Bir kayıt defteri anahtarı oluşturmak istediğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] hive oluşturucuları altında\\*GUID* nerede *GUID* GUID belirli dilin proje sistemi veya hizmet tarafından tanımlanır. Anahtar adı, özel araç programlı adı haline gelir. Özel araç anahtar aşağıdaki değerlere sahiptir:  
  
    -   (Varsayılan)  
  
         İsteğe bağlı. Özel araç kullanıcı dostu bir açıklaması verilmiştir. Bu parametre isteğe bağlıdır ancak önerilir.  
  
    -   CLSID  
  
         Gerekli. Sınıf kitaplığı uygulayan COM bileşeninin tanımlayıcısını belirtir <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>.  
  
    -   GeneratesDesignTimeSource  
  
         Gerekli. Bu özel aracı tarafından üretilen dosyalar türlerinden görsel tasarımcılar kullanılabilir olup olmadığını gösterir. Bu parametrenin değeri türleri için görsel tasarımcılar kullanılabilir değil (sıfır) 0 veya (bir) 1 türleri için görsel tasarımcılar kullanılabilir olması gerekir.  
  
    > [!NOTE]
    >  Ayrı olarak özel bir araç kullanılabilir olmasını istediğiniz her dil için özel bir araç kaydetmeniz gerekir.  
  
     Örneğin, MSDataSetGenerator kendisini kez her dil için kaydeder:  
  
    ```  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{164b10b9-b200-11d0-8c61-00a0c91e29d5}\MSDataSetGenerator]  
    @="Microsoft VB Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{fae04ec1-301f-11d3-bf4b-00c04f79efbc}\MSDataSetGenerator]  
    @="Microsoft C# Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
  
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\Generators\{e6fdf8b0-f3d1-11d4-8576-0002a516ece8}\MSDataSetGenerator]  
    @="Microsoft J# Code Generator for XSD"  
    "CLSID"="{E76D53CC-3D4F-40a2-BD4D-4F3419755476}"  
    "GeneratesDesignTimeSource"=dword:00000001  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator>   
 [Tek dosya oluşturucuları uygulama](../../extensibility/internals/implementing-single-file-generators.md)   
 [Görsel tasarımcılar türlerine gösterme](../../extensibility/internals/exposing-types-to-visual-designers.md)   
 [BuildManager nesnesine giriş](http://msdn.microsoft.com/en-us/50080ec2-c1c9-412c-98ef-18d7f895e7fa)