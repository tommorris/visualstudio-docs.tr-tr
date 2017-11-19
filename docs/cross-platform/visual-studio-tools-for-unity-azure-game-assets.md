---
title: "Unity Azure izlenecek oyun varlıklar için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: C06FAB2E-F592-4EFF-B96A-58858C92DCEB
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 3b1ad3d7dc6af48986e8b10278a8b8135843239d
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="import-sample-game-assets"></a>Örnek oyun varlıkları alma

Çekirdek işlevselliğini test ve çalıştığı ortaya göre örnek oyun varlıklar alma zamanı geldi.

## <a name="import-package"></a>Paketi İçeri Aktar

1. Karşıdan [örnek oyun varlıklar paketi](https://github.com/dantogno/UnityAzureSample/blob/master/Azure%20Easy%20tables%20sample%20game%20assets.unitypackage).

2. Unity projeniz açıktır emin olun, sonra yükleme konumuna gidin ve dosyasına çift tıklayın. Bu içeri aktarma iletişim kutusunda Unity getirir.

3. Tıklatın **tüm** ve ardından **alma**. Tamamlanması için sonuçta elde edilen ilerleme çubukları bekleyin.

  ![Paketi İçeri Aktar](media/vstu_azure-import-sample-assets-image1.png)

## <a name="add-scenes-to-build-settings"></a>Planda yapı ayarları ekleme

Dosyaları alma tamamladıktan sonra gerekli Sahne dosyaları Unity projenin yapı ayarlarında eklenmesi gerekir.

1. Unity proje penceresinde gidin **Azure kolay tabloları örnek oyun varlıklar/planda** dizin.

2. Unity menüsünden seçin **Dosya > Yapı ayarları...** . Bu derleme Ayarları iletişim kutusu görüntüler.

3. Sürükleme **HeatmapScene**, **LeaderboardScene**, **MenuScene**, ve **RaceScene** Projepenceresinedosyalarından**İçinde perde yapı** derleme Ayarları iletişim kutusu bölümü.

  ![Paketi İçeri Aktar](media/vstu_azure-import-sample-assets-image2.png)

4. Unity menüsünden seçin **Dosya > Proje kaydetme** yapı ayarları kaydedilir emin olmak için.

## <a name="next-step"></a>Sonraki adım

* [Örnek oyunu sınayın](visual-studio-tools-for-unity-azure-game.md)