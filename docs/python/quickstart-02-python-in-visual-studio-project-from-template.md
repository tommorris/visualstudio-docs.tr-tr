---
title: "Hızlı Başlangıç - bir şablon kullanarak Visual Studio'da Python projesi oluşturun | Microsoft Docs"
description: "Yerleşik şablonlarından birini kullanarak bir Visual Studio projesi oluşturarak Python hızlı şekilde kullanmaya başlayın."
ms.custom: 
ms.date: 03/08/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: quickstart
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 4ab0f91022240d1fcf60bd6889ea9b2ec39f2db3
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>Hızlı Başlangıç: Visual Studio'da bir şablondan bir Python projesi oluşturma

Seçtiğiniz sonra [Python desteği Visual Studio 2017 yüklü](installing-python-support-in-visual-studio.md), şablonları, çeşitli kullanarak yeni bir Python proje oluşturmak kolaydır.

1. Visual Studio'yu başlatın.

1. Seçin **Dosya > Yeni > Proje** (Ctrl + Shift + N). İçinde **yeni proje** iletişim, arama "Python" ve istediğiniz şablonu seçin. Bir şablon seçerek şablonu sağlar kısa bir açıklama görüntüler unutmayın. (Ayrıca bkz. [Python projeleri](managing-python-projects-in-visual-studio.md#project-templates).)

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

        return output

    def test_py():
        digits = 1000

        start = perf_counter()
        output = pi_digits_Python(digits)
        elapsed = perf_counter() - start

        print("PI to " + str(digits) + " digits in " + str(int(elapsed * 10000)/10000) + " seconds:")

        ## replace inserts the decimal point
        print(output.replace("3", "3.", 1))

    if __name__ == "__main__":
        test_py()
    ```

1. Ctrl + F5 tuşuna basarak veya seçerek program Çalıştır **hata ayıklama > hata ayıklama olmadan Başlat** menüsünde. Sonuçları konsol penceresinde görüntülenir.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Öğretici: Visual Studio'da Python ile çalışma](tutorial-working-with-python-in-visual-studio-step-01-create-project.md)

## <a name="see-also"></a>Ayrıca bkz.

- [El ile varolan bir Python yorumlayıcısı tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).
- [Python desteği Visual Studio 2015 ve daha önce yükleme](installing-python-support-in-visual-studio.md).
- [Konumları yüklemek](installing-python-support-in-visual-studio.md#install-locations).
