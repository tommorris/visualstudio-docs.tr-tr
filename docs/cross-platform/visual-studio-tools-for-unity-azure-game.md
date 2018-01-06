---
title: "Unity Azure izlenecek oyun için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: DA86FC7F-E456-4DFC-84BF-D780421508B9
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 7d0a7da4093b8f90ab76dee55f1ec9ad6dc21679
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="test-the-sample-game"></a>Örnek oyunu sınayın

Örnek oyun oyuncunun davranış hakkında verileri kaydeder ve Azure kolay tablolarda depolayan basit yarış oyun ' dir. Örnek oyun Azure'dan veri okumak ve player için görselleştirmek planda de içerir.

Bu bölüm yalnızca örnek oyun ve düzgün çalıştığından emin açıklanacaktır. Sonraki bölümlerde örnek oyun nasıl çalıştığını açıklayan daha fazla ayrıntıya gider.

## <a name="starting-the-game"></a>Oyun başlatma

1. Unity proje penceresinde gidin **varlıklar/Azure kolay tabloları örnek oyun varlıklar/planda** klasör.

2. Çift tıklayarak **MenuScene** açın.

3. Unity oyununuzu penceresinde **en boy oranını açılır** ve **16:9**.

  ![Kümesi en boy oranı](media/vstu_azure-test-sample-game-image1.png)

4. Tıklatın **Yürüt** oyun Unity Düzenleyicisi'nde çalıştırmak için düğmesi.


## <a name="complete-a-race"></a>Bir yarış tamamlayın

Skorbordu veya heatmap görüntülemeden önce en az bir kez yarış tamamlayarak bazı örnek verileri oluşturmak en iyisidir.

1. Unity Düzenleyicisi'nde çalışan oyuna tıklayın **yarış!** Yeni bir yarış başlamak için Başlat'ı tıklatın.

2. Kullanım **WASD** veya **ok tuşları** arabayı ve izleme etrafında saat yönünde diz tamamlayın. Örnek amacıyla bazı duvarları yol içine kilitlenme emin olun. Bir çakışma kaydedilirken konsol belirtmelidir Unity çıktısında hata ayıklama.

  >[!NOTE]
  > Arabayı çevrilecek yönetmek ve devam etmek sorun yaşıyor **yeniden**. Veriler, yalnızca bir diz tamamladıktan sonra Azure'a gönderilir.

  ![Bir yarış Başlat](media/vstu_azure-test-sample-game-image2.png)

3. Damalı bitiş satırını geçmesinden sonra oyun görüntülemesi gereken bir **tamamlandı** ileti. Bu noktada, kilitlenme verilerini Azure'a yüklenecek.

4. İlk 10 hızlı diz birini tamamladıysanız, istenir yüksek bir puan için bir ad girmeyi zaman. Adınızı girin ve tıklayın **gönderme**.

  ![Bir yarış Başlat](media/vstu_azure-test-sample-game-image3.png)

## <a name="view-the-heatmap"></a>Görünüm heatmap

1. Tıklatın **görünüm kilitlenme Heatmap** düğmesini yarış Sahne veya seçin **kilitlenme Heatmap** ana menüden.

2. Heatmap Sahne Azure CrashInfo tablodaki verileri yükler ve saydam bir kırmızı kürenin oynatıcıları yarış izleme duvarları ile burada başvurularla konumlara görüntüler. Çakışan bir alanda birden çok çökme (Crash) meydana gelirse, Küreler daha açık görünmesi gerekir.

  ![Heatmap](media/vstu_azure-test-sample-game-image4.png)

## <a name="view-the-leaderboard"></a>Görünüm Skorbordu

1. Tıklatın **Skorbordu** yarış Sahne veya ana menü düğmesi.

2. Yüksek puan Skorbordu Sahne yükler Azure ve görüntüler her yüksek bir oynatıcı adı ve diz zamanı HighScoreInfo tablodan veri puan girişi.

  ![Skorbordu](media/vstu_azure-test-sample-game-image5.png)

## <a name="next-step"></a>Sonraki adım

* [RaceScene açıklaması](visual-studio-tools-for-unity-azure-racescene.md)
