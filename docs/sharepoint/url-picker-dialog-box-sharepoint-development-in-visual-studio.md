---
title: "URL Seçici iletişim kutusu (Visual Studio'da SharePoint Geliştirme) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.SharePointTools.VWD.URLPicker
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, URL picker
- SharePoint development in Visual Studio, designer
ms.assetid: 33f8f521-e1f8-4242-a580-8a4bd9cb5ddc
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: c475b44b15b206464e2a910cc410964906706bd6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="url-picker-dialog-box-sharepoint-development-in-visual-studio"></a>URL Seçici İletişim Kutusu (Visual Studio'da SharePoint geliştirme)
  URL Seçici iletişim kutusu, SharePoint çalıştıran yerel sunucu ana sayfa dosyası veya projenizdeki veya bulunan görüntü dosyaları gibi dosyalar seçebilirsiniz.  
  
 Bir özelliği ayarlamak için bir dosya seçmek üzere seçeneği varsa, bu iletişim kutusu görüntülenir. Üç nokta düğmesini seçerek bu iletişim kutusunu açabilir (![ASP.NET Mobil Tasarımcı elips](../sharepoint/media/mwellipsis.gif "ASP.NET Mobil Tasarımcı elips")) çeşitli özelliklerinde yanındaki **özellikleri** penceresi. Belirli öznitelikler için değerleri atadığınızda üç nokta düğmesini ayrıca bir IntelliSense komut istemi görünür **kaynak** Designer görünüm.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Proje klasörleri**  
 Projedeki veya SharePoint çalıştıran yerel sunucu üzerinde tanımlanan klasörlerin listesini görüntüler. Alt klasörleri görüntülemek için genişletme düğmesini seçin.  
  
 Genişletme **proje** düğümü projenizde dosyaları seçin. İletişim kutusunda olarak seçilebilir görünmesi için projenizdeki dosyalar aşağıdaki ölçütleri karşılamalıdır:  
  
-   Dosya eşlenmiş bir klasörde bulunmalıdır.  
  
-   Dosya çözüm pakete eklenmesi gerekir.  
  
-   Dosya başka bir projede yer alamaz.  
  
 Bu ölçütleri karşılamayan dosyalar başvurmak istiyorsanız, dosya yolunu el ile girmeniz gerekir.  
  
 Genişletme **Server** düğümü SharePoint çalıştıran yerel sunucu üzerinde bulunan dosyaları seçin. İletişim kutusunda olarak seçilebilir görünmesi için bu dosyalar aşağıdaki ölçütleri karşılamalıdır:  
  
-   Dosya aşağıdaki eşlenen klasörlerden birinde bulunmalıdır: **görüntüleri**, **düzenleri**, veya **ControlTemplates**.  
  
-   Dosya SharePoint içerik veritabanı bulunamıyor.  
  
 Bu ölçütleri karşılamayan dosyalar başvurmak istiyorsanız, dosya yolunu el ile girmeniz gerekir.  
  
 **Klasörün içeriği**  
 Seçilen klasördeki dosyaların bir listesini görüntüler. Bir dosya seçin ve ardından **Tamam** iletişim kutusunu kapatmak ve seçiminizi adlı işleme göndermek için düğmesi.  
  
 **Dosya türü**  
 Gerçekleştirmekte olduğunuz görev için uygun olan dosyalar listesinden seçmenize olanak sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SharePoint için uygulama sayfaları oluşturma](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint için Web bölümleri oluşturma](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Web Bölümleri veya Uygulama Sayfaları için Yeniden Kullanılabilir Denetimler Oluşturma](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)   
  
  