---
title: Hızlı Başlangıç - Python kodu bir depo kopyalama
description: Bu hızlı başlangıç Visual Studio Takım Gezgini kullanarak Python koans depoyu kopyalama tarafından Visual Studio'da Python projesi oluşturun.
ms.custom: mvc
ms.date: 03/21/2018
ms.technology:
- devlang-python
dev_langs:
- python
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 80b840e14332498e86f7136f19ea6b7b106812b6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="quickstart-clone-a-repository-of-python-code-in-visual-studio"></a>Hızlı Başlangıç: Visual Studio'da Python kodu bir depoyu kopyalayın

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installing-python-support-in-visual-studio.md), kolayca depoyu Python kodu kopyalayın ve bir proje oluşturun.

[!INCLUDE[install-github-extension](includes/install-github-extension.md)]

2. Visual Studio'yu başlatın.

3. Seçin **Görünüm > Takım Gezgini...**  açmak için **Takım Gezgini** , GitHub veya Visual Studio Team Services bağlanmak veya için bir depoyu kopyalayın penceresi. (Görmüyorsanız **Bağlan** gösterilen sayfasında Aşağıda, bu sayfasına gidersiniz üst araç çubuğundaki Tak simgesini seçin.)

    ![Takım Gezgini penceresi gösteren Visual Studio Team Services, GitHub ve depo kopyalama](media/team-explorer.png)

4. Altında **yerel Git depoları**seçin **kopya** komutu sonra girin `https://github.com/gregmalcolm/python_koans` URL alanına kopyalanan dosyalar için bir klasör girin ve seçin **kopya** düğme.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalarını almak için tam bir klasördür. Farklı `git clone` komutunu Takım Gezgini'nde kopyasını oluşturma otomatik olarak oluşturmaz alt depo adını.

5. Kopyalama tamamlandıktan sonra depo adını görünür **yerel Git depoları** listesi. Depo panosunda gitmek için bu adına çift tıklayın **Takım Gezgini**.

6. Altında **çözümleri**seçin **yeni...** .

    ![Takım Gezgini penceresi, bir kopya yeni proje oluşturma](media/team-explorer-new-project.png)

7. İçinde **yeni proje** görünür, iletişim gidin "Den varolan Python kodu" Python dili (veya "Python" Search'te) seçin, proje için bir ad belirtin, Ayarla **konumu** aynı klasöre Depo ve select **Tamam**. Görüntülenen Sihirbazı'nda seçin **son**.

8. Seçin **Görünüm > Çözüm Gezgini** menüsünde.

9. İçinde **Çözüm Gezgini**, genişletin `python3` düğümünü sağ tıklatın `contemplate_koans.py`seçip **başlangıç dosyası olarak ayarlayın**. Bu adım Visual Studio Proje çalıştırırken kullanması gereken hangi dosya söyler.

10. Seçin **Proje > Koans özellikleri...**  menüsünden seçin **genel** sekmesini tıklatın ve ayarlama **çalışma dizini** "python3" için. Varsayılan olarak Visual Studio çalışma dizini başlangıç dosyasının konumu yerine Proje kök ayarladığından, bu adım gereklidir (`python3\contemplate_koans.py`, proje özelliklerinde de görebileceğiniz). Program kodu için bir dosya arar `koans.txt` çalışma klasöründe, bu nedenle bu değeri değiştirmeden gördüğünüz bir çalışma zamanı hatası.

    ![Python proje için çalışma dizini ayarlama](media/projects-set-working-directory.png)

11. CTRL + F5 tuşuna basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. Görürseniz bir `FileNotFoundError` için `koans.txt`, önceki adımda açıklandığı gibi ayarlar çalışma dizinini kontrol edin.

12. Program başarıyla çalıştırıldığında satırında 17 onaylama hata görüntüler `python3/koans/about_asserts.py`. Bu kasıtlıdır: program öğretmek sorununuz tarafından Python kasıtlı tüm hataları düzeltmek için tasarlanmıştır. (Daha fazla ayrıntı üzerinde bulunan [Ruby Koans](http://rubykoans.com/), Python Koans neden olacak.)

    ![İlk Python koans program çıktısı](media/koans-output.png)

13. Açık `python3/koans/about_asserts.py` Çözüm Gezgini'nde bulunduğu yere giderek ve dosyayı çift. Satır numaraları Düzenleyicisi'nde varsayılan olarak görünmez dikkat edin. Bunu değiştirmek için seçin **Araçlar > Seçenekler**seçin **tüm ayarları göster** iletişim kutusunun alt kısmındaki penceresine gidin **metin düzenleyicisi > Python > Genel** ve seçin **Satır numaraları**:

    ![Satır numarası Python dosyaları açma](media/options-general-line-numbers.png)

14. Değiştirerek hatayı düzeltin `False` satırına 17 bağımsız `True`. Satırı aşağıdaki gibi şöyle olmalıdır:

    ```python
    self.assertTrue(True) # This should be True
    ```

15. Programı yeniden çalıştırın. Visual Studio, hataları hakkında sizi uyarır, yanıt **Evet** kodu çalıştırmaya devam etmek için. Daha sonra ilk onay geçirir ve sonraki koan üzerinde programı durdurur bakın. Hataları ve program düzeltme devam etmek istediğiniz gibi yeniden.

> [!Important]
> Bu Hızlı Başlangıç, doğrudan bir kopyasını oluşturduğunuz *python_koans* github'daki. Bu tür bir depo yazarı doğrudan değişikliklere karşı korunur, böylece değişiklikleri depoya kaydedilmeye çalışılırken başarısız olur. Uygulamada, geliştiriciler bunun yerine, kendi GitHub hesabı için bir tür bir depoyu çatallaştırmanız, var. değişiklikleri yapın ve ardından bu değişiklikleri özgün deponuza göndermek için çekme isteği oluşturun. Kendi çatalı varsa, daha önce kullanılan özgün depo URL'si yerine URL'sini kullanın.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Ayrıca bkz.

- [El ile varolan bir Python yorumlayıcısı tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installing-python-support-in-visual-studio.md).
- [Konumları yüklemek](installing-python-support-in-visual-studio.md#install-locations).
