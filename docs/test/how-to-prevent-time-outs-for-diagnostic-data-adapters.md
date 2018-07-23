---
title: Visual Studio'da tanılama veri bağdaştırıcıların zaman aşımı
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, increasing time-outs
ms.assetid: 39fff4fc-9233-4f67-96ac-e81bbaf7ca82
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: fca48c45af5ec93519e1688ec54677c233d2fe17
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178325"
---
# <a name="how-to-prevent-time-outs-for-diagnostic-data-adapters"></a>Nasıl yapılır: Tanılama Veri Bağdaştırıcıları için Zaman Aşımını Önleme

Test ayarlarınızda tanı veri bağdaştırıcıları kullanıyorsanız, aşağıdaki nedenlerden biri nedeniyle test çalıştırmanızın başlattığınızda bir zaman aşımı oluşabilir:

-   Test denetleyicisi hizmeti test denetleyicisi bilgisayarında çalışmıyor. Hizmeti yeniden başlatmanız gerekebilir. Test denetleyicinizin belirlenmesi ve test denetleyicilerini yönetme hakkında daha fazla bilgi için bkz. [Test denetleyicilerini yönetme ve Test aracıları Visual Studio ile](../test/manage-test-controllers-and-test-agents.md).

-   Uzak bir bilgisayarda veri topluyorsanız, güvenlik duvarı Microsoft Test Yöneticisi'ni engelleyebilir. Microsoft Test Yöneticisi'ni çalıştıran bilgisayar test denetleyicisinden gelen bağlantıları kabul etmeniz gerekir. Güvenlik Duvarı tarafından engellendiği için Microsoft Test Yöneticisi'ni bir ileti denetleyicisinden almadığında zaman aşımı oluşur. Microsoft Test Yöneticisi'ni çalıştıran bilgisayarda güvenlik duvarı ayarlarınızı işaretlemeniz gerekir.

-   Test denetleyicisi, Microsoft Test Yöneticisi'ni çalıştıran bilgisayar adı çözümlenemiyor. DNS bu bilgisayar için yanlış adres sağlıyorsa bu durum oluşabilir. Bu sorunu gidermek için ağ yöneticisine başvurmanız gerekebilir.

Bir çok sayıda veri toplaması gereken uzun bir test çalıştırdığınızda, bu verilerin toplanması zaman aşımına olduğunu fark edebilirsiniz. Bu sorunu çözmek için aşağıdaki yordamı kullanabilirsiniz.

Yapılandırma dosyası için Microsoft Test Yöneticisi ya da yapılandırma dosyasını zaman aşımına uğrayan test aracısı için güncelleştirerek zaman aşımını artırabilirsiniz.

Microsoft Test Yöneticisi için yapılandırma dosyası olarak adlandırılır **mtm.exe.config**. Şu dizinde bulunur: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

Bir test aracısını güncelleştirmek için aşağıdaki yapılandırma dosyalarını test aracısı bilgisayarında güncelleştirmeniz gerekir. Tüm bu dosyalar aynı dizindeki test aracısı bilgisayarında bulunur: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

-   QTAgent.exe.config

-   QTAgent32.exe.config

-   QTDCAgent.exe.config

-   QTDCAgent32.exe.config

El ile testleri çalıştırın ve bir hata oluşturulduğunda veya test durumu tamamlandığında bir ortamdan verilerini toplamak, tanılama veri bağdaştırıcıları tarafından toplanan tüm veriler el ile testler çalıştıran bilgisayara aktarılır. Çok fazla veri topladıysanız veya yavaş bir ağ bağlantınız varsa varsayılan değer olan 60 saniyeden uzun sürebilir. Örneğin, IntelliTrace bağdaştırıcısını IntelliTrace olaylarını toplamak ve birçok işlem için bilgi çağırmak için yapılandırdıysanız, bu verinin aktarım süresi varsayılan zaman aşımı aşabilir. Bu değeri arttırmak için aşağıdaki yordamı güncelleştirmek için kullanabilirsiniz **mtm.exe.config**.

Test Çalıştırıcısı faaliyeti ya da bir test aracısı zaman aşımına uğrarsa bir hata iletisi görüntülenir. Test aracısı için hata iletisi hangi test aracısı bilgisayarın zaman aşımına bilgileri içerir. Aldığınız hata iletisi bağlı olarak yapılandırma dosyalarını güncelleştirmek için aşağıdaki yordamı kullanın.

## <a name="to-increase-the-time-outs-for-your-diagnostic-data-adapters"></a>Tanılama verilerini bağdaştırıcılarınız için zaman aşımlarını arttırmak için

1.  Bir Windows Explorer (veya dosya Gezgini) penceresi açın.

     Bunu yapmak için sağ **Başlat** gelin ve **Araştır**.

    > [!NOTE]
    > Dosyayı güncelleştirmek için yönetici ayrıcalıkları gerektirebilir.

2.  Bilgisayarınızda bir dizin bulun *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* , güncelleştirmeniz gereken dosyayı içeren.

3.  Dosyaya sağ tıklayın ve fareyle **birlikte Aç**. Bir düzenleyici seçin.

     Dosya, düzenleyicide görüntülenir. Bu dosyada depolanan bir çok ayar vardır. Bu ayarların çoğu, Microsoft Test Yöneticisi'ni kullanarak değiştirilebilir. Ancak, zaman aşımı ayarları aşağıdaki adımlarda açıklandığı şekilde el ile değiştirilmelidir.

4.  Zaman aşımı değerlerini artırmak için test yürütme ayarları bölümünü değiştirmeniz gerekir. Bu bölümde, aşağıdaki biçime sahiptir:

    ```text
    <!-- Begin: Test execution settings -->

        <!-- How long test runner will wait for an event raised to all local data collectors to complete.  Default is 300. -->
        <add key="DataCollectorEventTimeoutInSeconds" value="300"/>

        <!-- How long test runner will wait for test run operations, such as starting or stopping a test run, to complete.  Default is 60. -->
        <add key="RunOperationTimeoutInSeconds" value="60"/>

        <!-- End: Test execution settings -->
    ```

5.  Tanılama veri bağdaştırıcıları tamamlanması olayların tamamlanmasını bekleme süresini artırmak için anahtar değeri artırmak **DataCollectorEventTimeoutInSeconds**

6.  Zaman aşımı hatası iletisi Test Çalıştırıcısı etkinliği içinse anahtarının değerini arttırmalısınız **RunOperationTimeoutInSeconds**.

7.  Bir hata için veya testleri çalıştıran bilgisayara bir test bittiğinde toplanan herhangi bir veri aktarımı için zaman aşımını artırmak için aşağıdaki zamanaşımını eklemeniz **mtm.exe.config** dosyasının appSettings bölümünde:

    ```text
    <!-- How long test runner waits for data collected by diagnostic data adapters to be transferred to the computer. Default is 60 seconds. -->
    <add key="GetCollectorDataTimeout" value="300"/>
    ```

    > [!NOTE]
    > Zaman aşımı değeri saniyelerle ifade edilir.

8.  Dosyaya yaptığınız değişiklikleri kaydedin ve daha önce zaman aşımına uğramış testleri yeniden çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)