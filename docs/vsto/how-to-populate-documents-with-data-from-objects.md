---
title: 'Nasıl yapılır: belgeleri nesne verileriyle doldurma | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], populating with data
- data [Office development in Visual Studio], adding to documents
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: baac72889a34474157bd89e151f6e63c19968fbb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-populate-documents-with-data-from-objects"></a>Nasıl Yapılır: Belgeleri Nesne Verileriyle Doldurma
  Windows Forms projelerindeki gibi bir veri nesnesi belirtilmemelidir verileri Microsoft Office Word için belge düzeyi projelerine aynı şekilde çalışır. Verileri bir nesneden çözümünüze getirmek için aynı araçları ve kod kullanmak ve verileri görüntülemek için Windows Forms denetimleri kullanabilirsiniz. Ayrıca, ana bilgisayar denetimleri kullanarak verileri görüntüleyebilirsiniz. Konak denetimleri, olaylar ve veri bağlama özelliğiyle geliştirilmiş yerel Microsoft Office Word nesneleridir. Daha fazla bilgi için bkz: [konak öğelerine ve denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
 Belgeyi bir nesneden verilerle doldurmak için üç temel adımları tamamlamanız gerekir:  
  
-   Veriye bağlayabilirsiniz belge için bir denetim ekleyin.  
  
-   Bir veri nesnesi belgeye ekleyin.  
  
-   Veri nesnesi BindingSource bağlayın.   
  
## <a name="adding-a-data-object"></a>Veri nesnesi ekleme  
  
#### <a name="to-add-a-data-object"></a>Bir veri nesnesi eklemek için  
  
-   Açık **veri kaynakları** penceresi ve bir nesneden bir veri kaynağı oluşturun. Daha fazla bilgi için bkz: [yeni veri kaynakları ekleyin](/visualstudio/data-tools/add-new-data-sources).  
  
## <a name="connecting-the-data-object-to-the-bindingsource"></a>Veri nesnesi BindingSource bağlanma  
 Belge düzeyi projelerine belgenize denetimleri ekleyebilir ve bunları tasarım zamanında verilere bağlayın.  
  
 VSTO eklentisi projelerine denetimleri oluşturmak ve çalışma zamanında bağlayın.  
  
### <a name="document-level-projects"></a>Belge düzeyi projelerine  
  
##### <a name="to-connect-the-data-object-to-the-bindingsource"></a>Veri nesnesi BindingSource bağlanmak için  
  
1.  İstediğiniz verileri alan sürükleyin **veri kaynakları** belgenizi penceresine. Bu denetim otomatik olarak oluşturur.  
  
2.  Kodunuzda, veri kaynağı için seçtiğiniz nesnenin türü örneği oluşturun.  
  
3.  Örneğine atadığınız <xref:System.Windows.Forms.BindingSource.DataSource%2A> özelliği <xref:System.Windows.Forms.BindingSource>.  
  
### <a name="application-level-projects"></a>Uygulama düzeyi projeleri  
  
##### <a name="to-connect-the-data-object-to-the-bindingsource"></a>Veri nesnesi BindingSource bağlanmak için  
  
1.  Kodunuzda, veri kaynağıyla ilişkilendirilmiş nesne türünün bir örneği oluşturun.  
  
2.  Bir örneğini oluşturmak bir <xref:System.Windows.Forms.BindingSource>.  
  
3.  Veri kaynağı örneği atayın <xref:System.Windows.Forms.BindingSource.DataSource%2A> özelliği <xref:System.Windows.Forms.BindingSource>.  
  
4.  Veri kaynağı denetimine veri bağlama olarak ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
 [Yeni veri kaynakları ekleyin](/visualstudio/data-tools/add-new-data-sources)   
 [Visual Stduio verilere Windows Forms denetimleri bağlama](/visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio)
 
 [Nasıl yapılır: belgeleri veritabanı verileriyle doldurma](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Nasıl yapılır: konak kontrolü verileriyle veri kaynağını güncelleme](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md)   
 [Windows Forms uygulamalarındaki verilere bağlanma](/visualstudio/data-tools/connecting-to-data-in-windows-forms-applications)   
 [BindingSource Bileşenine Genel Bakış](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
  