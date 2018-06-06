---
title: Visual Studio'da Test ayarlarını kullanarak testler sırasında ekran ve ses kayıtlarını dahil
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, recording desktop video
ms.assetid: 2cefe8c2-430a-4cb4-bbe0-f3edb2e5bc03
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 44994b7b643d63f548092aba9a878b939f3968af
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751000"
---
# <a name="how-to-include-recordings-of-the-screen-and-voice-during-tests-using-test-settings"></a>Nasıl yapılır: Test Ayarlarını Kullanarak Testler Sırasında Ekran ve Ses Kayıtlarını Dahil Etme

Yapılandırma Düzenleyicisi'nden Visual Studio'da, ekran ve ses test çalıştıran kullanıcının kayıtları tanılama veri bağdaştırıcısı yapılandırabilirsiniz. Bu tanılama veri bağdaştırıcısı test sırasında masaüstü oturumunun ekran ve ses kaydını kaydeder. Kayıt test sonucu ile kaydedilmez veya hataya eklenebilir. Diğer ekip üyelerinin kaydı yeniden oluşturması zor olan uygulama hatalarını yalıtmak için kullanabilirsiniz.

> [!WARNING]
> Ekran ve ses kayıtlarını birden çok monitör yapılandırmalarını desteklemez.

Ekran ve Ses Kaydedicisi el ile veya otomatikleştirilmiş testler ile kullanılabilir. Örneğin, kodlanmış UI testi uzaktan çalıştırırsanız çalışan kodlanmış UI testi görmek için Masaüstü kaydetmek isteyebilirsiniz. Bir ekran ve ses uzaktan kaydı yakalama hakkında daha fazla bilgi için bkz: [nasıl yapılır: ayarlama yukarı bilgisayarınızı Test Aracısı ile etkileşime Testleri Çalıştır masaüstü ile](../test/how-to-set-up-your-test-agent-to-run-tests-that-interact-with-the-desktop.md).

## <a name="to-configure-screen-and-voice-recording-for-your-test-settings"></a>Ekran ve ses için test ayarlarınızı kaydı yapılandırmak için

1.  Ekran ve ses kaydetmek için yapılandırmak istediğiniz test ayarlarını açın. Daha fazla bilgi için bkz: [(VSTS) test ederken Tanılama verileri toplama](/vsts/manual-test/collect-diagnostic-data) veya [toplamak tanılama bilgileri Test ayarlarını kullanarak](../test/collect-diagnostic-information-using-test-settings.md).

2.  Test ayarlarını seçin **rol** ekran ve ses kaydetmek için kullanılacak.

    > [!NOTE]
    > El ile ve otomatikleştirilmiş testler için bu testleri çalıştırır makine olacaktır.

3.  Seçin **ekran ve Ses Kaydedicisi** ve ardından **yapılandırma**.

     Yapılandırma tanılama veri bağdaştırıcısı – ekran ve Ses Kaydedicisi iletişim kutusu görüntülenir.

     ![Video yapılandırması](../test/media/testsettingvideoconfiggdr.png)

4.  (İsteğe bağlı) Seçin **ses kaydetmeye etkinleştirmek** kaydınızı ses içeriği yakalamak için.

5.  (İsteğe bağlı) Onay kutusunu işaretleyin **test çalışması geçerse kaydı Kaydet** her ikisi için ekran ve ses kayıtlarını kaydetme başarısız oldu ve testleri geçirilen belirtmek için.

    > [!WARNING]
    > Seçerseniz **test çalışması geçerse kaydı Kaydet**, kaydı sunucuda depolama alanı kullanan test sonuçları ile depolanır. Bu ekleri temizlemek için Test ek temizleyici aracını kullanabilirsiniz.

6.  Altında **ekran kalitesini**, aşağıdaki açılan liste seçenekleri yapılandırın:

    1.  **Kare hızı:** ekran ve ses kaydetmeye kullanmak istediğiniz saniyede kaç çerçeve belirtin. Saniye başına 4 çerçeveleri varsayılan değerdir. 2 ile 20 arasındaki değerleri belirtilebilir.

    2.  **Bit hızı:** kaç kilobayt sayısı ekran ve ses kaydetmeye kullanmak üzere ikinci belirtin. Varsayılan değer 512'dır. Değer 512 ile 10.000 arasında bir değer belirtilebilir.

    3.  **Quality(1-100):** ekran ve ses 1 ile 100 arasında bir aralık seçerek kaydı kalitesini belirtebilirsiniz. Varsayılan değer 50 (Orta düzey)'dir.

7.  Seçin **Tamam**. Tanılama izleme toplayıcı ayarları şimdi yapılandırılmış ve test ayarlarınız için kaydedilir.

    > [!TIP]
    > Bu tanılama veri bağdaştırıcısı için yapılandırmayı sıfırlamayı tercih **varsayılan yapılandırmaya sıfırlanır** Visual Studio için ve **Varsayılana Sıfırla** Microsoft Test Yöneticisi için.

## <a name="see-also"></a>Ayrıca bkz.

- [(VSTS) test ederken tanılama verisi toplama](/vsts/manual-test/collect-diagnostic-data)
- [El ile testlerde (VSTS) tanılama verisi toplama](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Test ayarlarını kullanarak tanılama bilgileri Topla](../test/collect-diagnostic-information-using-test-settings.md)
- [(VSTS) el ile testleri çalıştırma](/vsts/manual-test/getting-started/run-manual-tests)