---
title: Canlı ASP.NET Azure uygulamaları - Visual Studio hata ayıklama | Microsoft Docs
ms.description: Learn how to set snappoints and view snapshots with the Snapshot Debugger
ms.custom: mvc
ms.date: 03/16/2018
ms.technology:
- vs-ide-debug
ms.topic: tutorial
helpviewer_keywords:
- debugger
ms.assetid: adb22512-4d4d-40e5-9564-1af421b7087e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- azure
ms.openlocfilehash: 3d6173c62b359508819db26ff9dcdceb90644202
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="debug-live-aspnet-azure-apps-using-the-snapshot-debugger"></a>Anlık görüntü hata ayıklayıcı kullanarak canlı ASP.NET Azure uygulamalarının hatalarını ayıklama

İlgilendiğiniz kod yürüttüğünde anlık görüntü hata ayıklayıcı üretim uygulamalarınızın bir anlık görüntüsünü alır. Bir anlık görüntüyü almaya hata ayıklayıcı istemek üzere kodunuzda snappoints ve logpoints ayarlayın. Hata ayıklayıcı tam olarak ne üretim uygulamanızın trafiğini etkilemeden sorun oluştu görmenizi sağlar. Anlık görüntü hata ayıklayıcı üretim ortamlarında ortaya çıkan sorunları çözmek için gereken süreyi önemli ölçüde azaltmaya yardımcı olabilir.

Snappoints ve logpoints için kesme noktaları benzer, ancak kesme noktaları farklı olarak, uygulama snappoints durdurmak yok zaman ulaştı. Genellikle, bir snappoint adresindeki anlık yansımasını yakalamada 10-20 milisaniye alır. 

Anlık görüntü koleksiyonu, Azure App Service içinde çalışan aşağıdaki web uygulamaları için kullanılabilir:

- .NET Framework 4.6.1 çalışan ASP.NET uygulamalarını veya sonraki bir sürümü.
- .NET Core 2.0 veya daha sonra Windows üzerinde çalışan ASP.NET Core uygulamaları.

Ayrıca, anlık görüntü hata ayıklayıcı yalnızca Visual Studio 2017 Enterprise sürümü 15,5 veya üzerini ve temel ya da daha yüksek uygulama hizmeti planları için kullanılabilir. 

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Anlık görüntü hata ayıklayıcı Başlat
> * Bir snappoint ayarlama ve anlık görüntü görüntüleme
> * Bir logpoint ayarlayın

## <a name="start-the-snapshot-debugger"></a>Anlık görüntü hata ayıklayıcı Başlat

1. Yükleme [Visual Studio 2017 Enterprise sürümü 15,5](https://www.visualstudio.com/downloads/) veya sonraki bir sürümü. Bir önceki Visual Studio 2017 yüklemesinden güncelleştiriyorsanız, Visual Studio yükleyicisi çalıştırın ve ASP.NET ve web geliştirme iş yükü anlık görüntü hata ayıklayıcı bileşeni denetleyin.

2. Anlık görüntü debug istediğiniz projeyi açın. 

    > [!IMPORTANT] 
    > Anlık görüntü hata ayıklama için açmanız gerekir. **kaynak kodu aynı sürümünü** Azure uygulama hizmetiniz yayımlanır. 

3. Cloud Explorer'da (**Görünüm > Cloud Explorer**), Azure uygulama hizmeti projenizi dağıtıldığı sağ tıklatın ve seçin **Attach anlık görüntü hata ayıklayıcı**.

   ![Anlık görüntü hata ayıklayıcıyı başlatma](../debugger/media/snapshot-launch.png)

    Seçtiğiniz ilk kez **Attach anlık görüntü hata ayıklayıcı**, Azure App Service üzerinde anlık görüntü hata ayıklayıcı site uzantısı yüklemeniz istenir. Bu yükleme, Azure App Service yeniden başlatılmasını gerektirir. 

   Visual Studio hata ayıklama modu anlık sunulmuştur.

    > [!NOTE]
    > Application Insights site uzantısı, anlık görüntü hata ayıklama de destekler. Bir "uzantısı güncel site" hata iletisiyle karşılaşırsanız bkz [sorun giderme ipuçları ve anlık görüntü hata ayıklama için bilinen sorunlar](../debugger/debug-live-azure-apps-troubleshooting.md) ayrıntıları yükseltme.

   ![Anlık görüntü hata ayıklama modu](../debugger/media/snapshot-message.png)

   **Modülleri** penceresi gösterir, tüm modülleri Azure App Service için ne zaman yüklemiş (seçin **hata ayıklama / Windows / modülleri** bu penceresini açmak için).

   ![Modüller penceresini denetleyin](../debugger/media/snapshot-modules.png)

## <a name="set-a-snappoint"></a>Bir snappoint ayarlayın

1. Kod Düzenleyicisi'nde bir snappoint ayarlamak ilgilendiğiniz kod satırı yanındaki sol cilt payı'ı tıklatın. Yürütecek bildiğiniz kod olduğundan emin olun.

   ![Bir snappoint ayarlayın](../debugger/media/snapshot-set-snappoint.png)

2. Tıklatın **toplamaya** üzerinde snappoint açmak için.  

   ![Üzerinde snappoint Aç](../debugger/media/snapshot-start-collection.png)

    > [!TIP]
    > Bir anlık görüntü görüntülerken adım olamaz, ancak yürütme kodunun farklı satırlarındaki izlemek için kodunuzda birden çok snappoints yerleştirebilirsiniz. Kodunuzda birden çok snappoints varsa, anlık görüntü hata ayıklayıcı karşılık gelen anlık görüntüler aynı son kullanıcı oturumundan olmasını sağlar. Çok sayıda kullanıcı uygulamanızı basarsa olsa bile anlık görüntü hata ayıklayıcı bunu yapar.

## <a name="take-a-snapshot"></a>Bir anlık görüntü alın

Bir snappoint açıldığında snappoint yerleştirildiği kod satırı yürütür her bir anlık görüntü yakalar. Bu yürütme sunucunuzda gerçek bir istek neden olabilir. İsabet, web sitenizi tarayıcı görünümüne gidin ve tüm eylemleri, snappoint zorlamak için snappoint isabet neden gerekli.

## <a name="inspect-snapshot-data"></a>Anlık görüntü verilerini inceleyin.

1. Snappoint gelindiğinde, bir anlık görüntü tanılama araçları penceresinde görünür. Bu pencereyi açmak için **hata ayıklama / Windows / Tanılama Araçları Göster**.

   ![Bir snappoint açın](../debugger/media/snapshot-diagsession-window.png)

1. Anlık görüntü Kod düzenleyicisinde açmak için snappoint çift tıklayın.

   ![Anlık görüntü verilerini inceleyin.](../debugger/media/snapshot-inspect-data.png)

   Bu görünümden DataTips görüntülemek için kullanmak değişkenlerinden gelebilirsiniz **Yereller**, **saatlerde**, ve **çağrı yığını** windows ve ayrıca ifadeleri değerlendirin.

    Web hala etkin olduğunu ve son kullanıcılar etkilenen değil. Varsayılan olarak yalnızca bir anlık görüntü snappoint yakalanır: bir anlık görüntü yakalandıktan sonra snappoint devre dışı bırakır. Snappoint konumundaki başka bir anlık görüntü yakalamak istiyorsanız, snappoint tıklayarak etkinleştirebilirsiniz **güncelleştirme koleksiyon**.

Ayrıca, uygulamanızın daha fazla snappoints ekleyebilir ve birlikte Aç **güncelleştirme koleksiyonu** düğmesi.

**Yardım gerekiyor mu?** Bkz: [sorun giderme ve bilinen sorunlar](../debugger/debug-live-azure-apps-troubleshooting.md) ve [anlık görüntü hata ayıklama hakkında SSS](../debugger/debug-live-azure-apps-faq.md) sayfaları.

## <a name="set-a-conditional-snappoint"></a>Koşullu snappoint ayarlayın

Uygulamanızı belirli bir durumda yeniden zordur, koşullu snappoint kullanımını yardımcı olup olmadığını değerlendirin. Koşullu snappoints Yardım uygulama gibi bir değişken incelemek istediğiniz belirli bir değere sahip olduğunda istenen bir duruma girdiği kadar anlık kaçının. İsabet sayıları ya da ifadeler, filtreleri kullanarak koşulları ayarlayın.

#### <a name="to-create-a-conditional-snappoint"></a>Koşullu snappoint oluşturmak için

1. Snappoint simgesini (boş Top) sağ tıklatın ve seçin **ayarları**.

   ![Ayarlarını seçin](../debugger/media/snapshot-snappoint-settings.png)

1. Snappoint Ayarları penceresinde, bir ifade yazın.

   ![Bir ifade yazın](../debugger/media/snapshot-snappoint-conditions.png)

   Önceki çizimde, anlık görüntü için snappoint yalnızca geçen zaman `visitor.FirstName == "Dan"`.

## <a name="set-a-logpoint"></a>Bir logpoint ayarlayın

Bir snappoint gelindiğinde bir anlık görüntü alma ek olarak, bir ileti oturum snappoint de yapılandırabilirsiniz (diğer bir deyişle, bir logpoint oluşturma). Uygulamanızı yeniden dağıtmak zorunda kalmadan logpoints ayarlayabilirsiniz. Logpoints neredeyse yürütülür ve herhangi bir etkisi veya yan etkileri çalışan uygulamanıza neden olabilir.

#### <a name="to-create-a-logpoint"></a>Bir logpoint oluşturmak için

1. Snappoint simgesini (mavi Altıgene) sağ tıklatın ve seçin **ayarları**.

1. Snappoint Ayarları penceresinde, seçin **Eylemler**.

    ![Bir logpoint oluşturma](../debugger/media/snapshot-logpoint.png)

1. İleti alanında günlüğe kaydetmek istediğiniz yeni günlük iletisi girebilirsiniz. Değişkenleri, bir günlük iletisinde süslü ayraçlar içinde yerleştirerek de değerlendirebilirsiniz.

    Seçerseniz **çıkış penceresine göndermek için**, logpoint gelindiğinde ileti tanılama araçları penceresinde görüntülenir.

    ![Diagsession penceredeki Logpoint verileri](../debugger/media/snapshot-logpoint-output.png)

    Seçerseniz **uygulama günlüğüne Gönder**, logpoint gelindiğinde gelen iletileri görebilirsiniz ileti herhangi bir yerde görüntülenir `System.Diagnostics.Trace` (veya `ILogger` .NET Core içinde), gibi [App Insights](/azure/application-insights/app-insights-asp-net-trace-logs).

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, anlık görüntü hata ayıklayıcı kullanmayı öğrendiniz. Bu özellik hakkında daha fazla ayrıntı okumak isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Anlık görüntü hatalarını ayıklama hakkında SSS](../debugger/debug-live-azure-apps-faq.md)
