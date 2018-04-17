---
title: İç içe geçmiş projeleri için filtreleme addItem iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- filtering, nested projects
- nested projects, AddItem dialog box filtering
ms.assetid: 5b3e352e-7f18-4f66-be16-b0ad55637ce5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 50a9491dad92e4f1dd090a6de1ebf48ef1b88085
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="filtering-the-additem-dialog-box-for-nested-projects"></a>İç içe geçmiş projeleri için filtreleme addItem iletişim kutusu
Görüntülediğinizde bir **addItem** ana proje iç içe geçmiş bir proje için iletişim kutusu, hangi öğeler iletişim kutusunda görüntülenen denetleyebilirsiniz.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2> Arabirimi olacak düğümleri filtreleme olanak tanır bir **addItem** iletişim kutusu. Alt proje görüntülendiğinde **addItem** iletişim kutusu, üst uygulayabilirsiniz `IVsFilterAddProjectItemDlg` çocuğun projesinde görüntülenmesi arabirimi ve filtre öğeleri.  
  
 Projeleri belirli üst projeleri altında işleve göre gruplandırılır olduğunda uygulayabileceğiniz `IVsFilterAddProjectItemDlg` kullanıcı seçtiğinde **proje öğesi Ekle** iç içe proje kısayol menüsünde. Uygulama `IvsFilterAddProjectItemDlg displays` yalnızca proje öğelerini ya da bu gruba belirli dosyaları. Aynı dizinde depolanır olsa bile diğer grupları için proje öğeleri iletişim kutusu dışında filtrelenir.  
  
 Kullanıcı açtığında **addItem** alt, üst projenin uygulaması için iletişim kutusu `IVsFilterAddProjectItemDlg` arabirimi çağrılır.  
  
 `IVsFilterAddProjectItemDlg` Arabirimi, kategoriye göre filtreleme de uygulayabilirsiniz. Daha fazla bilgi için bkz: [ekleme yeni öğe iletişim kutuları için öğe eklemeyi](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md) ve [kaydetme proje ve öğe şablonlarını](../../extensibility/internals/registering-project-and-item-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Öğeler ekleme yeni öğe Ekle iletişim kutuları](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Proje ve öğe şablonları kaydediliyor](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Projeleri İç İçe Geçirme](../../extensibility/internals/nesting-projects.md)