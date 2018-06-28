---
title: Hızlı Başlangıç - kopya deposu Python kodu
description: Bu hızlı başlangıç Visual Studio Takım Gezgini kullanarak Python koans depoyu kopyalama tarafından Visual Studio'da Python projesi oluşturun.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: e183833222f64a24a2d523e32f624ed24c54bc58
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056714"
---
# <a name="quickstart-clone-a-repository-of-python-code-in-visual-studio"></a>Hızlı Başlangıç: Visual Studio'da Python kodu bir depoyu kopyalayın

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installing-python-support-in-visual-studio.md), Visual Studio için GitHub uzantısını ekleyebilirsiniz. Uzantı, kolayca Python kodu bir depoyu kopyalayın ve bir proje ondan IDE içinde oluşturabilirsiniz olanak tanır. Her zaman de komut satırında depoları kopyalayın ve bunlarla Visual Studio içindeki çalışma.

[!INCLUDE[install-github-extension](includes/install-github-extension.md)]

1. Visual Studio'yu başlatın.

1. Seçin **Görünüm > Takım Gezgini** açmak için **Takım Gezgini** , GitHub veya Visual Studio Team Services bağlanmak veya için bir depoyu kopyalayın penceresi. (Görmüyorsanız **Bağlan** gösterilen sayfasında Aşağıda, bu sayfasına gidersiniz üst araç çubuğundaki Tak simgesini seçin.)

    ![Takım Gezgini penceresi gösteren Visual Studio Team Services, GitHub ve depo kopyalama](media/team-explorer.png)

1. Altında **yerel Git depoları**seçin **kopya** komutu sonra girin `https://github.com/gregmalcolm/python_koans` URL alanına kopyalanan dosyalar için bir klasör girin ve seçin **kopya** düğme.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalarını almak için tam bir klasördür. Farklı `git clone` komutunu Takım Gezgini'nde kopyasını oluşturma otomatik olarak oluşturmaz alt depo adını.

1. Kopyalama tamamlandıktan sonra depo adını görünür **yerel Git depoları** listesi. Depo panosunda gitmek için bu adına çift tıklayın **Takım Gezgini**.

1. Altında **çözümleri**seçin **yeni**.

    ![Takım Gezgini penceresi, bir kopya yeni proje oluşturma](media/team-explorer-new-project.png)

1. İçinde **yeni proje** görünür, iletişim gidin "Den varolan Python kodu" Python dili (veya "Python" Search'te) seçin, proje için bir ad belirtin, Ayarla **konumu** aynı klasöre Depo ve select **Tamam**. Görüntülenen Sihirbazı'nda seçin **son**.

1. Seçin **Görünüm > Çözüm Gezgini** menüsünde.

1. İçinde **Çözüm Gezgini**, genişletin `python3` düğümünü sağ tıklatın `contemplate_koans.py`seçip **başlangıç dosyası olarak ayarlayın**. Bu adım Visual Studio Proje çalıştırırken kullanması gereken hangi dosya söyler.

1. Seçin **Proje > Koans özellikleri** menüsünden seçin **genel** sekmesini tıklatın ve ayarlama **çalışma dizini** "python3" için. Varsayılan olarak Visual Studio çalışma dizini başlangıç dosyasının konumu yerine Proje kök ayarladığından, bu adım gereklidir (`python3\contemplate_koans.py`, proje özelliklerinde de görebileceğiniz). Program kodu için bir dosya arar `koans.txt` çalışma klasöründe, bu nedenle bu değeri değiştirmeden gördüğünüz bir çalışma zamanı hatası.

    ![Python proje için çalışma dizini ayarlama](media/projects-set-working-directory.png)

1. CTRL + F5 tuşuna basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. Görürseniz bir `FileNotFoundError` için `koans.txt`, önceki adımda açıklandığı gibi ayarlar çalışma dizinini kontrol edin.

1. Program başarıyla çalıştırıldığında satırında 17 onaylama hata görüntüler `python3/koans/about_asserts.py`. Bu kasıtlıdır: program öğretmek sorununuz tarafından Python kasıtlı tüm hataları düzeltmek için tasarlanmıştır. (Daha fazla ayrıntı üzerinde bulunan [Ruby Koans](http://rubykoans.com/), Python Koans neden olacak.)

    ![İlk Python koans program çıktısı](media/koans-output.png)

1. Açık `python3/koans/about_asserts.py` Çözüm Gezgini'nde bulunduğu yere giderek ve dosyayı çift. Satır numaraları Düzenleyicisi'nde varsayılan olarak görünmez dikkat edin. Bunu değiştirmek için seçin **Araçlar > Seçenekler**seçin **tüm ayarları göster** iletişim kutusunun alt kısmındaki penceresine gidin **metin düzenleyicisi > Python > Genel** ve seçin **Satır numaraları**:

    ![Satır numarası Python dosyaları açma](media/options-general-line-numbers.png)

1. Değiştirerek hatayı düzeltin `False` satırına 17 bağımsız `True`. Satırı aşağıdaki gibi şöyle olmalıdır:

    ```python
    self.assertTrue(True) # This should be True
    ```

1. Programı yeniden çalıştırın. Visual Studio, hataları hakkında sizi uyarır, yanıt **Evet** kodu çalıştırmaya devam etmek için. Daha sonra ilk onay geçirir ve sonraki koan üzerinde programı durdurur bakın. Hataları ve program düzeltme devam etmek istediğiniz gibi yeniden.

> [!Important]
> Bu Hızlı Başlangıç, doğrudan bir kopyasını oluşturduğunuz *python_koans* github'daki. Bu tür bir depo yazarı doğrudan değişikliklere karşı korunur, böylece değişiklikleri depoya kaydedilmeye çalışılırken başarısız olur. Uygulamada, geliştiriciler bunun yerine, kendi GitHub hesabı için bir tür bir depoyu çatallaştırmanız, var. değişiklikleri yapın ve ardından bu değişiklikleri özgün deponuza göndermek için çekme isteği oluşturun. Kendi çatalı varsa, daha önce kullanılan özgün depo URL'si yerine URL'sini kullanın.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Ayrıca bkz.

- [El ile varolan bir Python yorumlayıcısı tanımlayan](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installing-python-support-in-visual-studio.md).
- [Konumları yüklemek](installing-python-support-in-visual-studio.md#install-locations).
