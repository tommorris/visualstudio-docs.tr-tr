---
title: Bir alt sürüme deposu ayarlama
description: Alt sürüme Mac için Visual Studio kullanarak
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: e5f395511ad3b2b3cc4568a4d701ca5dbcc02736
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
ms.locfileid: "34000263"
---
# <a name="setting-up-a-subversion-repository"></a>Bir alt sürüme deposu ayarlama

Alt sürüme olan bir merkezi _sürüm denetimi sistemi_, tüm dosyaları ve düzeltmelerini içeren tek bir sunucu olduğu anlamına gelir, hangi kullanıcıların herhangi bir dosyayı herhangi bir sürümü kontrol edebilirsiniz. Dosyalar bir uzak alt sürüme depodan kullanıma, kullanıcı bir anlık görüntü depo zamandaki o noktada alır.

Sürüm denetimi için alt sürüme kullanmak için makinenizde yüklenmelidir. Alt sürüme ise denetlemek için makinenize yüklü, Terminal içinde aşağıdaki komutu kullanın:

```bash
svn --version
```

Bu komut, sürüm numarasını döndürür.

Alt sürüme zaten yüklü değilse, bunu almak için kolay yükleyerek yoludur _Xcode komut satırı araçları_. Xcode komut satırı araçları ve alt sürüme yüklemek için aşağıdaki komutu kullanın.

```bash
xcode-select --install
```

Alt sürüme makinenizde yüklendikten sonra projenizin SVN içinde yayımlamak için aşağıdaki adımları kullanın.

1. Bir ücretsiz SVN deposu oluşturun. Bu örnek için [Assembla](https://app.assembla.com/) kullanıldı. Oluşturduktan sonra bir URL sağlanacaktır, hangi depoya bağlanmak için kullanılacak: 

    ![SVN URL'sini Kopyala](media/version-control-subversion1-sml.png)

2. Visual Studio için Mac projesi oluşturun veya açın.

3. Sağ tıklayın proje ve select **sürüm denetimi > Sürüm denetimi Yayımla...** : 

    ![Proje Yayımlama Başlat](media/version-control-subversion2.png)

4. İçinde **depo Bağlan** sekmesine **alt sürüme** en yukarıdan aşağı açılır.

5. Adım 1'den URL'sini girin. Girilen URL sonra diğer alanları varsayılan olarak doldurulur: 

    ![Depo seçin ve iletişim ayrıntılarını girin](media/version-control-subversion3.png)

7. Tıklatın **Tamam** ve tuşlarına basarak onaylayın **Yayımla**.

7. İstenirse, kimlik bilgilerinizi site deposu oluşturmak için aşağıda gösterildiği gibi girin:

    ![Alt sürüme deposu için kimlik bilgilerini girme](media/version-control-subversion5.png)

8.  Kullanılabilir tüm sürüm denetim komutlarının artık sürüm denetimi menüde görünür olması gerekir.

