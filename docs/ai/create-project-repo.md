---
ms.technology: vs-ai-tools
ms.openlocfilehash: 73292b9e0c7df23db839a7a13f70dbc2432d564f
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/28/2018
ms.locfileid: "29708780"
---
# <a name="clone-a-repository-of-python-code-in-visual-studio"></a>Visual Studio'da Python kodu bir depoyu kopyalayın

Seçtiğiniz sonra [AI için Visual Studio Araçları yüklü](installation.md), kolayca depoyu Python kodu kopyalayın ve bir proje oluşturun.

1. Visual Studio yükleyiciyi çalıştırmak GitHub depoları için bağlanmak için **Değiştir**seçip **bileşenleri tek tek** sekmesi. Ekranı aşağı kaydırarak **kod Araçları** bölümünde, select **Visual Studio için GitHub uzantısı**ve seçin **Değiştir**.

    ![Visual Studio yükleyicisinde GitHub uzantısı seçme](media\create-project-repo\installation-github-extension.png)

2. Visual Studio'yu başlatın.

3. Seçin **Görünüm > Takım Gezgini...**  açmak için **Takım Gezgini** , GitHub veya Visual Studio Team Services bağlanmak veya için bir depoyu kopyalayın penceresi.

    ![Takım Gezgini penceresi gösteren Visual Studio Team Services, GitHub ve depo kopyalama](media\create-project-repo\team-explorer.png)

4. Altında URL'si alanına **yerel Git depoları**, girin `https://github.com/Microsoft/samples-for-ai`, kopyalanan dosyalar için bir klasör girin ve seçin **kopya**.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalarını almak için belirli bir klasördür. Farklı `git clone` komutunu Takım Gezgini'nde kopyasını oluşturma otomatik olarak oluşturmaz alt depo adını.

5. Kopyalama tamamlandıktan sonra deposu panoya gitmek için Takım Gezgini, alttaki Depo klasörünü çift tıklatın. Altında **çözümleri**seçin **yeni...** .

    ![Takım Gezgini penceresi, bir kopya yeni proje oluşturma](media\create-project-repo\team-explorer-new-project.png)

6. İçinde **yeni proje** görünen seçin iletişim "**ilk varolan Python kodu**", proje için bir ad belirtin, Ayarla **konumu** deposu olarak aynı klasöre ve seçin **Tamam**. Görüntülenen Sihirbazı'nda seçin **son**.

7. Seçin **Görünüm > Çözüm Gezgini** menüsünde.

8. Çözüm Gezgini'nde genişletin `TensorFlow Examples> MNIST` düğümünü sağ tıklatın `convolutional.py`seçip **başlangıç dosyası olarak ayarlayın**. Bu adım Visual Studio Proje çalıştırırken kullanması gereken hangi dosya söyler.

10. CTRL + F5 tuşuna basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. Görürseniz bir ', önceki adımda ayarlama Çalışma dizini yeniden denetleyin.


11. Program başarıyla çalıştığında, bunu, eğitim karşıdan yükle ve veri kümesi, test sonra modeli eğitmek ve çıkış hata oranı Başlat görürsünüz. İstediğiniz zaman içinde azaltmak için hata oranı

    ![İlk Python MNIST program çıktısı](media\create-project-repo\tensorflow-mnist-running.png)

> Anaconda kullanıyorsanız ve eksik numpy hakkında bir hata alırsanız gerekebilir [Python ortamınızı Anaconda kullanacak şekilde değiştirme](../python/selecting-a-python-environment-for-a-project.md).

11. İlerleme TensorBoard ile görselleştirebilirsiniz. Projenize sağ tıklayın ve tıklayın **çalıştırmak TensorBoard** TensorBoard günlükleri, çıktı dizini seçin.

    ![tensorboard Çalıştır](media\create-project-repo\run-tensorboard.png)

11. Fazla mesai, azalan hata kalitesini arttırma anlamına gelir dikkat edin

    ![tensorboard Çalıştır](media\create-project-repo\tensorboard.png)