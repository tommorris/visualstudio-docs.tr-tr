---
title: "Unity Azure izlenecek bağlantı için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 516A8FB2-8DFF-4BAB-8116-FDCD1C228DB3
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: cb2ce447f21231b98d6464824ba7d088fee16cce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="test-the-client-connection"></a>İstemci bağlantısını sınama

AzureMobileServiceClient singleton oluşturulduğunda, istemci bağlantısı test zamanı geldi.

## <a name="create-the-testclientconnection-script"></a>TestClientConnection komut dosyası oluşturma

1. İçinde **betikleri** Unity, klasörde adlı yeni bir C# betik oluşturma **TestClientConnection**.

2. Komut dosyasını Visual Studio'da açın, herhangi bir şablon kodu silin ve aşağıdakileri ekleyin:

  ```csharp
  using System.Collections.Generic;
  using UnityEngine;
  using System.Threading.Tasks;
  using System;
  using System.Linq;
  using Microsoft.WindowsAzure.MobileServices;

  public class TestClientConnection : MonoBehaviour
  {
      void Start()
      {
          Task.Run(TestTableConnection);
      }

      private async Task TestTableConnection()
      {
          var table = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

          Debug.Log("Testing ToListAsync...");
          await TestToListAsync(table);

          Debug.Log("Testing InsertAsync...");
          await TestInsertAsync(table);

          Debug.Log("Testing DeleteAsync...");
          await TestDeleteAsync(table);

          Debug.Log("All testing complete.");
      }

      private async Task TestInsertAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await TestToListAsync(table);
              var initialCount = allEntries.Count();

              await table.InsertAsync(new CrashInfo { X = 1, Y = 2, Z = 3 });

              allEntries = await TestToListAsync(table);
              var newCount = allEntries.Count();

              Debug.Assert(newCount == initialCount + 1, "InsertAsync failed!");
          }
          catch (Exception)
          {
              throw;
          }
      }

      private async Task<List<CrashInfo>> TestToListAsync(IMobileServiceTable<CrashInfo> table)
      {
          try
          {
              var allEntries = await table.ToListAsync();
              Debug.Assert(allEntries != null, "ToListAsync failed!");
              return allEntries;
          }
          catch (Exception)
          {

              throw;
          }
      }

      private async Task TestDeleteAsync(IMobileServiceTable<CrashInfo> table)
      {
          var allEntries = await TestToListAsync(table);

          foreach (var item in allEntries)
          {
              try
              {
                  await table.DeleteAsync(item);
              }
              catch (Exception)
              {
                  throw;
              }
          }

          allEntries = await TestToListAsync(table);

          Debug.Assert(allEntries.Count() == 0, "DeleteAsync failed!");
      }
  }
  ```

3. Unity içinde **GameObject** menüsünde, select **GameObject > boş oluştur** boş GameObject Unity görünüm oluşturmak için. Yeniden adlandırmak **TestClientConnection**.

4. **Sürükleme** Unity TestClientConnection betikten **proje** TestClientConnection GameObject penceresinden **hiyerarşi** penceresi.

5. Unity menüde seçin **Dosya > Sahne olarak Kaydet...** . Sahne adı **istemci bağlantı testi** tıklatıp **kaydetmek**.

5. Tıklatın **Yürüt** düğmesi Unity ve konsol penceresine uyun. Onaylar hiçbiri başarısız olduğunu onaylayın.

6. Azure portalındaki CrashInfo kolay tabloyu açın. Şimdi olan bir giriş olmalıdır **X, Y, Z** , koordinatları **(1, 2, 3)** ve değerini **true** için de **silinmiş** sütun. Testi her zaman aynı değerlere ancak benzersiz bir kimliği ile yeni bir giriş tabloya eklenmesi gerekir.

  ![Kolay tablo girişi](media/vstu_azure-test-client-connection-image1.png)

## <a name="next-step"></a>Sonraki adım
* [Örnek oyun varlıklar alma](visual-studio-tools-for-unity-azure-game-assets.md).
