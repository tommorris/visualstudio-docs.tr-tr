---
title: "Dizinleri ekleme yeni öğe Ekle iletişim kutusu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Add New Item dialog box, extending
ms.assetid: 67ae8af6-3752-49e8-8ce3-007aca5f7982
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 591cc9ef1693f2a910eb42a2be3ff5db02ed5c8d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-directories-to-the-add-new-item-dialog-box"></a>Dizinleri ekleme yeni öğe Ekle iletişim kutusu
Aşağıdaki kod örneğinde nasıl dizinler için yeni bir dizi kaydedileceği gösterilmektedir **Yeni Öğe Ekle** iletişim kutusu. Dizinler için **Yeni Öğe Ekle** iletişim kutusunda her proje için farklıdır. Bu nedenle, bulunan projeleri alt anahtarının altındaki dizinleri kayıtlı \<HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp\Projects >:  
  
## <a name="the-registry-script"></a>Kayıt defteri komut dosyası  
  
```  
NoRemove Projects  
{  
  NoRemove %GUID_Project%  
  {  
    NoRemove AddItemTemplates  
    {  
      NoRemove TemplateDirs  
      {  
        ForceRemove %CLSID_Package%  
        {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
          {  
            val TemplatesDir = s '%Template_Path%'     
            val SortPriority = d 2000  
          }  
        }  
      }  
    }  
  }  
}  
```  
  
 Template_Path değeri proje şablonlarını içeren dizinin tam yolunu belirtir. Bu şablonlar .vsz dosyaları veya kopyalanma Prototipik şablon dosyalarını olabilir.  
  
 SortPriority değeri sıralama önceliği belirtir.  
  
## <a name="adding-items-to-an-existing-project"></a>Varolan bir projesine öğeler ekleme  
 Varolan bir projeye öğeleri de ekleyebilirsiniz. Örneğin, bir [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] proje öğeleri ekleyebilirsiniz \<kök > \Program Visual Studio \VC#\CSharpProjectItems\LocalProjectItems klasör. Bu durumda `%GUID_Project%` bir C# projesi ({FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}) GUID değeridir.  
  
 Varolan projeyi proje alt programlama tarafından da genişletebilirsiniz. Proje alt türe yeni bir proje türü yazmak zorunda kalmadan bir proje genişletebilirsiniz. Proje alt türleri hakkında daha fazla bilgi için bkz: [proje Subtypes](../../extensibility/internals/project-subtypes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları kaydediliyor](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Öğeler ekleme yeni öğe Ekle iletişim kutuları](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Yeni Proje iletişim kutusu için dizinler ekleme](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)