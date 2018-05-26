---
title: Yerel bir klasöre dağıtma
description: Yerel bir klasöre uygulama dağıtmak
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: bd477fec033eb75f626401586abfd10c798601ef
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
1. İçinde **Çözüm Gezgini**, proje düğümüne sağ tıklayın ve seçin **Yayımla** (Web formları için **Web uygulaması yayımlama**).

    Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Tıklatın **yeni bir profil**.

1. İçinde **Yayımla** iletişim kutusunda **klasörü**, tıklatın **Gözat**ve yeni bir klasör oluşturun **C:\Publish**.

    ![RemoteDBG_Publish_Local](../media/remotedbg_publish_local.png "RemoteDBG_Publish_Local")

    Web Forms uygulaması için seçin **özel** Yayımla iletişim kutusunda bir profil adı girin ve seçin **Tamam**.

1. Tıklatın **profili oluşturma** aşağı açılan listesinde (**Yayımla** varsayılan değer).

1. İçinde **Yayımla** iletişim kutusu, tıklatın **ayarları** bağlamak ve ardından **ayarları** sekmesi.

1. Yapılandırma kümesi **hata ayıklama**seçin **var olan tüm dosyaları yayımlamak için önceki silin**ve ardından **kaydetmek**.

    > [!NOTE]
    > Yayın derlemesi kullanırsanız, yayımladığınızda, web.config dosyasında hata ayıklama devre dışı.

1. Tıklatın **yayımlama**.

    ![RemoteDBG_Publish_Debug_Config](../media/remotedbg_publish_debug_config.png "RemoteDBG_Publish_Debug_Config")
    
    Uygulama yayımlayan bir **hata ayıklama** projesinin yerel klasörde yapılandırma. İlerleme durumunu çıktı penceresinde gösterir.

1. ASP.NET proje dizini, Visual Studio bilgisayardan ASP.NET uygulaması için yapılandırılan yerel dizine kopyalayın (Bu örnekte, **C:\Publish**) Windows Server bilgisayarında. Bu öğreticide, el ile kopyaladığınız ancak PowerShell, Xcopy veya Robocopy gibi diğer araçları kullanabilirsiniz varsayıyoruz.

    > [!CAUTION]
    >  Kod ya da yeniden değişiklikleri yapmanız gerekirse, yeniden yayımlamanız ve bu adımı yineleyin. Uzak makineye kopyaladığınız yürütülebilir yerel kaynağı ve simgeleri tam olarak eşleşmelidir.    Bu alırsınız yapmazsanız bir `cannot find or open the PDB file` işlemde hata ayıklamak çalıştığınızda Visual Studio'da uyarı.

1. Windows Server'da, uygulamanın doğru uygulama tarayıcınızda açarak çalıştırabilirsiniz olduğunu doğrulayın.

    Uygulamanın düzgün çalışmazsa, ASP.NET, sunucunuz ve Visual Studio makinenizin üzerinde yüklü sürüm arasında bir uyuşmazlık olabilir veya IIS veya Web sitesi yapılandırma ile ilgili bir sorun olabilir. Önceki adımlarda yeniden denetleyin.
