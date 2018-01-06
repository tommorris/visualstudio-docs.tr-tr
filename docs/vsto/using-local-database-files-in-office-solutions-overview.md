---
title: "Office çözümleri genel bakış yerel veritabanı dosyaları kullanarak | Microsoft Docs"
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
- Office applications [Office development in Visual Studio], data
- data [Office development in Visual Studio], local
- local data [Office development in Visual Studio]
ms.assetid: 7a920e6b-f0c3-4a62-b5dd-02668a6177b6
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9d807c38af14249b265c411de31f6cde03855c60
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-local-database-files-in-office-solutions-overview"></a>Office Çözümlerinde Yerel Veritabanı Dosyaları Kullanmaya Genel Bakış
  Bir SQL Server Express (.mdf) veya bir Microsoft Office Access (.mdb) dosyası gibi bir veritabanı dosyası Office çözümünüzde içerebilir. Bu, son kullanıcıların merkezi veritabanı bakımının örneğin yalnızca tek bir bilgisayarda kullanılan bir yerel stok çözümüne gerekli olduğu durumlarda yerel bir veritabanı bulundurmanız sağlar.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="importing-the-database-file-into-a-project"></a>Veritabanı dosyası bir projeye içeri aktarma  
 Veritabanı dosyasını projenize içeri aktarmak için kullanın **veri kaynağı Yapılandırma Sihirbazı** veritabanı dosyasına dayalı bir veri kaynağı oluşturmak için. Sihirbaz, veritabanı dosyası ve bir türü belirtilmiş veri kümesi projenize ekler.  
  
## <a name="deploying-the-database-file"></a>Veritabanı dosyasını dağıtma  
 **Veri kaynağı Yapılandırma Sihirbazı** yerel veritabanı dosyasına bağlantılar oluşturmak için göreli bir yol kullanır. Bu, dosyaların göreli konumları sahipseniz çözümü bir bilgisayardan diğerine kopyalamak sağlar.  
  
 Bir sunucuya çözümünüzü dağıtmak ve sonra belgeyi her son kullanıcıya dağıtın, gerekir el ile de veritabanı dosyasını dağıtın ve aynı konumda yer alan belge göre yükleyin. Çözemiyorsa veritabanı dosyasını da taşır sürece bu, son kullanıcı kendi bilgisayarda yeni bir konuma belge taşıyamazsınız anlamına gelir.  
  
## <a name="local-database-files-and-caching-the-dataset"></a>Yerel veritabanı dosyaları ve veri kümesi önbelleğe alma  
 Microsoft Office Excel ve Microsoft Office Word için belge düzeyi çözümlerde, belge kümelerinde öznitelik dataset örneğiyle işaretleyerek önbelleğe alabilirsiniz <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute>. Eklediğinizde veritabanı dosyasını projenize kullanarak **veri kaynağı Yapılandırma Sihirbazı**, türü belirtilmiş veri kümesi projenize otomatik olarak eklenir. Uygulanacak nadiren gereklidir <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> bu veri kümesine veri zaten kullanıcının bilgisayarında yerel olduğundan. Daha fazla bilgi için bkz: [veri önbelleğe alma](../vsto/caching-data.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Office çözümü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Verileri Önbelleğe Alma](../vsto/caching-data.md)  
  
  