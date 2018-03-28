---
title: Paket gereksinimlerini yönetmek için requirements.txt dosyasını kullanarak | Microsoft Docs
description: Bir proje bağımlılıklarınızı yönetmek için bir requirements.txt dosyasını kullanabilirsiniz. Requirements.txt dosyasını içeren bir proje almaya devam ederseniz, bu bağımlılıkları tek bir adımda kolayca yükleyebilirsiniz.
ms.custom: ''
ms.date: 02/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: b9d1a35d8ba34561c56ca14261591c7b80bacdb0
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="managing-required-packages-with-requirementstxt"></a>Gerekli paketleri requirements.txt ile yönetme

Bir proje başkalarıyla yapı sistemini kullanarak paylaşıyorsanız ya da planlıyorsanız [için Microsoft Azure yayımlama](python-azure-cloud-service-project-template.md), proje gerektiren dış paketler belirtmeniz gerekir. Kullanmak için önerilen yaklaşımdır bir [requirements.txt dosyasını](http://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org) bağımlı paketler gerekli sürümlerini yükler PIP komutların listesini içerir.

Teknik olarak, dosya gereksinimleri izlemek için kullanılabilir (kullanarak `-r <full path to file>` bir paket yüklerken), ancak Visual Studio'nun sağladığı belirli desteği `requirements.txt`:

- İçeren bir proje yüklerse `requirements.txt` ve bu dosyada listelenen paketleri yüklemek isterseniz, genişletin **Python ortamları** düğümünde **Çözüm Gezgini**, sonra sağ bir ortam düğümü ve select **Requirements.txt'ten Yükle**:

    ![Requirements.txt'ten yükle](media/environments-requirements-txt-install.png)

- Bir ortamda yüklü tüm gerekli paketler zaten varsa, bu ortam Çözüm Gezgini'nde sağ tıklatın ve seçin **requirements.txt Oluştur** gerekli dosya oluşturulamadı. Dosya zaten mevcutsa güncelleştirmek için bir istem görüntülenir:

    ![Güncelleştirme requirements.txt seçenekleri](media/environments-requirements-txt-replace.png)

  - **Dosyanın tamamı yerine** tüm öğeleri, açıklamalar ve mevcut olan seçenekler kaldırır.
  - **Varolan girişleri yenileme** paket gereksinimlerini algılar ve, şu anda yüklü olan sürümle eşleştirmek için sürüm tanımlayıcıları güncelleştirir.
  - **Güncelleştirme ve girişleri ekleme** bulunur ve diğer tüm paketler dosyanın sonuna ekler gereksinimlere yeniler.

Çünkü `requirements.txt` dosyaları bir ortamı gereksinimlerini donmasına yöneliktir, yüklü olan tüm paketlerin kesin sürümleriyle yazılır. Kesin sürümlerini kullanan başka bir bilgisayarda ortamınızı kolayca üretebileceği sağlar. PIP dışında bir yükleyici veya başka bir paketi bir bağımlılık olarak bir sürüm aralığı ile yüklenmiş olsa bile paketleri dahil edilir.

Bir paket pip tarafından yüklenemez ve görünür bir `requirements.txt` dosyası, tüm yükleme başarısız olur. Bu durumda, bu paket dışlanacak veya kullanılacak dosyasını el ile düzenleme [PIP'ın seçenekleri](http://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format) yüklenebilir bir paketin sürümü için başvurmak için. Örneğin, kullanmayı tercih edebilirsiniz [ `pip wheel` ](http://pip.readthedocs.org/en/latest/reference/pip_wheel.html) bağımlılığı derlemek ve eklemek için `--find-links <path>` için seçenek, `requirements.txt`:

```output
C:\Project>pip wheel azure
Downloading/unpacking azure
    Running setup.py (path:C:\Project\env\build\azure\setup.py) egg_info for package azure

Building wheels for collected packages: azure
    Running setup.py bdist_wheel for azure
    Destination directory: c:\project\wheelhouse
Successfully built azure
Cleaning up...

C:\Project>type requirements.txt
--find-links wheelhouse
--no-index
azure==0.8.0

C:\Project>pip install -r requirements.txt -v
Downloading/unpacking azure==0.8.0 (from -r requirements.txt (line 3))
    Local files found: C:/Project/wheelhouse/azure-0.8.0-py3-none-any.whl
Installing collected packages: azure
Successfully installed azure
Cleaning up...
    Removing temporary dir C:\Project\env\build...
```

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)