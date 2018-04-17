---
title: Proje ekleme ve proje öğesi şablonları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], adding
- project items [Visual Studio], adding
ms.assetid: 8c59217f-56e5-4540-a73b-cd10de189373
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 94d521d288b470db56736668f11d47dab71d2533
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-project-and-project-item-templates"></a>Proje ve proje öğesi şablonları ekleme
Kendi proje türleri oluşturduğunuzda, yeni proje ve proje öğeleri standart kullanarak eklemek için destek sağlamalısınız [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) iletişim kutuları. Aşağıdaki konular, projeler ve proje öğelerini eklemek için farklı teknikleri tartışın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Proje Bağlamı](../../extensibility/internals/project-context.md)  
 Proje ne ortamda transpires için bağlam bilgisi çoğunu sağladığı açıklanmıştır.  
  
 [Proje Önceliği](../../extensibility/internals/project-priority.md)  
 Bir proje öğesi genellikle hakkında proje öğesini açmak için kullanılan Karışıklığı önlemek için bir proje bir üyesi olduğunu açıklar.  
  
 [Çeşitli Dosyalar Projesi](../../extensibility/internals/miscellaneous-files-project.md)  
 Bir proje öğesi açıldığında kullanılacak düzenleyicileri belirlerken proje oynadığı bir proje ve rol dosyalarını açmak için kullanılan düzenleyicileri iki tür hakkında bilgi sağlar.  
  
 [Proje ve Öğe Şablonlarını Kaydetme](../../extensibility/internals/registering-project-and-item-templates.md)  
 Neler olduğunu açıklar olduğunda bir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projesi oluşturulur.  
  
 [Yeni Öğe Ekleme İletişim Kutularına Öğe Ekleme](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)  
 Öğeler ekleme işlemi açıklanmaktadır **Yeni Öğe Ekle** iletişim kutusu.  
  
 [Yeni Proje İletişim Kutusuna Dizin Ekleme](../../extensibility/internals/adding-directories-to-the-new-project-dialog-box.md)  
 Özel şablonlar VSPackage tarafından kullanılabilir hale içeren yeni bir dizin kaydı bir örnek sağlar.  
  
 [Yeni Öğe Ekleme İletişim Kutusuna Dizin Ekleme](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)  
 Dizinler için yeni bir dizi kaydetme örneğidir **Yeni Öğe Ekle** iletişim kutusu.  
  
 [Proje Sistemlerini Genişletmeye Yönelik IDE Tanımlı Komutlar](../../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)  
 Farklı türlerde proje sistemleri genişletmek için kullanılan komut öğeleri listeler.  
  
 [Genişletme Projeleri için Genellikle Kullanılan Nesnelerin CATID’leri](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)  
 Genişletmek için kullanılan nesneler için CATIDs listeler [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] proje sistemleri.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Nasıl Yapılır: Projeye Özgü Düzenleyicileri Açma](../../extensibility/how-to-open-project-specific-editors.md)  
 Bir proje için belirli bir düzenleyici doğası gereği bağlı bir öğeyi açmak için adım adım yönergeler sağlar.  
  
 [Nasıl Yapılır: Standart Düzenleyicileri Açma](../../extensibility/how-to-open-standard-editors.md)  
 Bir standart Düzenleyicisi'ni açmak için adım adım yönergeler sağlar.  
  
 [Proje Alt Türleri](../../extensibility/internals/project-subtypes.md)  
 Alt kavramsal konuları proje için bağlantılar sağlar. Proje subtypes genişletmek varolan [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] ve [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] projeleri.  
  
 [Proje Türleri](../../extensibility/internals/project-types.md)  
 Yeni proje türleri tasarlama hakkında bilgi sağlayan ek konulara bağlantılar sağlar.