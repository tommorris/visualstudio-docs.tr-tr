---
title: "Nasıl yapılır: belgeleri hizmet verileriyle doldurma | Microsoft Docs"
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
- documents [Office development in Visual Studio], populating with data
- Web services [Office development in Visual Studio], populating documents
- data [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: eb06e77cf45a3c912f569686cdbe246baece8a03
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-populate-documents-with-data-from-services"></a>Nasıl Yapılır: Belgeleri Hizmet Verileriyle Doldurma
  Windows Forms projelerindeki gibi veri erişimi için Microsoft Office belge düzeyi projelerine aynı şekilde çalışır. Çözümünüze verileri getirmek için aynı araçları ve kod kullanmak ve verileri görüntülemek için bile Windows Forms denetimleri kullanabilirsiniz. Ayrıca, Microsoft Office Excel ve Microsoft Office Word olayları ve veri bağlama özelliğiyle geliştirilmiş yerel nesneler olan konak kontrollerinden yararlanabilir. Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Aşağıdaki örnek, verilere bağlı denetimler tasarım zamanında belgelere ekleme gösterilmektedir. Verilere bağlı denetimler çalışma zamanında VSTO eklentiler ekleme konusunda bir örneği için bkz [izlenecek yol: veri bağlamanın bir VSTO içinde hizmet eklenti proje](../vsto/walkthrough-binding-to-data-from-a-service-in-a-vsto-add-in-project.md).  
  
 ![video bağlantı](../vsto/media/playvideo.gif "video bağlantı") ilgili video gösterimi için bkz: [nasıl yapmak I: etkileşimde Microsoft Excel Web hizmetlerinden?](http://go.microsoft.com/fwlink/?LinkID=130284).  
  
### <a name="to-populate-a-document-level-project-with-data-from-a-web-service"></a>Belge düzeyi proje bir Web hizmeti verilerle doldurmak için  
  
1.  Açık **veri kaynakları** penceresi ve projeniz için bir veri kaynağı hizmeti oluşturun. Daha fazla bilgi için bkz: [yeni veri kaynakları ekleyin](/visualstudio/data-tools/add-new-data-sources).  
  
2.  Tablo veya istediğiniz alanı sürükleyin **veri kaynakları** belgenizi penceresine.  
  
     Bir denetim belge üzerinde oluşturulan bir <xref:System.Windows.Forms.BindingSource> oluşturulur projenizi nesne sınıfında bağlanır ve sınıflar, hizmet için oluşturulur.  
  
3.  Kodunuzda, 1. adımda bağlı Web hizmeti sınıfının bir örneğini oluşturun.  
  
4.  Web hizmeti ile iletişim için gerekli olan özellikleri varsa, bu özelliklerin örneklerini oluşturun.  
  
5.  Oluşturun ve 4. adımda oluşturduğunuz Web hizmeti ve hiç özelliği örneği tarafından kullanıma sunulan yöntemleri kullanarak veri isteği gönderin.  
  
     Kullandığınız yöntem, Web hizmetini sunar bağlıdır.  
  
6.  Web hizmetine veri yanıtını atayın <xref:System.Windows.Forms.BindingSource.DataSource%2A> özelliği <xref:System.Windows.Forms.BindingSource>.  
  
 Projeyi çalıştırdığınızda denetimleri veri kaynağındaki ilk kaydı görüntüler. Nesneleri kullanarak para birimi olayları işleyerek kayıtlarda kaydırma etkinleştirebilirsiniz <xref:System.Windows.Forms.BindingSource>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Office çözümlerinde denetimlere veri bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Yeni veri kaynakları ekleyin](/visualstudio/data-tools/add-new-data-sources)   
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Nasıl yapılır: çalışma sayfalarını veritabanı verileriyle doldurma](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Nasıl yapılır: belgeleri nesne verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Nasıl Yapılır: Konak Kontrolü Verileriyle Veri Kaynağını Güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)  
  
  