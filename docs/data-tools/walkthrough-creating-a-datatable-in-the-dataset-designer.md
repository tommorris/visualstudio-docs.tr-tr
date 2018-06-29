---
title: 'İzlenecek Yol: Veri Kümesi Tasarımcısında DataTable Oluşturma'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 2e02f01924d5bae2770c579c4bfadd314e03cbe3
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089111"
---
# <a name="walkthrough-create-a-datatable-in-the-dataset-designer"></a>İzlenecek yol: veri kümesi tasarımcısında DataTable oluşturma

Bu kılavuzda nasıl oluşturulacağını açıklar bir <xref:System.Data.DataTable> (olmadan bir TableAdapter) kullanarak **veri kümesi Tasarımcısı**. TableAdapters dahil veri tabloları oluşturma hakkında daha fazla bilgi için bkz: [oluşturma ve TableAdapters öğelerini yapılandırma](../data-tools/create-and-configure-tableadapters.md).

## <a name="create-a-new-windows-forms-application"></a>Yeni bir Windows Forms uygulaması oluşturma

1. Visual Studio'da üzerinde **dosya** menüsünde, select **yeni** > **proje**.

2. Genişletin **Visual C#** veya **Visual Basic** sol bölmesinde, ardından **Windows Masaüstü**.

3. Orta bölmede seçin **Windows Forms uygulaması** proje türü.

4. Proje adı **DataTableWalkthrough**ve ardından **Tamam**.

     **DataTableWalkthrough** projesi oluşturulur ve eklenen **Çözüm Gezgini**.

## <a name="add-a-new-dataset-to-the-application"></a>Yeni bir veri kümesi için uygulama ekleme

1.  Üzerinde **proje** menüsünde, select **Yeni Öğe Ekle**.

     Yeni Öğe Ekle iletişim kutusu görüntülenir.

2.  Sol bölmede seçin **veri**seçeneğini belirleyip **DataSet** Orta bölmede.

3.  Seçin **eklemek**.

     Visual Studio ekler adlı bir dosya **dataSet1.xsd dosyasını** projeye ve bunun içinde açılacak **veri kümesi Tasarımcısı**.

## <a name="add-a-new-datatable-to-the-dataset"></a>Yeni DataTable kümesine ekleme

1.  Sürükleme bir **DataTable** gelen **DataSet** sekmesinde **araç** üzerine **veri kümesi Tasarımcısı**.

     Adlı bir tablo **DataTable1** kümesine eklenir.

2.  Başlık çubuğunu tıklatın **DataTable1** ve yeniden adlandırmak `Music`.

## <a name="add-columns-to-the-datatable"></a>DataTable tablosuna sütun ekleme

1.  Sağ **müzik** tablo. İşaret **Ekle**ve ardından **sütun**.

2.  Sütun adı `SongID`.

3.  İçinde **özellikleri** penceresindeki ayarlayın <xref:System.Data.DataColumn.DataType%2A> özelliğine <xref:System.Int16?displayProperty=fullName>.

4.  Bu işlemi yineleyin ve aşağıdaki sütunlar ekleyin:

     `SongTitle`: <xref:System.String?displayProperty=fullName>

     `Artist`: <xref:System.String?displayProperty=fullName>

     `Genre`: <xref:System.String?displayProperty=fullName>

## <a name="set-the-primary-key-for-the-table"></a>Tablonun birincil anahtarı ayarlayın

Tüm veri tabloları birincil anahtarı olmalıdır. Bir birincil anahtar, belirli bir kayıt bir veri tablosunda benzersiz olarak tanımlar.

Birincil anahtarını ayarlamak için sağ **SongID** sütun ve ardından **birincil anahtarı ayarlama**. Bir anahtar simgesi görünür **SongID** sütun.

## <a name="save-your-project"></a>Projeyi kaydedin

DataTableWalkthrough proje üzerinde kaydetmek için **dosya** menüsünde, select **Tümünü Kaydet**.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio’da veri kümeleri oluşturma ve yapılandırma](../data-tools/create-and-configure-datasets-in-visual-studio.md)
- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Verileri doğrulama](../data-tools/validate-data-in-datasets.md)