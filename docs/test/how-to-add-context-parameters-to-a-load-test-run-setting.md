---
title: "Bağlam parametreleri bir yük testi çalışma ayarına Visual Studio'da ekleme | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, run settings, context parameters
- load tests, context parameters
ms.assetid: a8a0b97e-8040-4711-85ab-36548b130ed2
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 03db08b701574a4e910b96c843d0f2638e71a4f7
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-add-context-parameters-to-a-load-test-run-setting"></a>Nasıl yapılır: Bir Yük Testi Çalışma Ayarına Bağlam Parametreleri Ekleme

Kullanarak yük testi oluşturduktan sonra **Yeni Yük Testi Sihirbazı**, kullanabileceğiniz **Yük Testi Düzenleyicisi** senaryoları özelliklerini test gereksinimlerini ve hedeflerinizi karşılayacak şekilde değiştirmek için.

> [!NOTE]
> Çalışma ayarları özelliklerini ve açıklamalarının tam listesi için bkz: [yük testi çalıştırma ayarları özellikleri](../test/load-test-run-settings-properties.md).

Yük testi çalışma ayarı Yük Testi Düzenleyicisini kullanarak kullanmak üzere bağlam parametreleri oluşturabilirsiniz. Bağlam parametreleri, bir dize Parametreleştirme olanak tanır.

Zaten bir bağlam parametresi kullanılarak bir parametreli Web sunucusu URL'si kullanan bir Web performans testi yük testlerini içeren varsayalım. Web performans testinde kullanılan hesapla aynı ad değerini kullanan ayarı yük testi için bir bağlam parametresi ekleyebilirsiniz. Yük testi çalıştırdığınızda, bu Web performans testi farklı bir sunucuya eşler. Örneğin, yük test ederseniz WebServer1 URL'sini de Web sunucusu adı için adlı bir bağlam parametresi kullanan bir Web performans testi içerir. Çalışma da WebServer1 adlı ayarı yük testinde bağlam parametresi sonra belirtirseniz, yük testi çalışma ayarı yük testinde atanan bağlam parametresi kullanın. Yük testi Web performans testinde yük testinde bağlam parametresi olarak aynı bağlam parametresi adını kullanıyorsa, açıklamak için bağlam parametresi yük testinde Web performans testinde kullanılan bağlam parametresi geçersiz kılar.

> [!WARNING]
> Bir çalışma ayarına bağlam parametreleri kullandığınızda kasıtsız olarak Web performans testine bağlam parametresi geçersiz dikkat edin. Bu kasıtlı olarak olmadığınız sürece aynı bağlam parametre adlarını kullanmaktan kaçının.

Websunucusu1 bağlam parametresi değerini atamaktır `http://CorporateStagingWebServer`, sonra kullanabileceğiniz `WebServer1` boyunca yük test ve böylelikle kolayca değerini farklı bir Web sunucusuna herhangi bir zamanda değiştirin.

Ayrıca, farklı bir yük testi çalışma ayarlarında aynı adı kullanarak bir bağlam parametresi için farklı değerler atama tarafından yük testi farklı ortamlar kullanarak çalıştırabilirsiniz:

-   Kurumsal hazırlama Web Server çalıştırma ayarı: WebServer1 adlı bağlam parametresi http://CorporateStagingWebServer =

-   Kurumsal üretim Web Server çalıştırma ayarı: WebServer1 adlı bağlam parametresi http://CorporateProductionWebServer =

 **Komut satırından çalıştırma ayarını değiştirme**

 Bağlam parametresi stratejisi yararlanmak için komut satırından farklı çalışma ayarları kullanmak istiyorsanız, aşağıdaki komutları kullanın:

 **Set Test.UseRunSetting= CorporateStagingWebServer**

 - ve -

 **mstest /testcontainer:loadtest1.loadtest**

## <a name="to-add-a-context-parameter-to-a-run-setting"></a>Bir çalışma ayarına bağlam parametresi eklemek için

1.  Bir yük testi açın.

2.  Genişletme **çalıştırma ayarları** Yük Testi Düzenleyicisi yük testi ağacında klasöründe.

3.  Çalışma ayarı özel sağ bağlam parametresi ekleyin ve ardından istediğiniz **bağlam parametresi Ekle**.

     Yeni bir bağlam parametresi eklenen **bağlam parametreleri** klasöründe **çalıştırma ayarları** yük testi ağacı klasöründe.

     veya

     Zaten çalışma ayarı içeriyorsa, bir **bağlam parametreleri** klasörünü sağ tıklatın ve ardından **bağlam parametresi Ekle**.

4.  Özellikler penceresinde değerini değiştirin **adı** (örneğin, websunucusu1) uygun şekilde. Özellikler penceresinde değiştirin **değeri** kullanmak istediğiniz parametre (örneğin, http://CorporateStagingWebServer).

5.  (İsteğe bağlı) 3 ile 5 arasındaki adımları yineleyin ve kullanmak için farklı bir dize **değeri** özelliği (örneğin, http://CorporateProductionWebServer).

6.  Hangi çalışma etkin olmasını istediğiniz ayarları seçin. Çalışma ayarları kısayol menüsünü açın ve seçin **etkin olarak ayarla**.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)