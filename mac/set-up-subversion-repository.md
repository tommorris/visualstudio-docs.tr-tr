---
title: "Mac için Visual Studio'da bir alt sürüme deposu ayarlama | Microsoft Docs"
description: "Git ve alt sürüme Mac için Visual Studio kullanarak"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 0D58FB37-530E-495B-BED6-FD499477A9B6
ms.openlocfilehash: 0757ad29b8614a86f059f525f6ffe3100595d09b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="setting-up-a-subversion-repository"></a>Bir alt sürüme deposu ayarlama

Alt sürüme merkezi sürüm denetim sistemidir. Bu, tüm dosyaları ve kullanıcıların herhangi bir dosyayı herhangi bir sürümü denetleyebilirsiniz düzeltmelerini içeren tek bir sunucu olduğu anlamına gelir. Dosyalar bir uzak alt sürüme depodan kullanıma, kullanıcı bir anlık görüntü depo zamandaki o noktada alır.

Doğru svn paketleri içerirler gibi alt sürüme kullanmaya başlamadan önce Xcode komut satırı araçları yüklü olması gerekir. SVN aşağıdaki komutla terminale yüklü olduğunu denetleyebilirsiniz:

`svn h`

1. Bir ücretsiz SVN deposu oluşturun. Bu örnek için [Assembla](https://app.assembla.com/) kullanıldı. Oluşturduktan sonra bir URL sağlanacaktır, hangi depoya bağlanmak için kullanılacak: 

    ![SVN URL'si edinin ve kopyalama](media/version-control-subversion1-sml.png)

2. Visual Studio için Mac projesi oluşturun veya açın.

3. Sağ tıklayın proje ve select **sürüm denetimi > Sürüm denetimi Yayımla...** : 

    ![Proje Yayımlama Başlat](media/version-control-subversion2.png)

4. İçinde **depo Bağlan** sekmesine **alt sürüme** üst açılır.

5. Adım 1'den URL'sini girin. Bu, varsayılan olarak diğer alanları doldurmanız gerekir: 

    ![Depo seçin ve iletişim ayrıntılarını girin](media/version-control-subversion3.png)

7. Tıklatın **Tamam** ve tuşlarına basarak onaylayın **Yayımla**.

7. Depo oluşturun site için kimlik bilgilerinizi girmeniz istenebilir. Bunlar, aşağıda gösterildiği gibi girin:

    ![](media/version-control-subversion5.png)

8.  Kullanılabilir tüm sürüm denetim komutlarının artık sürüm denetimi menüde görünür olması gerekir.

