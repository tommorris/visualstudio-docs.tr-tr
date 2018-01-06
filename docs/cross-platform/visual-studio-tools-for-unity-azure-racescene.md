---
title: "Unity Azure izlenecek RaceScene için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1F9304E8-0F1B-4325-8BED-FE3EB0ADCE8D
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 7dc57628774624975cc6ede5bd241f322472bfe6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="racescene-explanation"></a>RaceScene açıklama

Unity RaceScene kullanan [standart varlıklar](https://www.assetstore.unity3d.com/en/#!/content/32351) düzeyi ve temel yarış oyunlar oluşturmak için. Bu bölümde, ilgili GameObjects ve betikleri RaceScene Hierarcy içinde listelenen sırayla aşağıdaki ekran görüntüsünde gösterildiği açıklanacaktır.

![RaceScene](media/vstu_azure-racescene-explanation-image1.png)

## <a name="multipurposecamerarig"></a>MultipurposeCameraRig

**MultipurposeCameraRig** arasındadır **kameralar** standart varlıklar paket. Inspector özelliklerini uygun bir hızda araba izlemek için düzenlediniz.

## <a name="levelgeometry"></a>LevelGeometry

LevelGeometry prefab kuruluş için kullanılan bir boş GameObject ' dir. Kendi alt GameObjects oynanabilir alanı oluşturun. Değer tabanlarını, duvarları, rampalar ve engellerini tüm prefabs içinde oluşturulmuş **prototipi oluşturulurken** standart varlıklar paket.

**Önemli bir Not** Azure'da kaydedilir çökme sınanacak bir nesne için sırayla bu içermelidir **duvar** etiket uygulanır.

![RaceScene](media/vstu_azure-racescene-explanation-image2.png)

## <a name="car"></a>Araba

**Araba** prefab olan **Taşıtlardan** standart varlıklar paket. Tek değişiklik olan **RecordCrashInfo** komut dosyası bileşeni eklenir.

### <a name="recordcrashinfo"></a>RecordCrashInfo

Bu komut dosyası kilitlenmelere denetler `OnCollisionEnter` ve bunları bir listeye kaydeder. `crashRecordingCooldown`ve `crashRecordingMinVelocity` ne oyun çökmeyle ilgili bir veri kümesi tutmak için göz önünde bulundurur sınırlayın.

Zaman `RaceFinished` olayı, `UploadNewCrashDataAsync` her kilitlenme Azure CrashInfo kolay tabloda listede gönderir.

```Csharp
using System.Collections;
using System.Collections.Generic;
using System.Threading.Tasks;
using UnityEngine;

public class RecordCrashInfo : MonoBehaviour
{
    [Tooltip("Time in seconds after a crash before a new crash can be recorded.")]
    [SerializeField]
    private float crashRecordingCooldown = 1;

    [Tooltip("How fast car must be traveling before crash can be recorded.")]
    [SerializeField]
    private float crashRecordingMinVelocity = 8;

    [SerializeField]
    private Rigidbody carRigidbody;

    [SerializeField]
    private GameObject crashMarkerPrefab;

    [Tooltip("If turned on, crash markers spawn when the player crashes.")]
    [SerializeField]
    private bool spawnDebugMarkers = false;

    private bool isOnCooldown = false;
    private bool meetsMinVelocity = false;
    private bool isRaceFinished = false;

    private List<CrashInfo> newCrashes = new List<CrashInfo>();

    private void LateUpdate()
    {
        // We have to update this in LateUpdate as opposed to checking in OnCollisionEnter.
        // The car's velocity has already decreased from crashing by the time
        // OnCollisionEnter gets called.

        meetsMinVelocity = carRigidbody.velocity.magnitude >= crashRecordingMinVelocity;
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (!isRaceFinished && collision.gameObject.tag == "Wall" && !isOnCooldown && meetsMinVelocity)
        {
            Debug.Log("Collided with wall!");

            newCrashes.Add(new CrashInfo
            {
                X = collision.transform.position.x,
                Y = collision.transform.position.y,
                Z = collision.transform.position.z
            });

            if (spawnDebugMarkers && Debug.isDebugBuild)
                Instantiate(crashMarkerPrefab, collision.transform.position, Quaternion.identity);

            isOnCooldown = true;
            StartCoroutine(Cooldown());
        }  
    }

    private IEnumerator Cooldown()
    {
        yield return new WaitForSeconds(crashRecordingCooldown);

        isOnCooldown = false;
    }

    private void OnRaceFinished()
    {
        Task.Run(UploadNewCrashDataAsync);
    }

    private async Task UploadNewCrashDataAsync()
    {
        var crashTable = AzureMobileServiceClient.Client.GetTable<CrashInfo>();

        try
        {
            Debug.Log("Uploading crash data to Azure...");

            foreach (var item in newCrashes)
            {
                await crashTable.InsertAsync(item);
            }
            Debug.Log("Finished uploading crash data.");
        }
        catch (System.Exception e)
        {
            Debug.Log("Error uploading crash data: " + e.Message);
        }

    }

    private void OnEnable()
    {
        Checkpoint.RaceFinished += OnRaceFinished;
    }

    private void OnDisable()
    {
        Checkpoint.RaceFinished -= OnRaceFinished;
    }

}
```

## <a name="checkpoints"></a>checkpoints

İle dört GameObjects düzeyine sahip **denetim noktası** komut dosyası bileşeni. Kontrol noktalarını player izleme aşağı yanlış şekilde seyahat tarafından yarış tamamlayamıyor emin olun. Bunlar, ayrıca player yarış tamamlandığında algıla. Bu yerdir `RaceFinished` olay çağrılır.

## <a name="invisible-collision"></a>Görünmez çakışma

Devre dışı MeshRenderer bileşenleri standart ilkel küpleriyle görünmez çakışma player inbounds tutmak için kullanılır. Ayrıca, **Bouncy** fizik malzeme görünmez duvarları kapalı Uçan araba Sıçrama satisfying şekilde emin olmak için ve görünmez duvar basarsa, onu kaydırma ve üstünde görünür giriş player önlemek için uygulanır Duvar.

## <a name="recordhighscore"></a>RecordHighScore

Bu betik, player yeni bir yüksek puan kazanılan olmadığını görmek için denetler. Varsa, görüntüler `enterNamePopup`, kendi ad girip tıklatın player sağlayan **gönderme**.

Yürütücü adı gönderildikten sonra `UploadNewHighScoreAsync` olarak adlandırılır ve yeni yüksek puan Azure HighScoreInfo kolay tabloda gönderilir.

```csharp
using System.Collections;
using System.Collections.Generic;
using Microsoft.WindowsAzure.MobileServices;
using UnityEngine;
using System.Threading.Tasks;
using System;
using System.Linq;
using UnityEngine.UI;

public class RecordHighScore : MonoBehaviour
{
    [SerializeField]
    private InputField nameInputField;

    [SerializeField]
    private CanvasGroup enterNamePopup;

    private List<HighScoreInfo> highScores;
    private string playerName = string.Empty;

    private async void Start()
    {
        ShowEnterNamePopup(false);
        highScores = await Leaderboard.GetTopHighScoresAsync();
    }

    private void ShowEnterNamePopup(bool shouldShow)
    {
        enterNamePopup.alpha = shouldShow ? 1 : 0;
        enterNamePopup.interactable = shouldShow;
    }

    public void SubmitButtonClicked()
    {
        playerName = nameInputField.text;
    }

    private async void OnAfterMostRecentScoreSet(float newScore)
    {
        bool isNewHighScore = CheckForNewHighScore(newScore);

        if (isNewHighScore)
        {
            Debug.Log("New High Score!");
            await GetPlayerNameAsync();
            await UploadNewHighScoreAsync(newScore);
        }
        else
        {
            Debug.Log("No new high score.");
        }
    }

    private async Task GetPlayerNameAsync()
    {
        // Wait a bit before showing the popup.
        // This just helps the player experience feel
        // less jarring.
        await Task.Delay(2000);
        ShowEnterNamePopup(true);

        // Wait until the player enters a name and clicks submit.
        // OnSubmitButtonClicked will set the playerName.
        while (playerName == string.Empty)
        {
            await Task.Delay(100);
        }

        ShowEnterNamePopup(false);
    }

    private bool CheckForNewHighScore(float newScore)
    {
        Debug.Log("Checking for a new high score...");

        bool isHighScoreListFull = highScores.Count >= Leaderboard.SizeOfHighScoreList;
        var lowerScores = highScores.Where(x => x.Time > newScore);

        return lowerScores.Count() > 0 || !isHighScoreListFull;
    }

    private async Task UploadNewHighScoreAsync(float newScore)
    {
        var newHighScoreInfo = new HighScoreInfo { Name = playerName, Time = newScore };

        try
        {
            Debug.Log("Uploading high score data to Azure...");

            await Leaderboard.HighScoreTable.InsertAsync(newHighScoreInfo);

            Debug.Log("Finished uploading high score data.");
        }
        catch (System.Exception e)
        {
            Debug.Log("Error uploading high score data: " + e.Message);
        }
    }

    private void OnEnable()
    {
        LapTimer.AfterMostRecentScoreSet += OnAfterMostRecentScoreSet;
    }

    private void OnDisable()
    {
        LapTimer.AfterMostRecentScoreSet -= OnAfterMostRecentScoreSet;
    }

}
```

## <a name="next-step"></a>Sonraki adım

* [HeatmapScene açıklama](visual-studio-tools-for-unity-azure-heatmapscene.md).
