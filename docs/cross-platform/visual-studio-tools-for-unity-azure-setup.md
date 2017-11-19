---
title: "Unity Azure izlenecek kurulumu için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: FFE17FC6-0B47-4A00-A125-01BD49E3873C
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 447f32c2e736084a08223b56f4188ca7c8abeea5
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="create-easy-tables"></a>Kolay tabloları oluşturma

Kolay başlatılmış tablolar ile azure'da bir mobil uygulama sahip olduğunuza göre yapı Unity oyununuzu gönderilen verileri izlemek tabloları zamanı geldi.

## <a name="setup-the-crash-heatmap-table"></a>Kurulum kilitlenme heatmap tablo

1. Azure Portalı'ndaki tüm kaynaklar'ı tıklatın ve kolay tablolar için önceki adımlarda yapılandırılmış mobil uygulamayı seçin.

  ![Mobil uygulama seçin](media/vstu_azure-setup-table-schema-image1.png)

2. Ekranı aşağı kaydırarak **mobil** seçin ve başlık **kolay tabloları**. Artık uygulamanızı kolay tablolar için başlatma hakkında tüm bildirim olmalıdır.  

  ![Kolay tabloları seçin](media/vstu_azure-setup-table-schema-image2.png)

3. Tıklatın **Ekle** düğmesi.

  ![Ekle'yi tıklatın](media/vstu_azure-setup-table-schema-image3.png)

4. Tablo adı "**CrashInfo**" tıklatıp **Tamam**. Geri kalan varsayılan ayarlarına seçeneklerinin bırakın.

  > [!WARNING]
  > Bu ad, izlenecek yolla oluşturulan veri modeli sınıfının adı eşleşmelidir.

  ![Ad ve Tamam'ı tıklatın](media/vstu_azure-setup-table-schema-image4.png)

5. Yeni bir tablo oluştururken bir bildirim Duyurusu.

> [!NOTE]
> Veriler eklendikçe kolay tablolarla tablo şemasını gerçekte dinamik olarak oluşturulur. Başka bir deyişle, uygun veri sütunlarını el ile bu adım sırasında ayarlanmış olması gerekmez.

## <a name="setup-the-leaderboard-table"></a>Kurulum Skorbordu tablo

1. Kolay tabloları dikey penceresine geri dönün ve tıklatın **Ekle** ikinci tablo eklemek için.

  ![İkinci tablo ekleme](media/vstu_azure-setup-table-schema-image10.png)

2. Yeni bir tablo adı "**HighScoreInfo**" tıklatıp **Tamam**. Seçeneklerin geri kalanı kendi varsayılan ayarlarında bırakın.

  > [!WARNING]
  > Bu ad, izlenecek yolla oluşturulan veri modeli sınıfının adı eşleşmelidir.

  ![Ad ve Tamam'ı tıklatın](media/vstu_azure-setup-table-schema-image11.png)

3. Yeni bir tablo oluştururken bir bildirim Duyurusu.


## <a name="next-step"></a>Sonraki adım

* [Geliştirme ortamını hazırlayın](visual-studio-tools-for-unity-azure-prepare.md)
