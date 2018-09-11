---
ms.technology: vs-ai-tools
ms.openlocfilehash: 5abaf2aafe2ff265123e9d4ed12f0ee350b22879
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283528"
---
# <a name="clone-a-repository-of-python-code-in-visual-studio"></a>Visual Studio'da Python kodunun bir depoyu kopyalama

Kaydederler [yapay ZEKA için Visual Studio Araçları yüklü](installation.md), kolayca Python kodu bir depoyu kopyalamak ve bir proje oluşturun.

1. Visual Studio Yükleyicisi'ni çalıştırın, GitHub depoları için bağlanmayı seçin **Değiştir**seçip **tek tek bileşenler** sekmesi. Ekranı aşağı kaydırarak **kod Araçları** bölümünden **Visual Studio için GitHub uzantısı**seçip **Değiştir**.

    ![Visual Studio Yükleyicisi'nde GitHub uzantısı seçme](media\create-project-repo\installation-github-extension.png)

2. Visual Studio'yu başlatın.

3. Seçin **Görüntüle > Takım Gezgini...**  açmak için **Takım Gezgini** penceresi içinde GitHub veya Azure DevOps bağlanabilir, ya da bir depoyu kopyalayın.

    ![Azure DevOps, GitHub'ı gösteren ve bir depo kopyalama Takım Gezgini penceresi](media\create-project-repo\team-explorer.png)

4. Altında alanına **yerel Git depoları**, girin `https://github.com/Microsoft/samples-for-ai`, kopyalanan dosyalar için bir klasör girin ve seçin **kopya**.

    > [!Tip]
    > Takım Gezgini'nde belirttiğiniz klasör, kopyalanan dosyalar almak için belirli bir klasördür. Farklı `git clone` komutunu, Ekip Gezgini'nde bir kopya oluşturma otomatik olarak oluşturmaz bir alt klasör deponun adını.

5. Kopyalama tamamlandığında, Team Explorer'ı depo panosuna gitmek için sayfanın alt kısmında depo klasörü çift tıklatın. Altında **çözümleri**seçin **yeni...** .

    ![Takım Gezgini penceresinde, bir kopya yeni proje oluşturma](media\create-project-repo\team-explorer-new-project.png)

6. İçinde **yeni proje** görüntülenen iletişim seçin "**ilk mevcut Python kodu**", proje için bir ad belirtin, Ayarla **konumu** deposu olarak aynı klasöre ve seçin **Tamam**. Açılan sihirbazda seçin **son**.

7. Seçin **Görüntüle > Çözüm Gezgini** menüsünde.

8. Çözüm Gezgini'nde `TensorFlow Examples> MNIST` düğümünü sağ `convolutional.py`seçip **başlangıç dosyası olarak ayarla**. Bu adım, Visual Studio projeyi çalışırken kullanması gereken hangi dosya söyler.

10. CTRL + F5 tuşlarına basın veya seçin **hata ayıklama > hata ayıklama olmadan Başlat** programı çalıştırmak için. Görürseniz bir ', önceki adımda ayarı çalışma dizini yeniden denetleyin.


11. Program başarıyla çalıştırıldığında, eğitim indirin ve veri kümesi, test sonra modeli eğitmek ve çıkış, hata oranı Başlat görürsünüz. İstediğiniz zaman içinde azaltmak için hata oranı

    ![İlk Python MNIST programının çıktısı](media\create-project-repo\tensorflow-mnist-running.png)

> Anaconda kullanıyorsanız ve eksik numpy hakkında bir hata iletisi, gerekebilir [Anaconda kullanmak için Python ortamınız değiştirme](../python/selecting-a-python-environment-for-a-project.md).

11. İlerleme durumunu TensorBoard görselleştirebilirsiniz. Projenize sağ tıklayın ve tıklayın **çalıştırma TensorBoard** TensorBoard günlükleri çıkış dizini'ı seçin.

    ![tensorboard çalıştırın](media\create-project-repo\run-tensorboard.png)

11. Kaliteyi artırma anlamına gelir, zaman içinde azalan hata dikkat edin.

    ![tensorboard çalıştırın](media\create-project-repo\tensorboard.png)