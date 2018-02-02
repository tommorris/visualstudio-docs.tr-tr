---
title: "Karışık mod Python/C++, Visual Studio'da hata ayıklama simgeleri | Microsoft Docs"
description: "Nasıl Visual Studio tam karma mod C++ ve Python hata ayıklama simgeleri yükleme yeteneği sağlar."
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 4657ed1c06605311dad0788a016760815f700b92
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="installing-debugging-symbols-for-python-interpreters"></a>Hata ayıklama simgeleri Python yorumlayıcılar için yükleme

Tam bir hata ayıklama deneyimini sağlamak üzere [karma mod Python hata ayıklayıcı](debugging-mixed-mode-c-cpp-python-in-visual-studio.md) Visual Studio'da simgeleri çok sayıda iç veri yapılarını ayrıştırmak için kullanılan Python yorumlayıcı için hata ayıklama. Python27.dll için örneğin, karşılık gelen simge python27.pdb dosyasıdır; python36.dll için python36.pdb simgesi dosyasıdır. Yorumlayıcı her sürümü aynı zamanda modülleri çeşitli simge dosyaları sağlar.

Visual Studio 2017, "Python 3" ile ve "Anaconda 3" yorumlayıcılar otomatik olarak kendi ilgili simgeleri yükleyin ve Visual Studio bu simgeleri otomatik olarak bulur. Visual Studio 2015 ve önceki sürümler için veya diğer yorumlayıcılar kullanırken, simgeler ayrı olarak karşıdan Visual Studio üzerine gelin ve ardından bunları yapmanız **Araçlar > Seçenekler** iletişim kutusunda **hata ayıklama > sembolleri**  sekmesi. Bu adımlar aşağıdaki bölümlerde ayrıntılı olarak açıklanmaktadır.

Karışık mod hata ayıklama oturumu başlatılırken sembolleri genellikle ihtiyaç duyduğunda, visual Studio isteyebilir. Bu durumda, iki seçenek içeren bir iletişim kutusu görüntüler:

- **Açık Simge Ayarları iletişim kutusu** açılır **seçenekleri** iletişim kutusuna **hata ayıklama > sembolleri** sekmesi.
- **Simgeleri my yorumlayıcı için karşıdan yüklemek** bu mevcut belgeleri sayfasını; bu durumda seçin açar **Araçlar > Seçenekler** gidin **hata ayıklama > simgeleri** devam etmek için sekme.

    ![Karışık mod hata ayıklayıcı simgeleri istemi](media/mixed-mode-debugging-symbols-required.png)

## <a name="downloading-symbols"></a>Simgeler indirme

- Python 3.5 ve sonraki sürümler: hata ayıklama simgeleri Python yükleyici aracılığıyla Al. Seçin **özel yükleme**seçin **sonraki** almak için **Gelişmiş Seçenekler**, kutularını seçip **hata ayıklama simgeleri karşıdan** ve **indirme hata ayıklama ikili**:

    ![Hata ayıklama simgeleri de dahil olmak üzere Python 3.x yükleyici](media/mixed-mode-debugging-symbols-installer35.png)

    Simge dosyaları (`.pdb`) sonra kök yükleme klasöründe bulunan (tek tek modülleri için simge dosyaları olan `DLLs` klasörünün yanı sıra). Bu nedenle, Visual Studio bunları otomatik olarak bulur ve başka bir adım gereklidir.

- Python 3.4.x ve daha önceki sürümlerde: indirilebilir .zip dosyalarından olarak semboller kullanılabilir [resmi dağıtımları](#official-distributions) veya [Enthought Kanopi](#enthought-canopy). İndirdikten sonra dosyaları gibi devam için yerel bir klasöre ayıklayın bir `Symbols` klasörün içinde Python klasör.

    > [!Important]
    > Simgeler Python alt yapı arasında farklılık gösterir ve 32-bit ve 64-bit derlemeleri arasında şekilde tam olarak sürümleri eşleştirmek istediğiniz. Kullanılan yorumlayıcı denetlemek için Genişlet **Python ortamları** *düğümü* projenizi Çözüm Gezgini'nde ve Not ortam adı altında. O **Python ortamları** *penceresi* ve yükleme konumu not edin. Ardından bu konumda bir komut penceresi açın ve Başlat `python.exe`, tam sürümünü görüntüleyen ve 32 bit veya 64-bit olup.

- ActiveState Python gibi başka bir üçüncü taraf Python dağıtım için: Bu dağıtım yazarları başvurun ve bunları sembolleriyle sağlamak üzere isteyin. WinPython, kendi bölümü için değişiklik yapmadan standart Python yorumlayıcısı içerir, bu nedenle simgeleri resmi dağıtım için karşılık gelen sürüm numarasını kullanın.

## <a name="pointing-visual-studio-to-the-symbols"></a>Visual Studio simgeleri işaret eden

Simgeler ayrı olarak yüklediyseniz, Visual Studio bunları haberdar olmak için aşağıdaki adımları izleyin. Python 3.5 veya sonraki Yükleyici ile simgeleri yüklediyseniz, Visual Studio otomatik olarak bulur.

1. Seçin **Araçlar > Seçenekler** menü gidin **hata ayıklama > sembolleri**.
    
1. Seçin **Ekle** düğmesi (aşağıda gösterilen) araç çubuğunda, genişletilmiş burada indirilen simgeleri klasörü girin (nerede olduğu `python.pdb` gibi bulunduğu `c:\python34\Symbols`, aşağıda gösterilen) ve seçin **Tamam**. 

    ![Karışık mod hata ayıklayıcısı seçeneklerini simgeleri](media/mixed-mode-debugging-symbols.png)

1. Hata ayıklama oturumu sırasında Visual Studio ayrıca, bir kaynak dosya konumu Python yorumlayıcı için isteyebilir. Kaynak dosyalarını indirdiğiniz varsa (gelen [python.org/downloads](https://www.python.org/downloads), örneğin), sonra da, Elbette bunları da işaret edebilir.

> [!Note]
> İletişim kutusunda gösterilen simgesi önbelleğe alma özelliklerini, çevrimiçi bir kaynaktan simgelerin yerel önbellek oluşturmak için kullanılır. Simgeler zaten yerel olarak mevcut olduğundan bu özellikleri Python yorumlayıcı sembolleriyle gerekli değildir. Her iki durumda da başvurmak [sembolleri belirtin ve Visual Studio hata ayıklayıcısı kaynak dosyalarında](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md) Ayrıntılar için.

## <a name="official-distributions"></a>Resmi dağıtımları

| Python sürümü | İndirmeler | 
| --- | --- | 
| 3.5 ve sonraki sürümler | Python yükleyici aracılığıyla simgeler yükleyebilir. | 
| 3.4.4 | [32-bit](https://www.python.org/ftp/python/3.4.4/python-3.4.4-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.4/python-3.4.4.amd64-pdb.zip) |
| 3.4.3 | [32-bit](https://www.python.org/ftp/python/3.4.3/python-3.4.3-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.3/python-3.4.3.amd64-pdb.zip) |
| 3.4.2 | [32-bit](https://www.python.org/ftp/python/3.4.2/python-3.4.2-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.2/python-3.4.2.amd64-pdb.zip) |
| 3.4.1 | [32-bit](https://www.python.org/ftp/python/3.4.1/python-3.4.1-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.1/python-3.4.1.amd64-pdb.zip) |
| 3.4.0 | [32-bit](https://www.python.org/ftp/python/3.4.0/python-3.4.0-pdb.zip) - [64-bit](https://www.python.org/ftp/python/3.4.0/python-3.4.0.amd64-pdb.zip) |
| 3.3.5 | [32-bit](http://www.python.org/ftp/python/3.3.5/python-3.3.5-pdb.zip) - [64-bit](http://www.python.org/ftp/python/3.3.5/python-3.3.5.amd64-pdb.zip) |
| 3.3.4 | [32-bit](http://python.org/ftp/python/3.3.4/python-3.3.4-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.4/python-3.3.4.amd64-pdb.zip) |
| 3.3.3 | [32-bit](http://python.org/ftp/python/3.3.3/python-3.3.3-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.3/python-3.3.3.amd64-pdb.zip) |
| 3.3.2 | [32-bit](http://python.org/ftp/python/3.3.2/python-3.3.2-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.2/python-3.3.2.amd64-pdb.zip) |
| 3.3.1 | [32-bit](http://python.org/ftp/python/3.3.1/python-3.3.1-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.1/python-3.3.1.amd64-pdb.zip) |
| 3.3.0 | [32-bit](http://python.org/ftp/python/3.3.0/python-3.3.0-pdb.zip) - [64-bit](http://python.org/ftp/python/3.3.0/python-3.3.0.amd64-pdb.zip) |
| 2.7.11 | [32-bit](https://www.python.org/ftp/python/2.7.11/python-2.7.11-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64-pdb.zip) |
| 2.7.10 | [32-bit](https://www.python.org/ftp/python/2.7.10/python-2.7.10-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.10/python-2.7.10.amd64-pdb.zip) |
| 2.7.9 | [32-bit](https://www.python.org/ftp/python/2.7.9/python-2.7.9-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.9/python-2.7.9.amd64-pdb.zip) |
| 2.7.8 | [32-bit](https://www.python.org/ftp/python/2.7.8/python-2.7.8-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.8/python-2.7.8.amd64-pdb.zip) |
| 2.7.7 | [32-bit](https://www.python.org/ftp/python/2.7.7/python-2.7.7-pdb.zip) - [64-bit](https://www.python.org/ftp/python/2.7.7/python-2.7.7.amd64-pdb.zip) |
| 2.7.6 | [32-bit](http://python.org/ftp/python/2.7.6/python-2.7.6-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.6/python-2.7.6.amd64-pdb.zip) |
| 2.7.5 | [32-bit](http://python.org/ftp/python/2.7.5/python-2.7.5-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.5/python-2.7.5.amd64-pdb.zip) |
| 2.7.4 | [32-bit](http://python.org/ftp/python/2.7.4/python-2.7.4-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.4/python-2.7.4.amd64-pdb.zip) |
| 2.7.3 | [32-bit](http://python.org/ftp/python/2.7.3/python-2.7.3-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.3/python-2.7.3.amd64-pdb.zip) |
| 2.7.2 | [32-bit](http://python.org/ftp/python/2.7.2/python-2.7.2-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.2/python-2.7.2.amd64-pdb.zip) |
| 2.7.1 | [32-bit](http://python.org/ftp/python/2.7.1/python-2.7.1-pdb.zip) - [64-bit](http://python.org/ftp/python/2.7.1/python-2.7.1.amd64-pdb.zip) |


## <a name="enthought-canopy"></a>Enthought Kanopi

Enthought Kanopi simgeleri 1.2 sürümünden başlayarak, ikili dosyaları sağlar. Bunlar otomatik olarak yanında dağıtım yüklenir, ancak, daha önce açıklandığı gibi simge yolu içeren klasörü el ile eklemeniz gerekir. Simgeleri bulunan Kanopi tipik kullanıcı başına yüklenmesi için `%UserProfile%\AppData\Local\Enthought\Canopy\User\Scripts` 64-bit sürümü için ve `%UserProfile%\AppData\Local\Enthought\Canopy32\User\Scripts` 32-bit sürümü için.

Enthought Python dağıtım (EPD) yanı sıra Enthought Kanopi 1.1 ve önceki yorumlayıcı simgeleri sağlamaz ve bu nedenle karışık mod hata ayıklaması ile uyumlu değildir.