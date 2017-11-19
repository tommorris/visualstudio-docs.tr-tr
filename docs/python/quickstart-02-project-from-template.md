---
title: "Hızlı Başlangıç: Visual Studio'da bir şablondan bir Python projesi oluşturun. | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f4b66c5-3ad8-4067-90cd-0100205700a7
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 77e630f7ebfe5739010291ffc62e23a695c40807
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>Hızlı Başlangıç: Visual Studio'da bir şablondan bir Python projesi oluşturma

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installation.md), şablonları, çeşitli kullanarak yeni bir Python proje oluşturmak kolaydır.

1. Visual Studio'yu başlatın.

1. Seçin **Dosya > Yeni > Proje** (Ctrl + Shift + N). İçinde **yeni proje** iletişim, arama "Python" ve istediğiniz şablonu seçin. Bir şablon seçerek şablonu sağlar kısa bir açıklama görüntüler unutmayın. (Ayrıca bkz. [Python projeleri](python-projects.md#project-templates).)

    ![Python şablonuyla VS2017 yeni proje iletişim kutusu](media/projects-new-project-dialog2.png)

1. Bu Hızlı Başlangıç için "Python uygulaması" şablonunu seçin, proje adı (örneğin, "MakePI") ve konum verin ve seçin **Tamam**. 

1. Visual Studio Proje dosyası oluşturur (bir `.pyproj` diskteki dosya) yanı sıra şablon tarafından açıklanan diğer dosyaları. "Python uygulama" şablonuyla proje projenizi aynı adlı yalnızca bir boş dosya içeriyor. Dosyanın varsayılan olarak Visual Studio düzenleyicisinde açın.

    ![Python uygulama şablonu kullanırken sonuç projesi](media/projects-new-structure.png)

1. Aşağıdaki kod, hesaplar ve 1000 basamak pi'nin görüntüler gibi bazı kodu açık dosyaya ekleyin:

    ```python
    """ Print digits of PI; code adapted from the second, shorter solution
    at http://www.codecodex.com/wiki/Calculate_digits_of_pi#Python
    """

    from time import perf_counter

    def pi_digits_Python(digits):
        scale = 10000
        maxarr = int((digits / 4) * 14)
        arrinit = 2000
        carry = 0
        arr = [arrinit] * (maxarr + 1)
        output = ""

        for i in range(maxarr, 1, -14):
            total = 0
            for j in range(i, 0, -1):
                total = (total * j) + (scale * arr[j])
                arr[j] = total % ((j * 2) - 1)
                total = total / ((j * 2) - 1)

            output += "%04d" % (carry + (total / scale))
            carry = total % scale

        return output;

    def test_py():
        digits = 1000;

        start = perf_counter()
        output = pi_digits_Python(digits);
        elapsed = perf_counter() - start;

        print("PI to " + str(digits) + " digits in " + str(int(elapsed * 10000)/10000) + " seconds:")

        ## replace inserts the decimal point
        print(output.replace("3", "3.", 1))

    if __name__ == "__main__":
        test_py();
    ```

1. Ctrl + F5 tuşuna basarak veya seçerek program Çalıştır **hata ayıklama > hata ayıklama olmadan Başlat** menüsünde. Sonuçları konsol penceresinde görüntülenir.

## <a name="next-steps"></a>Sonraki Adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](vs-tutorial-01-01.md)

## <a name="see-also"></a>Ayrıca Bkz.

- [Varolan bir Python yorumlayıcısı için bir ortam oluşturma](python-environments.md#creating-an-environment-for-an-existing-interpreter).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installation.md).
- [Konumları yüklemek](installation.md#install-locations).
