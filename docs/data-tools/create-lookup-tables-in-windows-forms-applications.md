---
title: Windows Forms uygulamalarında arama tabloları oluşturma
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- lookup tables
- lookup tables, creating
ms.assetid: 0edd5385-c381-4b17-9096-74e2778db9d5
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 315bed179a21ec99a256fcc8cb16f6fc1164f238
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="create-lookup-tables-in-windows-forms-applications"></a>Windows Forms uygulamalarında arama tabloları oluşturma
Terim *arama tablosu* iki ilgili veri tablolarına bağlı denetimler açıklanmıştır. Bu arama denetimleri ikinci tabloda seçilen bir değere göre ilk tablodan veri görüntüler.

 Arama tabloları üst tablo ana düğümünün sürükleyerek oluşturabileceğiniz (gelen [veri kaynakları penceresi](add-new-data-sources.md)) formunuzda ilgili alt tablo sütununa bağlı bir denetim üzerine.

 Örneğin, bir içindekiler göz önünde bulundurun `Orders` bir satış veritabanında. Her bir kayıtta `Orders` tabloyu içeren bir `CustomerID`, hangi müşteri siparişin belirten. `CustomerID` Bir müşteri kaydına işaret eden bir yabancı anahtar `Customers` tablo. Bu senaryoda, genişletin `Orders` tablosundaki **veri kaynakları** penceresi ve ana düğüm kümesi **ayrıntıları**. Ardından `CustomerID` kullanmak için sütun bir <xref:System.Windows.Forms.ComboBox> (veya arama bağlama destekleyen herhangi bir denetim) ve sürükleyin `Orders` formunuza düğümü. Son olarak, sürükleyin `Customers` ilgili sütununa bağlı denetim düğüme — bu durumda, <xref:System.Windows.Forms.ComboBox> bağlı `CustomerID` sütun.

## <a name="to-databind-a-lookup-control"></a>DataBind bir arama denetimi

1.  Açık **veri kaynakları** penceresi.

    > [!NOTE]
    >  Arama tabloları gerektiren iki ilişkili tablolar veya nesneler bulunan **veri kaynakları** penceresi. Daha fazla bilgi için bkz: [kümelerindeki ilişkiler](relationships-in-datasets.md).

2.  Düğümleri genişletin **veri kaynakları** üst tablo ve tüm alt sütunlar ve ilgili alt tablo ve tüm sütunları görene kadar penceresi.

    > [!NOTE]
    >  Alt tablo düğüm üst tablo bir Genişletilebilir alt düğüm olarak görünür olandır.

3.  Alt tabloya açılan türünü değiştirme **ayrıntıları** seçerek **ayrıntıları** alt tablonun düğüm üzerinde denetim listesinden. Daha fazla bilgi için bkz: [veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

4.  İki tablo ilişkili düğümünü bulun ( `CustomerID` önceki örnekte düğüm). Açılan türünü değiştirme bir <xref:System.Windows.Forms.ComboBox> seçerek **ComboBox** denetim listesinde.

5.  Ana alt tablo düğümden sürükleyin **veri kaynakları** formunuza penceresi.

     Veri bağlama denetimleri (tanımlayıcı etiketlerle) ve bir aracı Şerit (<xref:System.Windows.Forms.BindingNavigator>) form üzerinde görüntülenir. A [DataSet](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, ve <xref:System.Windows.Forms.BindingNavigator> bileşen tepsisinde görünür.

6.  Şimdi ana üst tablo düğümden sürükleyin **veri kaynakları** pencere arama denetimi doğrudan üzerine ( <xref:System.Windows.Forms.ComboBox>).

     Arama bağlamaları şimdi oluşturulur. Denetimi ayarlanan belirli özellikler için aşağıdaki tabloya bakın.

    |Özellik|Ayar açıklaması|
    |--------------|----------------------------|
    |**veri kaynağı**|Visual Studio bu özelliği ayarlar <xref:System.Windows.Forms.BindingSource> denetimini üzerine sürüklediğiniz tablo için oluşturulan (tersine <xref:System.Windows.Forms.BindingSource> denetimi oluşturulduğunda oluşturulan).<br /><br /> Bir düzeltme yapmanız gerekirse, ardından bu kümesine <xref:System.Windows.Forms.BindingSource> tablosunun görüntülemek istediğiniz sütun.|
    |**DisplayMember**|Visual Studio bu özellik bir dize veri türünde denetime sürükleyin tablosu için birincil anahtar sonra ilk sütun ayarlar.<br /><br /> Bir düzeltme yapmanız gerekirse, bu görüntülemek istediğiniz sütun adına ayarlayın.|
    |**ValueMember**|Visual Studio, birincil anahtarda yer alan ilk sütunun veya tablonun ilk sütunu için bu özelliği ayarlar, bir anahtar tanımlanmamışsa varsa.<br /><br /> Bir düzeltme yapmanız gerekirse, sonra bu görüntülemek istediğiniz sütun ile tablosundaki birincil anahtar ayarlayın.|
    |**SelectedValue**|Visual Studio gelen bırakılan özgün sütun için bu özelliği ayarlar **veri kaynakları** penceresi.<br /><br /> Bir düzeltme yapmanız gerekirse, ardından bunu ilgili tablosundaki yabancı anahtar sütunu için ayarlayın.|

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)