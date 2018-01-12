---
title: "Office programlarındaki ortak görevler | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, getting started
- FAQs (frequently asked questions) [Office development in Visual Studio]
- Office development in Visual Studio, frequently asked questions
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 65a20b5d65ba49789aea857459bd6a4d316195eb
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="common-tasks-in-office-programming"></a>Office Programlarındaki Ortak Görevler
  Bu konu, aşağıdaki kategorisinden Visual Studio kullanarak Office çözümleri programlama hakkında genel soruların yanıtları bulmanıza yardımcı olmak için tasarlanmıştır.  
  
-   [Kurulum ve genel görevler](#projects).  
  
-   [Kullanıcı arabirimi özelleştirme görevleri](#ui).  
  
-   [Excel otomasyon görevleri](#excel).  
  
-   [Word otomasyon görevleri](#word).  
  
-   [Veri görevleri](#data).  
  
-   [Sunucu tarafı belge yönetim görevleri](#server).  
  
-   [Güvenlik görevlerini](#security).  
  
-   [Dağıtım görevleri](#deployment).  
  
##  <a name="projects"></a>Kurulum ve genel görevler  
  
-   [Nasıl yapılır: Visual Studio'da Office projeleri oluşturma](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
-   [Nasıl yapılır: Office çözümlerini yükseltme](http://msdn.microsoft.com/en-us/a269e539-b717-4680-a568-2152b070347e).  
  
-   [Nasıl yapılır: Office birincil birlikte çalışma derlemelerini yükleme](../vsto/how-to-install-office-primary-interop-assemblies.md).  
  
-   [Nasıl yapılır: birincil birlikte çalışma derlemeleriyle Office uygulamalarını](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md).  
  
-   [Nasıl yapılır: Office projelerinde olay işleyicileri oluşturma](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
-   [Nasıl yapılır: kod çalıştırmadan Office çözümlerini açma](../vsto/how-to-open-office-solutions-without-running-code.md).  
  
-   [Nasıl yapılır: Office çözümü için yapılandırma bilgilerini ayarlama](../vsto/how-to-set-up-configuration-information-for-an-office-solution.md).  
  
-   [Nasıl yapılır: Şeritte Geliştirici sekmesini gösterme](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
-   [Nasıl yapılır: eklenti kullanıcı arayüzü hatalarını gösterme](../vsto/how-to-show-add-in-user-interface-errors.md).  
  
##  <a name="ui"></a>Kullanıcı arabirimi özelleştirme görevleri  
  
### <a name="controls-on-documents-and-worksheets"></a>Belgeler ve çalışma sayfası üzerinde denetimleri  
  
-   [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md).  
  
-   [Nasıl yapılır: çalışma sayfalarına NamedRange denetimleri ekleme](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
-   [Nasıl yapılır: çalışma sayfalarına ListObject denetimleri ekleme](../vsto/how-to-add-listobject-controls-to-worksheets.md).  
  
-   [Nasıl yapılır: Windows Forms denetimleri Office belgelerine ekleme](../vsto/how-to-add-windows-forms-controls-to-office-documents.md).  
  
-   [Nasıl yapılır: Word belgelerine içerik denetimleri ekleme](../vsto/how-to-add-content-controls-to-word-documents.md).  
  
-   [Nasıl yapılır: Word belgelerine yer işareti denetimi ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md).  
  
### <a name="task-panes-in-document-level-customizations"></a>Belge düzeyi özelleştirmelerinde görev bölmeleri  
  
-   [Nasıl yapılır: Word belgelerini ve Excel çalışma kitaplarına Eylemler bölmesi ekleme](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md).  
  
### <a name="task-panes-in-vsto-add-ins"></a>VSTO eklentilerinde görev bölmeleri  
  
-   [Nasıl yapılır: uygulamaya özel görev bölmesi ekleme](../vsto/how-to-add-a-custom-task-pane-to-an-application.md).  
  
### <a name="ribbon-customizations"></a>Şerit özelleştirmelerini  
  
-   [Nasıl yapılır: Şerit özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md).  
  
-   [Nasıl yapılır: Şeritteki sekmenin konumunu değiştirme](../vsto/how-to-change-the-position-of-a-tab-on-the-ribbon.md).  
  
-   [Nasıl yapılır: yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md).  
  
-   [Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md).  
  
-   [Nasıl yapılır: Şerit XML Şerit Tasarımcısından Şerit Dışarı](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md).  
  
### <a name="outlook-form-regions"></a>Outlook Form bölgeleri  
  
-   [Nasıl yapılır: Outlook eklenti projesine Form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
-   [Nasıl yapılır: Outlook Form bölgesini görüntülemesini engelleme](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md).  
  
### <a name="custom-menus"></a>Özel menüler  
  
-   [Nasıl yapılır: kısayol menülerine komut eklemek](../vsto/how-to-add-commands-to-shortcut-menus.md).  
  
##  <a name="excel"></a>Excel otomasyon görevleri  
  
-   [Nasıl yapılır: program aracılığıyla çalışma sayfası hücresinde dize görüntüleme](../vsto/how-to-programmatically-display-a-string-in-a-worksheet-cell.md).  
  
-   [Nasıl yapılır: program aracılığıyla yeni çalışma kitapları oluşturma](../vsto/how-to-programmatically-create-new-workbooks.md).  
  
-   [Nasıl yapılır: program aracılığıyla çalışma kitaplarını açma](../vsto/how-to-programmatically-open-workbooks.md).  
  
-   [Nasıl yapılır: çalışma kitaplarını program aracılığıyla kaydetme](../vsto/how-to-programmatically-save-workbooks.md).  
  
-   [Nasıl yapılır: program aracılığıyla çalışma kitaplarını kapatma](../vsto/how-to-programmatically-close-workbooks.md).  
  
-   [Nasıl yapılır: program aracılığıyla yeni çalışma sayfaları çalışma kitaplarına ekleme](../vsto/how-to-programmatically-add-new-worksheets-to-workbooks.md).  
  
-   [Nasıl yapılır: çalışma sayfalarını program aracılığıyla gizleme](../vsto/how-to-programmatically-hide-worksheets.md).  
  
-   [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki çalışma sayfalarını taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md).  
  
-   [Nasıl yapılır: çalışma kitaplarını program aracılığıyla koruma](../vsto/how-to-programmatically-protect-workbooks.md).  
  
-   [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına başvuran](../vsto/how-to-programmatically-refer-to-worksheet-ranges-in-code.md).  
  
-   [Nasıl yapılır: program aracılığıyla çalışma kitaplarındaki aralıklara stilleri uygulamak](../vsto/how-to-programmatically-apply-styles-to-ranges-in-workbooks.md).  
  
-   [Nasıl yapılır: program aracılığıyla seçili hücreler içeren çalışma sayfalarındaki satırlarda biçimlendirmeyi değiştirme](../vsto/how-to-programmatically-change-formatting-in-worksheet-rows-containing-selected-cells.md).  
  
-   [Nasıl yapılır: program aracılığıyla çalışma sayfası aralıklarına metin arama](../vsto/how-to-programmatically-search-for-text-in-worksheet-ranges.md).  
  
-   [Nasıl yapılır: çalışma sayfalarını program aracılığıyla yazdırma](../vsto/how-to-programmatically-print-worksheets.md).  
  
-   [Nasıl yapılır: Excel hesaplarını program aracılığıyla çalıştırma](../vsto/how-to-programmatically-run-excel-calculations-programmatically.md).  
  
-   [Nasıl yapılır: çalışma sayfalarında verileri programlamayla sıralama](../vsto/how-to-programmatically-sort-data-in-worksheets.md).  
  
##  <a name="word"></a>Word otomasyon görevleri  
  
-   [Nasıl yapılır: program aracılığıyla yeni belgeler oluşturma](../vsto/how-to-programmatically-create-new-documents.md).  
  
-   [Nasıl yapılır: varolan belgeleri program aracılığıyla açma](../vsto/how-to-programmatically-open-existing-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla belgeleri kaydetme](../vsto/how-to-programmatically-save-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla belgeleri kapatma](../vsto/how-to-programmatically-close-documents.md).  
  
-   [Nasıl yapılır: Word belgelerine program aracılığıyla metin ekleme](../vsto/how-to-programmatically-insert-text-into-word-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla tanımlamak ve belgelerde aralıkları seçmek](../vsto/how-to-programmatically-define-and-select-ranges-in-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla sıfırlama Word belgelerinde aralıkları](../vsto/how-to-programmatically-reset-ranges-in-word-documents.md).  
  
-   [Nasıl yapılır: belgelerde metni program aracılığıyla biçimlendirme](../vsto/how-to-programmatically-format-text-in-documents.md).  
  
-   [Nasıl yapılır: Word belgelerine XMLNode denetimleri ekleme](../vsto/how-to-add-xmlnode-controls-to-word-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla, yer işareti metnini güncelleştirme](../vsto/how-to-programmatically-update-bookmark-text.md).  
  
-   [Nasıl yapılır: program aracılığıyla arama ve değiştirme belgelerdeki metni](../vsto/how-to-programmatically-search-for-and-replace-text-in-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla belgeleri yazdırma](../vsto/how-to-programmatically-print-documents.md).  
  
-   [Nasıl yapılır: program aracılığıyla Word tabloları oluşturma](../vsto/how-to-programmatically-create-word-tables.md).  
  
-   [Nasıl yapılır: program aracılığıyla Word tablolarına satır ve sütun ekleme](../vsto/how-to-programmatically-add-rows-and-columns-to-word-tables.md).  
  
-   [Nasıl yapılır: program aracılığıyla belgelerdeki karakterleri sayma](../vsto/how-to-programmatically-count-characters-in-documents.md).  
  
##  <a name="data"></a>Veri görevleri  
  
### <a name="data-bound-controls"></a>Veri bağlama denetimleri  
  
-   [Nasıl yapılır: çalışma sayfalarını veritabanı verileriyle doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md).  
  
-   [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md).  
  
-   [Nasıl yapılır: belgeleri hizmet verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-services.md).  
  
-   [Nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md).  
  
-   [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md).  
  
-   [Nasıl yapılır: belgeleri hizmet verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-services.md).  
  
-   [Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
### <a name="cached-data-in-document-level-solutions"></a>Belge düzeyi çözümlerde önbelleğe alınan veriler  
  
-   [Nasıl yapılır: veri kullanımı için çevrimdışı veya sunucuda önbelleğe](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   [Nasıl yapılır: program aracılığıyla bir veri kaynağı Office belgesinden önbelleğe](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md).  
  
-   [Nasıl yapılır: parola korumalı belgede veriyi önbelleğe](../vsto/how-to-cache-data-in-a-password-protected-document.md).  
  
### <a name="custom-xml-data"></a>Özel XML verileri  
  
-   [Nasıl yapılır: belge düzeyi özelleştirmelerine özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-document-level-customizations.md).  
  
-   [Nasıl yapılır: VSTO eklentilerini kullanarak belgelere özel XML bölümleri ekleme](../vsto/how-to-add-custom-xml-parts-to-documents-by-using-vsto-add-ins.md).  
  
##  <a name="server"></a>Sunucu tarafı belge yönetim görevleri  
  
-   [Nasıl yapılır: belgelerden yönetilen kod uzantılarını kaldırma](../vsto/how-to-remove-managed-code-extensions-from-documents.md).  
  
-   [Nasıl yapılır: belgelere yönetilen kod uzantıları ekleme](../vsto/how-to-attach-managed-code-extensions-to-documents.md).  
  
##  <a name="security"></a>Güvenlik görevleri  
  
-   [Nasıl yapılır: Office çözümlerini imzalama](../vsto/how-to-sign-office-solutions.md).  
  
##  <a name="deployment"></a>Dağıtım görevleri  
  
-   [Nasıl yapılır: ClickOnce kullanarak Office çözümü yayımlama](http://msdn.microsoft.com/en-us/2b6c247e-bc04-4ce4-bb64-c4e79bb3d5b8).  
  
-   [Nasıl yapılır: ClickOnce kullanarak bir SharePoint sunucusu için belge düzeyi Office çözümü yayımlama](http://msdn.microsoft.com/en-us/2408e809-fb78-42a1-9152-00afa1522e58).  
  
-   [Nasıl yapılır: ClickOnce Office çözümünü yükleme](http://msdn.microsoft.com/en-us/14702f48-9161-4190-994c-78211fe18065).  
  
-   [Nasıl yapılır: Office çözümlerini çalıştırmak için son kullanıcı bilgisayarlarında Önkoşulları Yükleme](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
-   [Nasıl yapılır: IIS Office çözümleri geliştirme için hazırla](http://msdn.microsoft.com/en-us/f62bce70-81d4-4f8b-86e6-2f2afec5d9b4).  
  
-   [Nasıl yapılır: Dağıtılmış Office çözümlerini güncelleme](http://msdn.microsoft.com/en-us/be96db53-b6ea-46ab-b8d9-b76b098b3b13).  
  
-   [Nasıl yapılır: Office çözümü yükleme konumunu değiştirmek](http://msdn.microsoft.com/en-us/d0eaa07b-2d72-4902-899f-2f9fb165b8fd).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başlarken &#40; Office geliştirme Visual Studio &#41;](../vsto/getting-started-office-development-in-visual-studio.md)   
 [Office uygulaması ve proje türüne göre kullanılabilir özellikler](../vsto/features-available-by-office-application-and-project-type.md)   
 [Office geliştirme örnekleri ve izlenecek yollar](../vsto/office-development-samples-and-walkthroughs.md)  
  
  