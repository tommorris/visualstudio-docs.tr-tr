---
title: "Hızlı Başlangıç: Visual Studio'da Python kodu bir depoyu kopyalama | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: quickstart
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 74be5c65cbb4b2498f9904c6e021c774400bfbf8
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2018
---
# <a name="quickstart-clone-a-repository-of-python-code-in-visual-studio"></a>Hızlı Başlangıç: Visual Studio'da Python kodu bir depoyu kopyalayın

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installing-python-support-in-visual-studio.md), kolayca depoyu Python kodu kopyalayın ve bir proje oluşturun.

[!INCLUDE[install-github-extension](includes/install-github-extension.md)]

2. Visual Studio'yu başlatın.

3. Seçin **Görünüm > Takım Gezgini...**  açmak için **Takım Gezgini** , GitHub veya Visual Studio Team Services bağlanmak veya için bir depoyu kopyalayın penceresi.

    ![Takım Gezgini penceresi gösteren Visual Studio Team Services, GitHub ve depo kopyalama](media/team-explorer.png)

4. Altında URL'si alanına **yerel Git depoları**, girin `https://github.com/gregmalcolm/python_koans`, kopyalanan dosyalar için bir klasör girin ve seçin **kopya**.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalarını almak için belirli bir klasördür. Farklı `git clone` komutunu Takım Gezgini'nde kopyasını oluşturma otomatik olarak oluşturmaz alt depo adını.

5. Kopyalama tamamlandıktan sonra deposu panoya gitmek için Takım Gezgini, alttaki Depo klasörünü çift tıklatın. Altında **çözümleri**seçin **yeni...** .

    ![Takım Gezgini penceresi, bir kopya yeni proje oluşturma](media/team-explorer-new-project.png)

6. İçinde **yeni proje** görünür, iletişim "Den varolan Python kodu" seçin, proje için bir ad belirtin, Ayarla **konumu** depo ve select aynı klasöre **Tamam**. Görüntülenen Sihirbazı'nda seçin **son**.

7. Seçin **Görünüm > Çözüm Gezgini** menüsünde.

8. Çözüm Gezgini'nde genişletin `python3` düğümünü sağ tıklatın `contemplate_koans.py`seçip **başlangıç dosyası olarak ayarlayın**. Bu adım Visual Studio Proje çalıştırırken kullanması gereken hangi dosya söyler.

9. Seçin **Proje > Özellikler** menüsünden seçin **genel** sekmesini tıklatın ve ayarlama **çalışma dizini** "python3" için. Varsayılan olarak Visual Studio çalışma dizini başlangıç dosyasının konumu yerine Proje kök ayarladığından bu gereklidir (`python3\contemplate_koans.py`, proje özelliklerinde de görebileceğiniz). Program kodu için bir dosya arar `koans.txt` çalışma klasöründe, bu nedenle bu değeri değiştirmeden göreceksiniz çalışma zamanı hatası.

    ![Python proje için çalışma dizini ayarlama](media/projects-set-working-directory.png)

10. CTRL + F5 tuşuna basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. Görürseniz bir `FileNotFoundError` için `koans.txt`, önceki adımda ayarlama Çalışma dizini yeniden denetleyin.

11. Program başarıyla çalıştırıldığında satırında 17 onaylama hata görüntüler `python3/koans/about_asserts.py`. Bu kasıtlıdır: program öğretmek sorununuz tarafından Python kasıtlı tüm hataları düzeltmek için tasarlanmıştır. (Daha fazla ayrıntı üzerinde bulunan [Ruby Koans](http://rubykoans.com/), Python Koans neden olacak.)

    ![İlk Python koans program çıktısı](media/koans-output.png)

12. Açık `python3/koans/about_asserts.py` Çözüm Gezgini'nde bulunduğu yere giderek ve dosyayı çift. Satır numaraları Düzenleyicisi'nde varsayılan olarak görünmez dikkat edin. Bunu değiştirmek için seçin **Araçlar > Seçenekler**seçin **tüm ayarları göster** iletişim kutusunun alt kısmındaki penceresine gidin **metin düzenleyicisi > Python > Genel** ve seçin **Satır numaraları**:

    ![Satır numarası Python dosyaları açma](media/options-general-line-numbers.png)

13. Değiştirerek hatayı düzeltin `False` satırına 17 bağımsız `True`. Satırı aşağıdaki gibi şöyle olmalıdır:

    ```python
    self.assertTrue(True) # This should be True
    ```

14. Yeniden ilk onay geçtiğini görmek için programını çalıştırın ve sonraki koan üzerinde programı durdurur. Hatalarını düzeltme ve istediğiniz programın yeniden çalıştırma devam edin.

> [!Important]
> Bu Hızlı Başlangıç, doğrudan bir kopyasını oluşturduğunuz *python_koans* github'daki. Bu tür bir depo yazarı doğrudan değişikliklere karşı korunur, böylece değişiklikleri depoya kaydedilmeye çalışılırken başarısız olur. Uygulamada, geliştiriciler bunun yerine, kendi GitHub hesabı için bir tür bir depoyu çatallaştırmanız, var. değişiklikleri yapın ve ardından bu değişiklikleri özgün deponuza göndermek için çekme isteği oluşturun. Bu adımları açıklanan [öğretici Git ile çalışma 6. adım -](tutorial-working-with-python-in-visual-studio-step-06-working-with-git.md).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Varolan bir Python yorumlayıcısı için bir ortam oluşturma](managing-python-environments-in-visual-studio.md#creating-an-environment-for-an-existing-interpreter).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installing-python-support-in-visual-studio.md).
- [Konumları yüklemek](installing-python-support-in-visual-studio.md#install-locations).
