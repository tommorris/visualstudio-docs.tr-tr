---
title: Python arama yolları nasıl uygulanır
description: Visual Studio Python arama yollarında ortamları ve projeleri nasıl kullandığı bir genel bakış.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: d1d05670192630e0bc4903988770c52840a5e347
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37118245"
---
# <a name="how-visual-studio-uses-python-search-paths"></a>Visual Studio Python arama yolları nasıl kullanır

Tipik Python kullanımla `PYTHONPATH` ortam değişkeni (veya `IRONPYTHONPATH`, vs.) Modülü dosyaları için varsayılan arama yolu sağlar. Diğer bir deyişle, kullandığınızda, bir `from <name> import...` veya `import <name>` deyimi, Python için eşleşen bir ada sırayla aşağıdaki konumlarda arar:

1. Python'un yerleşik modüller.
1. Çalıştırmakta olduğunuz Python kodu içeren klasör.
1. "Geçerli ortam değişkeni tarafından tanımlanan modülü arama yolu" olarak. (Bkz [modülü arama yolu](https://docs.python.org/2/tutorial/modules.html#the-module-search-path) ve [ortam değişkenleri](https://docs.python.org/2/using/cmdline.html#envvar-PYTHONPATH) Python belge temel.)

Visual Studio arama path ortam değişkeni bile tüm sistem için değişken ayarlandığında ancak yok sayar. Göz ardı, aslında, tam olarak *çünkü* tüm sistem için ayarlanır ve bu nedenle otomatik olarak yanıtlanamaz bazı sorular başlatır: olan Python 2.7 veya Python 3.6 amacı başvurulan modülleri? Standart kitaplık modülleri geçersiz kılma olacak? Bu davranış, geliştirici farkındadır yoksa bir kötü amaçlı geçirme girişimi mı?

Visual Studio, böylece arama yolları doğrudan hem ortamları ve projeleri belirtmek için bir yol sağlar. Çalıştırın ya da hata ayıklama Visual Studio'da kod değerinde arama yolları alır `PYTHONPATH` (ve diğer eşdeğer değişkenleri). Arama yollarına ekleyerek, Visual Studio konumların kitaplıklarında inceler ve IntelliSense veritabanları için onları gerektiğinde yapıları (Visual Studio 2017 sürüm 15,5 ve önceki; veritabanı oluşturmak biraz zaman alabilir kitaplıkları sayısına bağlı olarak).

Bir arama yolu eklemek için sağ **arama yolları** Çözüm Gezgini'nde, select öğesi **klasörü için arama yolu Ekle...** ve dahil etmek için klasörü seçin. Bu yol projeyle ilişkili herhangi bir ortam için kullanılır. (Hatalar ortamı Python 3 tabanlı ve Python 2.7 modülleri için bir arama yolu Ekle çalışırsanız görebilirsiniz.)

İle dosyaları bir `.zip` veya `.egg` uzantısı da eklenebilir arama yolları olarak seçerek **Zip arşivine arama yolu Ekle...** . Klasörlerle olduğu gibi bu dosyaların içeriğini taranan ve IntelliSense için kullanılabilir.

Aynı arama yolları kullanarak düzenli olarak ve içeriği genellikle değiştirmeyin, site paket klasörünüze yüklemek için daha etkili olabilir. Arama yolu ardından analiz ve IntelliSense veritabanında depolanan, her zaman hedeflenen ortamı ile ilişkili olması ve her projeye eklemek için bir arama yolu gerektirmez.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)