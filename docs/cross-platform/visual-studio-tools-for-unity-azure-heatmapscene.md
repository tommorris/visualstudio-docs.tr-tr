---
title: "Unity Azure izlenecek HeatmapScene için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: E11DA08B-7341-4743-A817-0CAD59844305
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 472b6d5adae5e23007b9c1aa4d9c75118a94e1cc
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="heatmapscene-explanation"></a>HeatmapScene açıklama

HeatmapScene örneğini içeren **LevelGeometry** prefab. Kilitlenme koordinatları yüklenen Azure'dan bu şekilde harita doğru düzeyi resim.

## <a name="heatmap-script"></a>Heatmap komut dosyası

### <a name="initializecrashlistasync"></a>InitializeCrashListAsync
`InitializeCrashListAsync`Azure üzerinde CrashInfo kolay tablo bağlanır ve kullandığı <a href="https://msdn.microsoft.com/en-us/library/azure/jj554274(v=azure.10).aspx"> `ToListAsync` </a> tüm girdilerini bir listeye eklemek için.

```
private async Task InitializeCrashListAsync()
 {
     Debug.Log("Downloading crash data from Azure...");

     for (int i = 0; i < numberOfAttempts; i++)
     {
         try
         {
             Debug.Log("Connecting... attempt " + (i +1));
             crashesFromServer = await crashesTable.ToListAsync();
             Debug.Log("Done downloading.");
             return;
         }
         catch (System.Exception e)
         {
             Debug.Log("Error connecting: " + e.Message);
         }

         if (i == numberOfAttempts - 1)
             Debug.Log("Connection failed. Check logs, try again later.");
         else
             await Task.Delay(500);
     }
 }
```

### <a name="spawnmarkersfromlist"></a>SpawnMarkersFromList
`SpawnMarkersFromList`Azure'dan alınan kilitlenme listesini dolaşır ve her giriş için bir kilitlenme işaret prefab başlatır.

```csharp
private void SpawnMarkersFromList()
{
    foreach (var item in crashesFromServer)
    {
        GameObject marker = GameObject.Instantiate(markerPrefab);
        marker.transform.position = new Vector3 { x = item.X, y = item.Y, z = item.Z };
    }
}
```

### <a name="deletecrashdataasync"></a>DeleteCrashDataAsync

`DeleteCrashDataAsync`Kullanıcı bastığında adlı **verileri Temizle** düğmesi. Yerel listesini Kilitlenmeler ve çağrıları tekrarlanan <a href="https://msdn.microsoft.com/en-us/library/azure/jj554258(v=azure.10).aspx"> `DeleteAsync` </a> her giriş için. Bu ayarlar her girişin **silinmiş** kolay tablosundaki sütun **doğru**. `ToListAsync`Bu silinen girişleri yok sayar.

```csharp
public async void DeleteCrashDataAsync()
{
    Debug.Log("Deleting crash data...");
    foreach (var item in crashesFromServer)
    {
        try
        {
            await crashesTable.DeleteAsync(item);
        }
        catch (System.Exception e)
        {
            Debug.Log("Error deleting crash data: " + e.Message);
        }
        Debug.Log("Done deleting crash data.");
    }
    SceneManager.LoadScene(SceneManager.GetActiveScene().name);
}
```

## <a name="next-step"></a>Sonraki adım

* [LeaderboardScene açıklaması](visual-studio-tools-for-unity-azure-leaderboardscene.md)