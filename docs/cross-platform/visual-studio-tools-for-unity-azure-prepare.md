---
title: "Azure Yönergeyi Hazırla Unity için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: B921C2AC-B5D6-4B24-918E-511F83D57275
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- azure
- unity
ms.openlocfilehash: 7554380435c77750eb48a5ce261cc0a2b3885ccd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="prepare-the-development-environment"></a>Geliştirme ortamını hazırlayın

Azure Mobile istemci SDK'sı Unity kullanmanın bazı önkoşulları vardır.

## <a name="download-and-install-unity-2017"></a>Unity 2017 yükleyip

Unity 2017.1 veya üstü gereklidir. Tüm Unity planlar boş kişisel planı dahil olmak üzere Kılavuzu ile çalışır. Unity https://store.unity.com/ indirin.

## <a name="download-and-install-visual-studio-2017"></a>Visual Studio 2017 yükleyip

Visual Studio 2017 15.3 Kılavuzu gerektirir ve üstü, Unity iş yükü ile oyun geliştirme ile. İzlenecek ücretsiz Community sürümü de dahil olmak üzere, Visual Studio 2017'in tüm sürümlerinde çalışır.

1. Visual Studio 2017 https://www.visualstudio.com/ adresindeki indirin.

2. Visual Studio 2017 yükleyin ve emin **oyun Unity ile geliştirme** iş yükü etkindir.

 ![Unity iş yükünü seçme](media/vstu_azure-prepare-dev-environment-image0.png)

 > [!NOTE]
 > Visual Studio 2017 zaten yüklediyseniz, görüntüleyin ve iş yükleri Visual Studio yükleyicisi çalıştırarak değiştirin.

## <a name="create-a-new-3d-unity-project"></a>Yeni bir 3B Unity projesi oluşturma

Unity başlatın ve yeni bir 3B projesi oluşturun.

![Yeni Unity projesi oluşturma](media/vstu_azure-prepare-dev-environment-image1.png)

## <a name="set-the-script-editor-to-visual-studio-preview-2017"></a>Visual Studio Önizleme 2017 komut dosyası Düzenleyicisi'ni ayarlayın

Zaten sahip olduğunuz Visual Studio 2017 Unity'nın dış betik düzenleyicisi olarak ayarlanmış, ancak 15.3 Önizleme sürümü olmak önemlidir mümkündür seçilir.

1. Unity gelen **Düzenle** menüsünde seçin **Düzenle > Tercihler...** .

  ![Tercihler menüsünü açın](media/vstu_azure-prepare-dev-environment-image1.2.png)

2. Unity Tercihler penceresi açıldığında, seçin **Harici Araçlar** sol tarafındaki sekmesinde.

3. İçinde **dış komut dosyası Düzenleyicisi** açılır menüsünde, select **Visual Studio 2017**.

  ![Ayarla dış komut dosyası Düzenleyicisi](media/vstu_azure-prepare-dev-environment-image3.png)

## <a name="change-the-unity-scripting-runtime-to-net-46"></a>Unity komut dosyası çalışma zamanı için .NET 4.6 değiştirme
İzlenecek yol .NET 4.6 Azure mobil istemci SDK'sını ve bağımlılıklarını kullanımı gerektirir.

1. Unity gelen **dosya** menüsünde seçin **Dosya > Yapı ayarları...** .

  ![Derleme Ayarları'nı açın](media/vstu_azure-prepare-dev-environment-image4.png)

2. Tıklatın **Player Ayarları...**  düğmesi.

  ![Player Ayarları'nı açın](media/vstu_azure-prepare-dev-environment-image5.png)

3. Player ayarları Unity Inspector penceresinde açar. Altında **yapılandırma** başlığını tıklatın **Scripting çalışma zamanı sürümü** açılır ve seçin **Experimental (.NET 4.6 eşdeğer)**. Bu Unity yeniden başlatmak için onay isteyen bir iletişim kutusu ister. Seçin **yeniden**.

  ![.NET 4.6 seçin](media/vstu_azure-prepare-dev-environment-image6.png)

## <a name="add-a-reference-to-systemnethttpdll"></a>System.Net.Http.dll bir başvuru ekleyin

Unity .NET 4.6 eşdeğer komut dosyası çalışma zamanı tarafından Azure mobil istemci SDK'sını gerekli System.Net.Http paket kullanılmasına izin verir. DLL dosyasını kullanmak için bir başvuru eklenmelidir ancak Unity içinde dahil edilir.

1. Unity Düzenleyicisi proje penceresinde **sağ tıklatın** **varlıklar** klasörü ve select **Gezgini'nde Göster**.

  ![Varlıklar klasörü Gezgini'nde Göster](media/vstu_azure-prepare-dev-environment-image7.png)

2. Açılır Gezgini penceresinde, çift tıklayarak **varlıklar** açmak için dizin.

3. Varlıklar dizin içinde **sağ tıklatın** seçip **yeni > metin belgesi**.

4. Yeni metin belgesi bir metin düzenleyicisinde açın ve satırı ekleyin:`-r:System.Net.Http.dll`

5. Belgeyi kaydedin ve kapatın.

4. Yeni metin belgesi yeniden adlandırma "**mcs.rsp**" ve .txt dosya uzantısı sildiğinizden emin olun.

  * Gizli dosya uzantılarını varsa, bunları göstermek için klasör görünümü seçeneklerinizin değiştirmeniz gerekir.
  * Başlat menüsü ve türü "Klasör Seçenekleri" açmak aramak için. Seçin "**dosya Gezgini seçenekleri**".
  * Seçin **Görünüm** sekmesinde ve Gelişmiş ayarlarda olun "**Gizle bilinen dosya türleri için uzantıları**" olarak işaretli değildir.

    ![Varlıklar klasörü Gezgini'nde Göster](media/vstu_azure-prepare-dev-environment-image8.png)

Bu adımları tamamladıktan sonra adlı bir dosya olmalıdır **mcs.rsp** satırıyla `r:System.Net.Http.dll` Unity projenizin kök **varlıklar** dizin.

>[!NOTE]
> Başvuru işlevselliği, Unity 3.3 için ve üstü, Visual Studio 15.3 + Unity yükündeki dahil Visual Studio Araçları gerektirir. Bu adım bir işe yaramazsa, yüklü VSTU doğru sürümüne sahip olduğunuzdan emin olun.

## <a name="add-the-newtonsoftjson-nuget-package-to-your-project"></a>Newtonsoft.Json NuGet paketini projenize ekleyin

Azure Mobile istemci SDK'sı Newtonsoft.Json paketi gerektirir. Ne yazık ki, Unity NuGet desteklemez. Unity Unity projesini Visual Studio'da açın ve NuGet ile bir pakete eklerseniz, Unity Düzenleyicisi'nde projeye bir sonraki açışınızda silecek. Ancak, NuGet paketleri el ile Unity projeye eklenebilir.

1. Unity projenizin varlıklar dizini olarak adlandırılan yeni bir klasör oluşturun "**NuGet paketlerini**". Yalnızca kuruluş budur.

2. Tıklayın ve https://www.nuget.org/packages/Newtonsoft.Json/ gidin **el ile karşıdan yükleme** düğmesi. .Nupkg dosyasını indirin.

  ![Varlıklar klasörü Gezgini'nde Göster](media/vstu_azure-prepare-dev-environment-image9.png)

3. Yeni yüklenen dosyasını bulun ve dosya uzantısı için .nupkg çıkarılıp **.zip**. Bu, görüntülemek ve başka bir zip dosyası gibi dahil dosyalarını ayıklamak izin vermelidir.

4. Açın veya ZIP dizine ayıklayın ve **\lib\net45**.

5. Kopya **Newtonsoft.Json.dll** Unity projenizin dosyasına **Assets\NuGet paketleri** dizin.

## <a name="add-the-azure-mobile-client-sdk-nuget-package-to-your-project"></a>Azure Mobile istemci SDK NuGet paketini projenize ekleyin

Azure Mobile istemci SDK'sı kolayca okuma ve yazma Azure kolay tablolara işlevleri içerir.

1. Tıklayın ve https://www.nuget.org/packages/Microsoft.Azure.Mobile.Client/ gidin **el ile karşıdan yükleme** düğmesi. .Nupkg dosyasını indirin.

2. Yeni yüklenen dosyasını bulun ve dosya uzantısı için .nupkg çıkarılıp **.zip**. Bu, görüntülemek ve başka bir zip dosyası gibi dahil dosyalarını ayıklamak izin vermelidir.

3. Açın veya ZIP dizine ayıklayın ve **\lib\net45**.

4. Kopya **Microsoft.Azure.Mobile.Client.dll** Unity projenizin dosyasına **Assets\NuGet paketleri** dizin.

>[!WARNING]
> Bu adımları tamamladıktan sonra yeniden başlattığınızdan emin Unity ve Visual Studio veya InteliSense yeni eklenen paketler anlamayabilir.

## <a name="conclusion"></a>Sonuç

Bu adımları tamamladıktan sonra Unity projenizi Azure mobil istemci SDK'ın Kurulum olmalıdır. Geliştirme ortamınızı Unity projenizde yeni C# kod oluşturma, Visual Studio'da açma ve aşağıdakileri yazarak sınayabilirsiniz en üstünde using deyimleri:
```
using System.Net.Http;
using Newtonsoft.Json;
using Microsoft.WindowsAzure.MobileServices;
```

InteliSense bu using deyimleri algılarsa, kurulumun düzgün bir şekilde tamamlandı. Herhangi bir hata veya InteliSense bu paketleri tanımıyor Unity ve Visual Studio'yu yeniden başlatmayı deneyin. Hala çalışmıyorsa, yukarıdaki adımları yeniden ziyaret.

## <a name="next-step"></a>Sonraki adım

* [Veri modeli sınıfları oluşturma](visual-studio-tools-for-unity-azure-data.md)
