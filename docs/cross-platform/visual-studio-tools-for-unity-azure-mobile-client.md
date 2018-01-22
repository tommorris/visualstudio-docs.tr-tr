---
title: "Unity Azure izlenecek mobil istemci için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5A8762A1-D843-4FD8-A89B-E5E489ECA03D
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: f6b7861b1cf027e4c2f47f711d6f47376dec3a7c
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="implement-the-azure-mobileserviceclient"></a>Azure MobileServiceClient uygulama

Azure Mobile istemci SDK'sı için Orta olan <a href="https://msdn.microsoft.com/en-us/library/azure/microsoft.windowsazure.mobileservices.mobileserviceclient(v=azure.10).aspx">MobileServiceClient</a>, mobil uygulama arka erişmesine izin verir.

## <a name="locate-the-url-of-the-mobile-app-backend"></a>Mobil uygulama arka ucu URL'sini bulun

`MobileServiceClient` Oluşturucusu mobil uygulama URL'sini nedenle önce bir parametre olarak alır ileriye dönük URL'yi bulun.

1. Azure portalında tıklatın **uygulama hizmetleri** düğmesi.

    ![Uygulama Hizmetleri](media/vstu_azure-implement-azure-mobileserviceclient-image1.png)

2. Mobil uygulamanız için girişi tıklatın.

    ![Mobil uygulama'ı tıklatın](media/vstu_azure-implement-azure-mobileserviceclient-image2.png)

3. Mobil uygulama arka URL'sini kopyalayın.

    ![URL'yi kopyalayın](media/vstu_azure-implement-azure-mobileserviceclient-image3.png)

## <a name="create-the-mobileserviceclient-singleton"></a>MobileServiceClient singleton oluşturma

Ayrıca tek bir örneği yalnızca olmalıdır `MobileServiceClient`, bu kılavuzda singleton deseni çeşitlemesi kullanılır.

1. İçinde **varlıklar/betikleri** Unity projenizin dizin oluşturma adlı yeni bir C# betik **AzureMobileServiceClient**.

2. Açık `AzureMobileServiceClient` komut dosyası ve ifadeler ve sınıf bildiriminin kullanımı dahil olmak üzere tüm var olan şablon kodu silin.

3. Aşağıdaki kodu ekleyin:

  ```csharp
  using Microsoft.WindowsAzure.MobileServices;

  public static class AzureMobileServiceClient
  {
      private const bool ignoreTls = true;
      private const string backendUrl = "MOBILE_APP_URL";
      private static MobileServiceClient client;

      public static MobileServiceClient Client
      {
          get
          {
              if (client == null)
              {
                  client = new MobileServiceClient(backendUrl);
              }

              return client;
          }
      }
  }
  ```

  > [!NOTE]
  > Tüm adımları tamamladınız IntelliSense Microsoft.WindowsAzure ad alanı tanımazsa denetleyin [geliştirme ortamını hazırlayın](visual-studio-tools-for-unity-azure-prepare.md) bölümü.

4. Önceki kodla `MOBILE_APP_URL` , mobil uygulamanızın arka ucuna URL'si ile.

## <a name="next-step"></a>Sonraki adım

* [Güncelleştirme Unity Mono güvenlik deposu](visual-studio-tools-for-unity-azure-security.md)
