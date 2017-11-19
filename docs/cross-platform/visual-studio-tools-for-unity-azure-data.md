---
title: "Unity Azure izlenecek veri modeli için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6FCCA8D1-0D06-4B2A-A55F-FC3D1FEA0F56
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: e3b6064a3947f57ffcbe6422162c6c72fca0ab21
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="create-data-model-classes"></a>Veri modeli sınıfları oluşturma

Unity projesi Azure mobil uygulama arka ucunda oluşturulan tablolarla karşılık gelen veri modeli sınıfları içermelidir.

## <a name="create-the-crashinfo-class"></a>CrashInfo sınıfı oluşturma

1. Unity içinde yeni bir kök klasörde eklemek **varlıklar** adlı dizin **betikleri**. Yeni komut dosyaları klasörü içinde adlı başka bir yeni bir klasör oluşturun **veri modelleri**. Yalnızca kuruluş budur.

2. Yeni veri modelleri klasör içinde adlı yeni bir C# betik oluşturma **CrashInfo**.

3. Yeni `CrashInfo` komut dosyası, deyimlerini kullanarak ve sınıf bildirimi dahil olmak üzere tüm şablonu kodunu silme ve aşağıdakileri ekleyin:

  ```csharp
  public class CrashInfo
  {
      public string Id { get; set; }
      public float X { get; set; }
      public float Y { get; set; }
      public float Z { get; set; }
  }
  ```

  > [!WARNING]
  > İzlenecek düzgün çalışması veri modeli sınıfının adını kolay Azure mobil uygulaması arka uçta oluşturulan tablosunun adı eşleşmelidir.

## <a name="create-the-highscoreinfo-class"></a>HighScoreInfo sınıfı oluşturma

1. Veri modelleri klasörü içinde adlı yeni bir C# betik oluşturma **HighScoreInfo**.

2. Yeni `HighScoreInfo` komut dosyası, deyimlerini kullanarak ve sınıf bildirimi dahil olmak üzere tüm şablonu kodunu silme ve aşağıdakileri ekleyin:

  ```csharp
  public class HighScoreInfo
  {
      public string Name { get; set; }
      public float Time { get; set; }
      public string Id { get; set; }
  }
  ```

  ## <a name="next-step"></a>Sonraki adım

  * [Azure MobileServiceClient uygulama](visual-studio-tools-for-unity-azure-mobile-client.md)
