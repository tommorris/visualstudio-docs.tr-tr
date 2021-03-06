---
ms.technology: vs-ai-tools
ms.openlocfilehash: b86097cc1e0e531fe6f95a01cfa1cae5e4ac42d7
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33870622"
---
# <a name="create-an-ai-project-from-existing-code"></a>Var olan koddan AI projesi oluşturma

Seçtiğiniz sonra [AI için Visual Studio Araçları yüklü](installation.md), var olan Python kodu bir Visual Studio projeye Getir kolaydır.

> [!Important]
>
> Burada anlatılan işlemine taşımayın veya özgün kaynak dosyalarını kopyalayın. Bir kopya ile çalışmak isterseniz, klasörü ilk çoğaltma.

1. Visual Studio'yu başlatın ve seçin **Dosya > Yeni > Proje**.

1. İçinde **yeni proje** iletişim, arama "**AI Araçları**" seçin "**gelen varolan Python kodu**" şablonu, bir ad ve konum proje verin ve seçin**Tamam**.

    ![Var olan koddan adım 1 yeni proje](media\create-project-existing\new-ai-project.png)

1. Görüntülenen Sihirbazı'nda mevcut kodunuzu yolunu ayarlama, dosya türleri için bir filtre ayarlamak ve projenizi gerektirir ve ardından seçin arama yollarını belirtin **Tamam**. Yollar hangi arama bilmiyorsanız, bu alanı boş bırakın.

![Var olan koddan 2. adım yeni proje](media\create-project-existing\azurebatch-newproject.png)

> Mevcut kodunuzu bir Azure Machine Learning projesinin bir parçası ise denetleyin "**olan Azure Machine Learning klasörü**" başarılı dönüştürülmesi hangi deneme gibi önemli Azure Machine Learning yapılandırma ayrıntılarını sağlamak için hesabı, hangi çalışma alanında, kullanmak için işlem bağlamı ve daha fazlası.

1. Bir başlatma dosyası ayarlamak için dosyayı Çözüm Gezgini'nde sağ tıklatın ve seçin bulun **başlangıç dosyası olarak ayarlamak**.

1. İsterseniz, Ctrl + F5 tuşuna basarak veya seçerek program Çalıştır **hata ayıklama > hata ayıklama olmadan Başlat**.

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](../python/tutorial-working-with-python-in-visual-studio-step-00-installation.md)

## <a name="see-also"></a>Ayrıca Bkz.

- [El ile varolan bir Python ortamı tanımlayın](../python/managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment)