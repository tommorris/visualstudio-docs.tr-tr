---
title: Katkıda bulunan yeni öğe Ekle iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6d8b35537828f99fe3683e03feac3960d6ca4adc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="contributing-to-the-add-new-item-dialog-box"></a>Katkıda bulunan yeni öğe Ekle iletişim kutusu
Proje alt öğeleri için tam yeni bir dizin sağlayabilir **Yeni Öğe Ekle** kaydetme iletişim kutusunda **Öğe Ekle** şablonlar altında `Projects` kayıt defteri alt anahtarı.  
  
## <a name="registering-add-new-item-templates"></a>Kaydetme Yeni Öğe Ekle şablonları  
 Bu bölümde altında bulunan **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** kayıt defterinde. Kayıt defteri girdilerini varsayın bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje kuramsal proje alt tarafından toplanır. Girişleri [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] proje aşağıda listelenmiştir.  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}]  
@="#2143"  
"DefaultProjectExtension"="vbproj"  
"PossibleProjectExtensions"="vbproj;vbp"  
"ProjectTemplatesDir"="visualStudioInstallPath\\Vb\\.\\VBProjects"  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}\AddItemTemplates\TemplateDirs\{12345678-1234-1234-1122334455667788}\/1]  
@="#100"  
"TemplatesDir"="projectSubTypeTemplatesDir\\VBProjectItems"  
```  
  
 `AddItemTemplates\TemplateDirs` Alt anahtarını içeren kayıt defteri girdileri burada öğeler kullanılabilir hale içinde dizin yolu ile **Yeni Öğe Ekle** iletişim kutusu yerleştirilir.  
  
 Ortam otomatik olarak tüm yükler `AddItemTemplates` verileri altında `Projects` kayıt defteri alt anahtarı. Bu temel proje uygulamaları için veri ve aynı zamanda belirli proje alt türleri için verileri içerebilir. Her proje alt proje türüne göre tanımlanır `GUID`. Proje alt alternatif kümesi olduğunu belirtebilirsiniz `Add Item` şablonları kullanılmalıdır belirli desteğimize projeye örneği için destekleyerek `VSHPROPID_ AddItemTemplatesGuid` numaralandırma içinden <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> içinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> GUID döndürmek için uygulama Proje alt değeri. Varsa `VSHPROPID_AddItemTemplatesGuid` özelliği belirtilmedi, temel projeyi GUID kullanılır.  
  
 Öğeleri filtrelemek **Yeni Öğe Ekle** uygulayarak iletişim kutusu <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> proje alt Toplayıcı nesnesindeki arabirim. Örneğin, bir veritabanı projesi toplayarak uygulayan bir proje alt bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projesi, filtreleyebilirsiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] özel öğeler **Yeni Öğe Ekle** ve filtreleme uygulayarak iletişim kutusunu açın, ekleyebilirsiniz Veritabanı Proje belirli öğeleri destekleyerek `VSHPROPID_ AddItemTemplatesGuid` içinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>. Öğeler ekleme ve filtreleme hakkında daha fazla bilgi için **Yeni Öğe Ekle** iletişim kutusu, bkz: [ekleme yeni öğe iletişim kutuları için öğe eklemeyi](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Genişletme Projeleri için Genellikle Kullanılan Nesnelerin CATID’leri](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)