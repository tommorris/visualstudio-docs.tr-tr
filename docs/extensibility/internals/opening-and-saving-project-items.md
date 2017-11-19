---
title: "Açma ve proje öğeleri kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], file persistence
- files [Visual Studio], opening and saving
- editors [Visual Studio SDK], file persistence
ms.assetid: f71898ad-335f-4c43-a177-4da87078afd1
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a30589591a7cef60ecfb19945366f8fcf539da02
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="opening-and-saving-project-items"></a>Açıp kaydederek proje öğeleri
Yeni bir proje türü eklediğinizde, projeler dosyalarınızda kaydetme ve açma yönetmelisiniz [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] tümleşik geliştirme ortamı (IDE). Aşağıdaki konular, dosyaları açma ve kaydetme için farklı yaklaşımlara tartışın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Dosya Aç komutu kullanarak dosyaları görüntüleme](../../extensibility/internals/displaying-files-by-using-the-open-file-command.md)  
 IDE nasıl işlediği hakkında ile ilgili adım adım bir açıklama sağlar **açık dosya** komutu ve bu komutuna yanıt olarak projeleri rol.  
  
 [Aç komutunu kullanarak dosyaları görüntüleme](../../extensibility/internals/displaying-files-by-using-the-open-with-command.md)  
 IDE nasıl işlediğini bir ayrıntılı, adım adım açıklama sağlar **birlikte Aç** bazı standart düzenleyicileri seçimine sahip bir dosyayı açma isteyen komutu.  
  
 [Nasıl yapılır: açık projeye özgü düzenleyiciler](../../extensibility/how-to-open-project-specific-editors.md)  
 Projenizdeki belirli bir türdeki dosyaları bir projeye özgü Düzenleyicisi'ni kullanarak açılmalıdır belirtmek için adım adım yönergeler sağlar.  
  
 [Nasıl yapılır: standart düzenleyicileri açın](../../extensibility/how-to-open-standard-editors.md)  
 Proje türünüz dosyaları için standart bir düzenleyici açmak IDE etkinleştirme belirtmek için adım adım yönergeler sağlar.  
  
 [Nasıl yapılır: açık belgeler için düzenleyicileri açın](../../extensibility/how-to-open-editors-for-open-documents.md)  
 Açık bir dosya için bir proje özgü düzenleyici açmak için adım adım yönergeler sağlar.  
  
 [Standart belgeyi kaydetme](../../extensibility/internals/saving-a-standard-document.md)  
 IDE nasıl işlediği hakkında ile ilgili ayrıntılı bir açıklama sağlar **kaydetmek**, **Kaydet**, ve **Tümünü Kaydet** komutları bir belge için bir standart Düzenleyicisi'nde açılır.  
  
 [Özel belge kaydetme](../../extensibility/internals/saving-a-custom-document.md)  
 Bir diyagram ve IDE nasıl işlediğini konusunda ayrıntılı bilgi sağlar **kaydetmek**, **Kaydet**, ve **Tümünü Kaydet** komutları belgeler için özel bir düzenleyici açılır.  
  
 [Proje dosyasında Düzenleyicisi açan belirleme](../../extensibility/internals/determining-which-editor-opens-a-file-in-a-project.md)  
 IDE uygun Düzenleyicisi'ni veya bir dosya için tasarımcı seçmek için aşağıdaki ele alınmaktadır.  
  
## <a name="related-sections"></a>İlgili Bölümler  
 [Özel düzenleyicileri ve tasarımcıları oluşturma](../../extensibility/creating-custom-editors-and-designers.md)  
 IDE barındırabilir ve her Düzenleyici açıklamalarını verir düzenleyicileri dört türlerini listeler.  
  
 [Proje türleri](../../extensibility/internals/project-types.md)  
 Nasıl projeleri kod derlenmiş ve yerleşik şeklini denetlemek, düzenleyiciler nasıl açıldığı ve proje öğeleri nasıl biçimlendirileceğini anlatılmaktadır.