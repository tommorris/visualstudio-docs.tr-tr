---
title: Seçme ve Python yorumlayıcılar yükleniyor
description: Visual Studio'da kısa yönergelerle yükleyicilerinin nerede bulacağını üzerinde desteklenen Python yorumlayıcılar tam bir listesi.
ms.custom: ''
ms.date: 02/20/2018
ms.technology:
- devlang-python
ms.devlang: python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: f60d8cde8e729745bb8efd4a5df9f41ade15752a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="installing-python-interpreters"></a>Python yorumlayıcılar yükleme

Varsayılan olarak Visual Studio 2017 Python geliştirme iş yükü yükleme Python 3 (64 bit) yükler. İsteğe bağlı olarak 32-bit ve 64 bit sürümlerini Python 2, Python 3, Anaconda 2 ve Anaconda 3 ' ü yüklemek açıklandığı gibi seçebileceğiniz [yükleme](installing-python-support-in-visual-studio.md).

Visual Studio yükleyicisi dışında aşağıdaki tabloda listelenen yorumlayıcılar birini el ile de yükleyebilirsiniz. Örneğin, Visual Studio yüklemeden önce Anaconda 3 yüklediyseniz, Visual Studio yükleyicisi yeniden yüklemeniz gerekmez.

İçin **Visual Studio 2015 ve önceki**, yorumlayıcılar biri el ile yüklemelisiniz.

Visual Studio (tüm sürümler) otomatik olarak algılar her yüklü Python yorumlayıcı ve ortamına kayıt denetleyerek (aşağıdaki [CESARETLENDİRİCİ 514 - Python kayıt Windows kayıt defterinde](https://www.python.org/dev/peps/pep-0514/)).

Visual Studio yüklü bir ortam algılamazsa bkz [el ile varolan bir ortama tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).

Visual Studio gösteren tüm bilinen ortamlarda [Python ortamları penceresi](managing-python-environments-in-visual-studio.md)ve varolan yorumlayıcılar güncelleştirmeleri otomatik olarak algılar.

| Yorumlayıcı | Açıklama |
| --- | --- |
| [CPython](https://www.python.org/) | "Yerel" ve en sık kullanılan Yorumlayıcı, 32 bit ve 64 bit sürümleri (32-bit önerilir) içinde kullanılabilir. En son dil özellikleri, maksimum Python paket uyumluluk, hata ayıklama için tam destek ve birlikte çalışma içeren [IPython](http://ipython.org/). Ayrıca bkz: [Python 2 veya Python 3 kullanmalıyım?](http://wiki.python.org/moin/Python2orPython3). Visual Studio 2015 ve önceki Python 3.6 desteklemez ve "Python sürümü 3.6 desteklenmiyor" hata verebilirsiniz unutmayın. Python 3.5 veya önceki kullanmak yerine. |
| [IronPython](https://github.com/IronLanguages/ironpython2) | Bir .NET uygulaması sağlama C# /F #/ Visual Basic birlikte çalışabilirliği, Python, 32 bit ve 64 bit sürümlerinde kullanılabilir olan erişim .NET API'leri, hata ayıklama standart Python (ancak değil C++ karışık modda hata ayıklama için) ve IronPython karma / C# hata ayıklama. IronPython, ancak sanal ortamları desteklemez. |
| [Anaconda](https://www.continuum.io) | Bir açık veri bilimi platform tarafından Python gücü ve CPython ve zor yükleme paketleri en son sürümünü içerir. Aksi takdirde karar veremez, öneririz. |
| [PyPy](http://www.pypy.org/) | Uzun süre çalışan programlar ve performans tanımlamak burada durumlar için yararlı olan Python yüksek performans izleme JIT uyarlamasını verir ancak diğer çözümleri bulunamıyor. Visual Studio ile ancak sınırlı destek Works Gelişmiş hata ayıklama özellikleri için. |
| [Jython](http://www.jython.org/) | Python Java sanal makine'üzerinde (JVM) uygulaması. IronPython, Jython içinde çalışan kodu benzer Java sınıfları ve kitaplıkları ile etkileşim kurabilir, ancak birçok kitaplıkları için CPython hedeflenen kullanmanız mümkün olmayabilir. Visual Studio ile ancak sınırlı destek Works Gelişmiş hata ayıklama özellikleri için. |

Yeni formlar algılama Python ortamları için sağlamak istediğiniz geliştiriciler bkz [PTVS Ortam Algılama](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (github.com'u).

## <a name="moving-an-interpreter"></a>Bir yorumlayıcı taşıma

Varolan bir yorumlayıcı dosya sistemi kullanılarak yeni bir konuma taşırsanız, Visual Studio değişikliği otomatik olarak algılamaz.

- Yorumlayıcı konumunu ilk olarak belirttiyseniz, **Python ortamları** penceresinde, Düzen ortamı kullanarak **yapılandırma** yeni bir konum belirtmek için bu penceresindeki sekmesi. Bkz: [el ile varolan bir ortama tanımlayan](managing-python-environments-in-visual-studio.md#manually-identifying-an-existing-environment).

- Sonra bir yükleyici programı kullanarak yorumlayıcı yüklediyseniz, yeni konumdaki yorumlayıcı yeniden yüklemek için aşağıdaki adımları kullanın:

  1. Python yorumlayıcı orijinal konumuna geri yükleyin.
  2. Kayıt defteri girişlerini temizler kendi Yükleyicisi'ni kullanarak yorumlayıcı kaldırın.
  3. İstenen konuma yorumlayıcı yeniden yükleyin.
  4. Otomatik Algıla eski konum yerine yeni konumu Visual Studio'yu yeniden başlatın.

Bu işlem Visual Studio kullanır, Yorumlayıcı'nın konumu tanımlamak kayıt defteri girdileri düzgün şekilde güncelleştirilmesini sağlar. Bir yükleyici kullanarak, tüm diğer yan bulunabilecek etkileri işler.

## <a name="see-also"></a>Ayrıca bkz.

- [Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)