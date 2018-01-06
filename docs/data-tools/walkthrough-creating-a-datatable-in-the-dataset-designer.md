---
title: "İzlenecek yol: veri kümesi tasarımcısında DataTable oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 7df2579f5556e0e35b4203c700ca3f96f46a7d2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-datatable-in-the-dataset-designer"></a>İzlenecek Yol: Veri Kümesi Tasarımcısında DataTable Oluşturma

Bu kılavuzda nasıl oluşturulacağını açıklar bir <xref:System.Data.DataTable> (olmadan bir TableAdapter) kullanarak **veri kümesi Tasarımcısı**. TableAdapters dahil veri tabloları oluşturma hakkında daha fazla bilgi için bkz: [oluşturma ve TableAdapters öğelerini yapılandırma](../data-tools/create-and-configure-tableadapters.md).  

Bu örneklerde gösterilen görevler aşağıdakileri içerir:  

-   Yeni bir Windows Forms uygulaması projesi oluşturma  

-   Yeni bir veri kümesi için uygulama ekleme  

-   Yeni bir veri tablosu veri kümesine ekleme  

-   Veri tablosuna sütun ekleme  

-   Tablonun birincil anahtarı ayarlama  

## <a name="creating-a-new-windows-forms-application"></a>Yeni bir Windows Forms uygulaması oluşturma

### <a name="to-create-a-new-windows-forms-application-project"></a>Yeni bir Windows Forms uygulaması projesi oluşturmak için  
  
1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni**, **proje...** .  
  
2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Klasik Masaüstü**.  

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.  

4. Proje adı **DataTableWalkthrough**ve ardından **Tamam**. 
  
     **DataTableWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.  

## <a name="adding-a-new-dataset-to-the-application"></a>Yeni bir veri kümesi için uygulama ekleme

### <a name="to-add-a-new-dataset-item-to-the-project"></a>Yeni bir veri kümesi öğe projeye eklemek için  
  
1.  Üzerinde **proje** menüsünde, select **Yeni Öğe Ekle...** .  
  
     Yeni Öğe Ekle iletişim kutusu görüntülenir.  
  
2.  Sol bölmede seçin **veri**seçeneğini belirleyip **DataSet** Orta bölmede.  
  
3.  Seçin **eklemek**.  
  
     Visual Studio ekler adlı bir dosya **dataSet1.xsd dosyasını** projeye ve bunun içinde açılacak **veri kümesi Tasarımcısı**.  

## <a name="adding-a-new-datatable-to-the-dataset"></a>Yeni bir DataTable veri kümesine ekleme  

### <a name="to-add-a-new-data-table-to-the-dataset"></a>Yeni bir veri tablosu veri kümesine eklemek için  
  
1.  Sürükleme bir **DataTable** gelen **DataSet** sekmesinde **araç** üzerine **veri kümesi Tasarımcısı**.  
  
     Adlı bir tablo **DataTable1** kümesine eklenir.  
   
2.  Başlık çubuğunu tıklatın **DataTable1** ve yeniden adlandırmak `Music`.  

## <a name="adding-columns-to-the-datatable"></a>DataTable tablosuna sütun ekleme

### <a name="to-add-columns-to-the-datatable"></a>DataTable tablosuna sütun eklemek için  
  
1.  Sağ **müzik** tablo. İşaret **Ekle**ve ardından **sütun**.  
  
2.  Sütun adı `SongID`.  
  
3.  İçinde **özellikleri** penceresindeki ayarlayın <xref:System.Data.DataColumn.DataType%2A> özelliğine <xref:System.Int16?displayProperty=fullName>.  
  
4.  Bu işlemi yineleyin ve aşağıdaki sütunlar ekleyin:  
  
     `SongTitle`: <xref:System.String?displayProperty=fullName>  
  
     `Artist`: <xref:System.String?displayProperty=fullName>  
  
     `Genre`: <xref:System.String?displayProperty=fullName>  
  
## <a name="setting-the-primary-key-for-the-table"></a>Tablonun birincil anahtarı ayarlama

Tüm veri tabloları birincil anahtarı olmalıdır. Bir birincil anahtar, belirli bir kayıt bir veri tablosunda benzersiz olarak tanımlar.  
  
### <a name="to-set-the-primary-key-of-the-data-table"></a>Veri tablonun birincil anahtarı ayarlamak için
  
-   Sağ **SongID** sütun ve ardından **birincil anahtarı ayarlama**.  
  
     Bir anahtar simgesi görünür **SongID** sütun.  
  
## <a name="saving-your-project"></a>Projenizi kaydetme  
  
### <a name="to-save-the-datatablewalkthrough-project"></a>DataTableWalkthrough projeyi kaydetmek için  
  
-   Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da veri kümeleri oluşturma ve yapılandırma](../data-tools/create-and-configure-datasets-in-visual-studio.md)  
[Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)  
[Verileri doğrulama](../data-tools/validate-data-in-datasets.md)  
[Verileri Kaydetme](../data-tools/saving-data.md)