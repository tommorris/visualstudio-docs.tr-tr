---
title: Sorun raporları için özel veriler
ms.date: 06/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- developer community privacy
- privacy, developer community
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2905cd6fcf9255eb8ba76d636d908651e2254115
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/22/2018
ms.locfileid: "36327082"
---
# <a name="developer-community-data-privacy"></a>Geliştirici topluluğu veri gizliliği

Varsayılan olarak, tüm bilgileri sorun raporları [Geliştirici topluluğu](https://developercommunity.visualstudio.com/), açıklamalar ve yanıtları dahil olmak üzere, herkese görünür. Sorunları, çözümleri ve diğer kullanıcıların bulduğunuz geçici çözümleri görmek tamamını topluluk izin verdiği için faydalıdır. Ancak, veri veya kimlik gizlilik konusuyla ilgilenen, seçeneğiniz vardır.

## <a name="identity-privacy"></a>Kimlik gizliliğini

Kimlik bilgilerinizi açıklama konusunda endişe varsa [yeni bir Microsoft hesabı oluşturmak](https://signup.live.com/) ilgili herhangi bir ayrıntıyı açıklamaz. Raporunuzu oluşturmak için bu hesabı kullanın.

## <a name="data-privacy"></a>Veri gizliliği

Veri gizlilik konusuyla ilgilenen, başlık veya her zaman ortak ilk rapor içeriğinin özel kalmasını istediğiniz herhangi bir şey koymayın. Bunun yerine, raporu oluşturur ve ardından ayrıntılar özel olarak ayrı bir açıklama için göndereceğiz not edin. Sorun raporu oluşturulduktan sonra kimlerin yanıtlar ve ekleri görebileceğini belirtebilirsiniz:

1. Oluşturulan rapora seçin **açıklama eklemek** özel sorun açıklamasını oluşturmak için.

1. Denetim yanıt Düzenleyicisi'nde kullanmak **gönderme** ve **iptal** yanıtınızı kitlesi belirtmek için düğmeler. Seçin **Viewable araburucu ve özgün posteri** görünürlük Microsoft çalışanlarına ve kendiniz için sınırlamak için.

   ![Geliştirici topluluğu gizlilik denetimi](media/developer-community-privacy-control.png)

   Yalnızca belirttiğiniz kişilerin, açıklama ve tüm görüntüleri, bağlantılar veya dahil kodu görebilirsiniz. Açıklama altında yanıtları özgün açıklama olarak aynı görünürlüğe sahiptir. Yanıtları gizlilik denetiminde kısıtlı görünürlük durumu doğru göstermiyor olsa bile bu geçerlidir.

1. Açıklama ve herhangi diğer bilgileri, görüntüler ve dosya ekleri, yeniden oluşturma için gerekli ekleyin. Seçin **gönderme** özel olarak bu bilgileri göndermek için düğme.

   > [!NOTE]
   > Ekli dosyalar üzerinde 2 GB sınırını ve en fazla 10 dosya yok. Daha büyük bir dosyayı karşıya yüklemeyi gerekiyorsa, yeni bir sorun raporu göndermek veya özel bir açıklama Microsoft çalışana ait bir karşıya yükleme URL'si isteyin.

Gizliliğinizi korumak ve hassas bilgileri genel görünümü dışında tutmak için Microsoft ile tüm etkileşimleri yanıtları görünürlük kısıtlanmış bir yorum altında tutmak için dikkatli olun. Diğer açıklamaları yanıtlar hassas bilgilerin yanlışlıkla açığa neden olabilir.

## <a name="data-we-collect"></a>Topladığımız veri

Varsa **bir sorun bildirmek** başlatılan Visual Studio Yükleyicisi'nden en son Kurulum günlüğüne toplarız.

Varsa **bir sorun bildirmek** başlatılan Visual Studio'dan bir veya daha fazla aşağıdaki veri türlerini topladığımız:

- Olay günlüğünden Watson ve .NET girişleri

- Visual Studio bellek içi etkinliği günlük dosyası

- PerfWatson dosyaları, Watson koleksiyonu etkinleştirilirse, gelen *VSFeedbackPerfWatsonData* klasörü

- Varsa, LiveShare günlük dosyaları, gelen *VSFeedbackVSRTCLogs* klasörü

- Varsa, Xamarin günlük dosyaları, gelen *%LOCALAPPDATA%\Xamarin\Logs*

- Varsa, Nuget günlük dosyaları, gelen *%TEMP%\NuGetScratch\nuget-dg\nugetSpec.dg*

- Varsa web hata ayıklayıcı günlük dosyaları:

   - *%Temp%\vscode-Chrome-Debug.txt*

   - *%Temp%\vscode-node-debug2.txt*

   - *%Temp%\vscode-Edge-Debug.txt*

- Bir ekran dahil seçerseniz,

- İçeren bir kayıt eklemek isterseniz verileri, kaydı:

   - Sorunu yeniden oluşturma adımları

   - ETL izleme dosyası

   - Döküm dosyası

   > [!NOTE]
   > Raporu göndermeden önce göndermek istemiyorsanız veri kaydını silebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio ile ilgili bir sorun bildirme](how-to-report-a-problem-with-visual-studio-2017.md)
- [C++ sorun raporu veri gizliliği](/cpp/how-to-report-a-problem-with-the-visual-cpp-toolset#reports-and-privacy)