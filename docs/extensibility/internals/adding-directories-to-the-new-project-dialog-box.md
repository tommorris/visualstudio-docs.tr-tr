---
title: "Yeni Proje iletişim kutusu için dizinler ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 881979b54fb8f8f07a7ffeb2f3648b690fe2bf78
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="adding-directories-to-the-new-project-dialog-box"></a>Yeni Proje iletişim kutusu için dizinler ekleme
Yeni proje türleri oluşturduğunuzda, yeni bir dizinde da kaydedebilirsiniz **yeni proje** bunları şablon olarak kullanmak için görüntülenecek iletişim kutusu. Aşağıdaki kod örneği, yeni bir dizin olarak da bilinen bir düğüm kaydetmek açıklanmaktadır. Örnekte, VSPackage CLSID_Package tarafından kullanıma sunulan şablonları kaydedilir. Sonuç olarak, sol tarafındaki **yeni proje** iletişim kutusu Folder_Label_ResID kaynak tarafından belirlenen bir adla eklenen düğümle sunar. Bu kaynak VSPackage uydu DLL yüklenir.  
  
 **Klasörü** değeri bir GUID Folder_Label_ResID düğümü altında görüntülendiği bir klasörün temsil eder. Örnekte, GUID temsil eden **diğer projeleri** klasöründe **proje türleri** bölmesinde **yeni proje** iletişim kutusu. Varsa **diğer projeleri** değeri etmeksizin, etiket en üst düzeyinde konumlandırıldı.  
  
 TemplatesDir değeri proje şablonlarını içeren dizinin tam yolunu belirtir. Bu dosyalar .vsz dosyaları veya kopyalanma tipik şablon dosyalarını olabilir.  
  
 TemplatesLocalizedSubDir belirtirseniz, bu kaynak kimliği yerelleştirilmiş şablonları tutan TemplatesDir alt adları bir dize olmalıdır. Çünkü [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dize kaynağını yükler, yoksa bir uydu DLL farklı alt ad her uydu DLL içerebilir. SortPriority değeri sıralama önceliği belirtir.  
  
```  
NoRemove NewProjectTemplates  
{  
    NoRemove TemplateDirs  
  {  
    ForceRemove %CLSID_Package%  
    {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
      {  
        val Folder = s '{DCF2A94A-45B0-11D1-ADBF-00C04FB6BE4C}'  
        val TemplatesDir = s '%Template_Path%'  
        val TemplatesLocalizedSubDir = s '#100'  
        val SortPriority = d 1000  
      }  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonları kaydediliyor](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Öğeler ekleme yeni öğe Ekle iletişim kutuları](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Yeni Öğe Ekleme İletişim Kutusuna Dizin Ekleme](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)