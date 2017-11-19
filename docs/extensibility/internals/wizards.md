---
title: Sihirbazlar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: projects [Visual Studio SDK], providing wizard support
ms.assetid: 59d9a77f-ee80-474b-a14f-90f477ab717b
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 838b7cac850b8e7eb3401065cf13202d3a3a40ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="wizards"></a>Sihirbazlar
Sihirbaz oluşturduktan sonra genellikle eklemek istediğiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE) böylece diğerleri kullanabilirsiniz. Eklenen sihirbazını sonra görünür **Yeni Proje Ekle** veya **Yeni Öğe Ekle** iletişim kutuları. Görmek için **Yeni Proje Ekle** veya **Yeni Öğe Ekle** iletişim kutuları, sağ tıklatın, açık bir çözümde **Çözüm Gezgini**, işaret **Ekle**, ve ardından **yeni proje** veya **yeni öğe**.  
  
 Sihirbazlar uygulanabilir [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] kullanıcıların izin verecek şekilde açtıklarında kullanılabilir değerler ağaç görünümünü seçim **Yeni Proje Ekle** iletişim kutusu veya **Yeni Öğe Ekle** iletişim kutusu, veya ne zaman sağ bir öğeyi **Çözüm Gezgini**.  
  
 Sihirbazı, yeni bir proje veya ites adını yerelleştirme seçeneği sağlayabilir ve Sihirbazı'nı seçtiğinizde, kullanıcıların göreceği simgesi belirleyebilirsiniz. Ayrıca yeni öğeler kullanılabilir diğer öğeler göre görünme sırasını kontrol edebilirsiniz; Öğeleri alfabetik olarak düzenlenmesine gerek yoktur.  
  
 Farklı şekilde, açıldığında, sihirbaz geçirilen özel parametrelerine göre başlayan Sihirbazı'nı da sağlayabilir.  
  
 Bu bölümdeki konular, neden üzerek dosyaları ele [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **Yeni Proje Ekle** ve **Yeni Öğe Ekle** kullanılabilir sihirbazlar ve şablonlar, arasında Sihirbazı'nı listelemek için iletişim kutuları ve Sihirbazı'nı IDE içinde düzgün çalışması için karşılaması gereken gereksinimleri.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Şablon dizin açıklaması (. Vsdir) dosyaları](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)  
 Dizin açıklama dosyaları şablonu genel bir bakış sağlar ve bunların klasörler, sihirbaz .vsz dosyaları ve iletişim kutularında bir proje ile ilişkili şablon dosyalarını görüntülemek için IDE'de işlevleri açıklanmaktadır.  
  
 [Sihirbazı'nı (. Vsz) dosyası](../../extensibility/internals/wizard-dot-vsz-file.md)  
 .Vsz dosyası üç bölümden listeler ve IDE sihirbazları nasıl başlatır açıklanmaktadır.  
  
 [Sihirbaz arabirimi (IDTWizard)](../../extensibility/internals/wizard-interface-idtwizard.md)  
 Açıklar `IDTWizard` sihirbazları IDE içinde çalışmak için uygulamalıdır arabirimi.  
  
 [Bağlam parametreleri](../../extensibility/internals/context-parameters.md)  
 Sihirbazlar nasıl uygulandığını ve IDE bağlam parametreleri kullanımla başarılı olduğunda ne olacağını açıklar.  
  
 [Özel Parametreler](../../extensibility/internals/custom-parameters.md)  
 Özel Parametreler sihirbaz başlatıldıktan sonra Sihirbazı'nın çalışmasını denetlemek için nasıl kullanılacağını açıklar.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Proje türleri](../../extensibility/internals/project-types.md)  
 Yeni proje türleri tasarlama hakkında bilgi sağlayan ek konulara bağlantılar sağlar.  
  
 [İzlenecek yol: bir sihirbaz oluşturma](http://msdn.microsoft.com/Library/adb41fe9-fcca-4e87-bf4f-bf2fa68e8b06)  
 Sihirbaz oluşturulacağını gösterir.  
  
 [Projeleri genişletme](../../extensibility/extending-projects.md)  
 Nasıl kullanılacağını açıklar [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] projeler ve çözümler kod dosyaları ve kaynak dosyaları ve kaynak denetimi nasıl düzenlemek için.