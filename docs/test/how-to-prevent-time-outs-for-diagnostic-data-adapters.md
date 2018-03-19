---
title: "Visual Studio tanılama veri bağdaştırıcıları için zaman aşımlarını | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Diagnostic Data Adapter, increasing time-outs
ms.assetid: 39fff4fc-9233-4f67-96ac-e81bbaf7ca82
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 50bdf23e83ca9ef70c40b010050a3e6aba90e0a5
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-prevent-time-outs-for-diagnostic-data-adapters"></a>Nasıl yapılır: Tanılama Veri Bağdaştırıcıları için Zaman Aşımını Önleme

Test ayarlarınızda tanılama veri bağdaştırıcıları kullanıyorsanız, aşağıdaki nedenlerden biri nedeniyle, testi başlattığınızda bir zaman aşımı oluşabilir:

-   Test denetleyicisi hizmeti test denetleyicisi bilgisayarda çalışmıyor. Hizmeti yeniden başlatmanız gerekebilir. Belirlemek için test denetleyicisi ve test denetleyicilerini yönetme hakkında daha fazla bilgi için bkz: [yönetme Test denetleyicilerini ve Test aracıları Visual Studio ile](../test/manage-test-controllers-and-test-agents.md).

-   Bir uzak bilgisayarda veri topluyorsanız, Güvenlik Duvarı'nı Microsoft Test Yöneticisi'ni engelleyebilir. Microsoft Test Yöneticisi'ni çalıştıran bilgisayar test denetleyicisinden gelen bağlantıları kabul etmeniz gerekir. Bir zaman aşımı, güvenlik duvarı tarafından engellendiği için Microsoft Test Yöneticisi'ni bir ileti denetleyicisinden almaz oluşur. Microsoft Test Yöneticisi'ni çalıştıran bilgisayar üzerindeki güvenlik duvarı ayarlarınızı denetleyin gerekir. Aşağıdaki güvenlik duvarı ayarları hakkında daha fazla bilgi için bkz: [Microsoft Web sitesini](http://go.microsoft.com/fwlink/?LinkId=184980).

-   Test denetleyicisi Microsoft Test Yöneticisi'ni çalıştıran bilgisayar adını çözümleyemiyor. DNS yanlış adresi bu bilgisayar için sağlarsa, bu durum oluşabilir. Bu sorunu gidermek için ağ yöneticinize başvurun gerekebilir.

 Çok miktarda veri toplamanız gerekir uzun bir testi çalıştırdığınızda, bu verilerin toplanması zaman aşımına olduğunu fark edebilirsiniz. Bu sorunu çözmek için aşağıdaki yordamı kullanabilirsiniz.

 Yapılandırma dosyası Microsoft Test Yöneticisi'ni veya yapılandırma dosyası için zaman aşımına uğrama test aracısı için güncelleştirerek zaman aşımı süresini artırabilir.

 Microsoft Test Yöneticisi için yapılandırma dosyası adlı **mtm.exe.config**. Şu dizinde bulunur: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

 Bir test aracısını güncelleştirmek için aşağıdaki yapılandırma dosyalarını test aracısı bilgisayarda güncelleştirmeniz gerekir. Bu tüm dosyalar aynı dizinde test aracısı bilgisayarda bulunur: *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE*.

-   QTAgent.exe.config

-   QTAgent32.exe.config

-   QTDCAgent.exe.config

-   QTDCAgent32.exe.config

 El ile testleri çalıştırma ve bir hata oluşturulduğunda veya test çalışması tamamlandı bir ortamdan verilerini toplamak, tanılama veri bağdaştırıcıları tarafından toplanan herhangi bir veri el ile testler çalıştıran bilgisayara aktarılır. Çok miktarda veri toplayan veya yavaş ağ bağlantısı varsa, 60 saniye varsayılan değerinden daha uzun sürebilir. Örneğin, IntelliTrace olaylarını toplamak ve birçok işlem için bilgi çağırmak için IntelliTrace bağdaştırıcısı yapılandırdıysanız, bu veri aktarımını varsayılan zaman aşımı aşabilir. Bu değeri artırmak için aşağıdaki yordamı güncelleştirmek için kullanabileceğiniz **mtm.exe.config**.

 Test Çalıştırıcısı etkinlik zaman aşımına uğrarsa ya da bir test aracısı zaman aşımı olursa bir hata iletisi görüntülenir. Test aracısı için hata iletisini hangi test aracısı bilgisayarı zaman aşımına uğradı bilgiler içerir. Aldığınız hata iletisi bağlı olarak yapılandırma dosyalarını güncelleştirmek için aşağıdaki yordamı kullanın.

## <a name="to-increase-the-time-outs-for-your-diagnostic-data-adapters"></a>Tanılama veri bağdaştırıcıları zaman aşımlarını artırmak için

1.  Bir Windows Explorer (veya dosya Gezgini) penceresini açın.

     Bunu yapmak için sağ **Başlat** üzerine gelin ve **Araştır**.

    > [!NOTE]
    > Dosyayı güncelleştirmek için yönetici ayrıcalıkları gerektirebilir.

2.  Bilgisayarınızda dizini bulun *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE* güncelleştirmesi gereken bir dosya içerir.

3.  Dosyaya sağ tıklayın ve fareyle **birlikte Aç**. Bir düzenleyici seçin.

     Dosya Düzenleyicisi'nde görüntülenir. Bu dosyada saklanan birçok ayar vardır. Bu ayarların çoğu Microsoft Test Yöneticisini kullanarak değiştirilebilir. Ancak, zaman aşımı ayarları aşağıdaki adımlarda açıklandığı şekilde el ile değiştirilmelidir.

4.  Zaman aşımı değerlerini artırmak için test yürütme ayarları bölümünü değiştirmeniz gerekir. Bu bölümde aşağıdaki biçime sahiptir:

    ```
    <!-- Begin: Test execution settings -->

        <!-- How long test runner will wait for an event raised to all local data collectors to complete.  Default is 300. -->
        <add key="DataCollectorEventTimeoutInSeconds" value="300"/>

        <!-- How long test runner will wait for test run operations, such as starting or stopping a test run, to complete.  Default is 60. -->
        <add key="RunOperationTimeoutInSeconds" value="60"/>

        <!-- End: Test execution settings -->
    ```

5.  Tanılama veri bağdaştırıcıları olaylar tamamlanması için bekleme süresini artırmak için anahtar değeri artırın **DataCollectorEventTimeoutInSeconds**

6.  Test Çalıştırıcısı etkinlik için zaman aşımı hata iletisi ise, anahtar değeri artırmanız gerekir **RunOperationTimeoutInSeconds**.

7.  Tüm veri aktarırken bir hata için veya bir test testleri çalıştıran bilgisayara sona erdiğinde toplanan zaman aşımı süresini artırmak için aşağıdaki zaman aşımını eklemek **mtm.exe.config** dosyasının appSettings bölümünde:

    ```
    <!-- How long test runner waits for data collected by diagnostic data adapters to be transferred to the computer. Default is 60 seconds. -->
    <add key="GetCollectorDataTimeout" value="300"/>
    ```

    > [!NOTE]
    > Zaman aşımı değeri saniye cinsindendir.

8.  Dosyaya yaptığınız değişiklikleri kaydedin ve daha önce zaman aşımına uğradı testleri yeniden çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)