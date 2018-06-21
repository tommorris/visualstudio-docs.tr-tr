---
title: Codeındex komutu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- command-line tools [Team Foundation Server]
- TFSConfig
- CodeIndex command [Team Foundation Server]
ms.assetid: b79568d4-6a64-4ca9-a1ee-3e57f92a9c5c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2216a4678436a9d7811adbdb4bef2ee930fbabb2
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36296300"
---
# <a name="codeindex-command"></a>Codeındex komutu

Kullanım **Codeındex** Team Foundation Server'ı dizin kodu yönetmek için komutu. Örneğin, CodeLens bilgi düzeltin veya sunucu performans sorunları araştırmak için dizin oluşturma devre dışı açmak için dizin sıfırlamak isteyebilirsiniz.

## <a name="required-permissions"></a>Gerekli izinler

Kullanılacak **Codeındex** komutu, bir üyesi olmanız gerekir **Team Foundation Yöneticileri** güvenlik grubu. Bkz: [izinleri ve gruplar Team Services ve TFS için tanımlı](/vsts/organizations/security/permissions?view=vsts).

> [!NOTE]
> Yönetici kimlik bilgileriyle oturum olsa bile, bu komutu çalıştırmak için yükseltilmiş bir komut istemi penceresi açmanız gerekir. Ayrıca Team Foundation için uygulama katmanı'ndan bu komutu da çalıştırmanız gerekir.

## <a name="syntax"></a>Sözdizimi

```cmd
TFSConfig CodeIndex /indexingStatus | /setIndexing:[ on | off | keepupOnly ] | /ignoreList:[ add | remove | removeAll | view ] ServerPath | /listLargeFiles [/fileCount:FileCount] [/minSize:MinSize] | /reindexAll | /destroyCodeIndex [/noPrompt] | /temporaryDataSizeLimit:[ view | <SizeInGBs> | disable ] | /indexHistoryPeriod:[ view | all | <NumberOfMonths> ] [/collectionName:CollectionName | /collectionId:CollectionId]
```

### <a name="parameters"></a>Parametreler

|**Bağımsız değişken**|**Açıklama**|
|------------------|---------------------|
|`CollectionName`|Takım projesi koleksiyonu adını belirtir. Adı boşluk içeriyorsa adı tırnak işaretleri, örneğin, "Fabrikam Web Site" alın.|
|`CollectionId`|Takım projesi koleksiyonu kimlik numarasını belirtir.|
|`ServerPath`|Bir kod dosyası yolunu belirtir.|

|**Seçeneği**|**Açıklama**|
|----------------|---------------------|
|**/indexingStatus**|Kod dizin oluşturma hizmeti yapılandırmasını ve durumunu gösterir.|
|**/setIndexing:**[üzerinde &#124; kapalı &#124; keepupOnly]|-   **üzerinde**: tüm değişiklik kümelerini Dizinlemeyi Başlat.<br />-   **devre dışı**: tüm değişiklik kümelerini dizin oluşturmayı durdur.<br />-   **keepupOnly**: önceden oluşturulmuş değişiklik dizin oluşturmayı durdur ve yalnızca yeni değişiklik dizin oluşturma işlemi başlatın.|
|**/ignoreList:**[eklemek &#124; kaldırmak &#124; removeAll &#124; Görünüm] `ServerPath`<br /><br /> Başlangıç, son veya her iki ucuna sunucusu yolun joker karakter (*) kullanabilirsiniz.|Kod dosyaları ve dizinli istemediğiniz yollarına listesini belirtir.<br /><br /> -   **ekleme**: istemediğiniz dosya dizine yoksayılan dosya listesine ekleyin.<br />-   **kaldırma**: yoksayılan dosya listesinden dizinli istediğiniz dosyayı kaldırın.<br />-   **removeAll**: yoksayılan dosya listesi temizleyin ve tüm dosyaların dizinini başlatın.<br />-   **Görünüm**: dizinli değil dosyalarına bakın.|
|**/listLargeFiles [/ fileCount:** `FileCount` **/minSize:** `MinSize`]|KB cinsinden belirtilen boyutu aşan dosyaları belirtilen sayısını gösterir. Daha sonra **/ignoreList** dizine almasını bu dosyaları dışarıda bırak seçeneği.|
|**/reindexAll**|Daha önce oluşturulmuş verilerini temizlemek ve dizin yeniden başlatın.|
|**/destroyCodeIndex [/noPrompt]**|Kod dizini silin ve tüm dizinlenmiş veri kaldırın. Kullanırsanız onayı gerektirmeyen **/noPrompt** seçeneği.|
|**/temporaryDataSizeLimit**: [Görünüm &#124; <`SizeInGBs`> &#124; devre dışı]|Değişiklik kümeleri işlerken CodeLens oluşturur ne kadar geçici veri denetimi. Varsayılan sınırı 2 GB'dir.<br /><br /> -   **Görünüm**: Geçerli boyut sınırını gösterir.<br />-   `SizeInGBs`: Boyut sınırını değiştirin.<br />-   **devre dışı**: boyut sınırını kaldırın.<br /><br /> Yeni bir değişiklik kümesi CodeLens işlemeden önce bu sınırı denetlenir. Geçici verileri bu sınırı aşarsa, CodeLens değil yenilerini değişiklik işleme duraklatılır. CodeLens veri temizlenir ve bu sınırın altına düştüğünde sonra işleme yeniden başlar. Temizleme günde bir kez otomatik olarak çalıştırır. Başka bir deyişle, geçici verileri çalışan temizleme başlatana kadar bu sınırı aşabilir.|
|**/indexHistoryPeriod**: [Görünüm &#124; tüm &#124; <`NumberOfMonths`>]|Denetim değişiklik geçmişinizi dizin ne kadar süre. Başka bir etkiler, ne kadar geçmiş CodeLens size gösterir. Varsayılan sınır 12 ay ' dir. Bu, yalnızca son 12 ay değişiklik geçmişinizden CodeLens gösterir anlamına gelir.<br /><br /> -   **Görünüm**: geçerli ay sayısını gösterir.<br />-   **tüm**: tüm değişiklik geçmişi dizin.<br />-   `NumberOfMonths`: Dizin değişiklik geçmişi için kullanılan ay sayısını değiştirin.|
|**/CollectionName:** `CollectionName`|Takım projesi koleksiyonu çalıştırılacağı adını belirtir **Codeındex** komutu. Kullanmayın, gerekli **/CollectionId**.|
|**/collectionId:** `CollectionId`|Takım projesi koleksiyonu çalıştırmak için kimlik numarasını belirtir **Codeındex** komutu. Kullanmayın, gerekli **/CollectionName**.|

## <a name="examples"></a>Örnekler

> [!NOTE]
> Burada adı geçen örnek şirketler, kuruluşlar, ürünler, etki alanı adları, e-posta adresleri, logolar, kişiler, yerler ve olaylar hayal ürünüdür.  Gerçek şirket, kuruluş, ürün, etki alanı adı, e-posta adresi, logo, kişi, yerler veya olayları ile ilişki amaçlanmamıştır veya çıkarılmamalıdır.

 Dizin oluşturma durumu ve yapılandırma kodu görmek için:

```cmd
TFSConfig CodeIndex /indexingStatus /collectionName:"Fabrikam Web Site"
```

 Tüm değişiklik kümelerini dizin oluşturma işlemi başlatmak için:

```cmd
TFSConfig CodeIndex /setIndexing:on /collectionName:"Fabrikam Web Site"
```

 Önceden oluşturulmuş değişiklik dizin oluşturmayı durdur ve yalnızca yeni değişiklik dizin oluşturma işlemi başlatmak için:

```cmd
TFSConfig CodeIndex /setIndexing:keepupOnly /collectionName:"Fabrikam Web Site"
```

 10 KB'den büyük olan en fazla 50 dosyaları bulmak için:

```cmd
TFSConfig CodeIndex /listLargeFiles /fileCount:50 /minSize:10 /collectionName:"Fabrikam Web Site"
```

 Belirli bir dosya dizine almasını hariç tutmak ve yoksayılan dosya listesine eklemek için:

```cmd
TFSConfig CodeIndex /ignoreList:add "$/Fabrikam Web Site/Catalog.cs" /collectionName:"Fabrikam Web Site"
```

 Dizinli değil tüm dosyaları görmek için:

```cmd
TFSConfig CodeIndex /ignoreList:view
```

 Daha önce oluşturulmuş verilerini temizlemek ve dizin yeniden başlatmak için:

```cmd
TFSConfig CodeIndex /reindexAll /collectionName:"Fabrikam Web Site"
```

 Tüm değişiklik geçmişini kaydetmek için:

```cmd
TFSConfig CodeIndex /indexHistoryPeriod:all /collectionName:"Fabrikam Web Site"
```

 CodeLens geçici veri boyutu sınırı kaldırın ve geçici veri boyutundan bağımsız olarak dizin oluşturmaya devam etmek için:

```cmd
TFSConfig CodeIndex /temporaryDataSizeLimit:disable /collectionName:"Fabrikam Web Site"
```

 Onay kodu diziniyle silmek için:

```cmd
TFSConfig CodeIndex /destroyCodeIndex /collectionName:"Fabrikam Web Site"
```

## <a name="see-also"></a>Ayrıca bkz.

- [CodeLens ile kod değişikliklerini ve diğer geçmişi bulma](../ide/find-code-changes-and-other-history-with-codelens.md)
- [Sunucu yapılandırmasını TFSConfig ile yönetme](/tfs/server/ref/command-line/tfsconfig-cmd)