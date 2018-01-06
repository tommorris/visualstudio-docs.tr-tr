---
title: "Visual Studio ve Docker kapsayıcıları için R araçları | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author:
- kraigb
- karthiknadig
ms.author:
- kraigb
- karthiknadig
manager: ghogen
ms.workload: data-science
ms.openlocfilehash: 45bfebe905b9cae502247fbd0b46d9b856fb2fea
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="using-docker-containers-with-r-tools-for-visual-studio"></a>Docker kapsayıcıları R araçları ile Visual Studio için kullanma

R sürümüne yönelik araçları Visual Studio (RTVS) 1.3 + yüklemenin yanı sıra [Windows için Docker](https://www.docker.com/docker-windows), Docker kapsayıcılarını ile çalışmayı destekler.

- [Bir kapsayıcı oluşturma](#creating-a-container)
- [Bir kapsayıcıya bağlanma](#connecting-to-a-container)
- [Özel olarak geliştirilmiş görüntüleri kullanma](#using-custom-built-images)

## <a name="creating-a-container"></a>Kapsayıcı oluşturma

1. Seçin **kapsayıcıları...**  sağ köşesinde düğmesinde **çalışma alanları** penceresi (**R Araçlar > Windows > çalışma alanları**). Ürününe sahip değilseniz, pencerenin Windows için Docker yüklü ve yükleme için bir bağlantı sağlar bildirir. Docker yüklenmesi bilgisayarın yeniden başlatılmasını gerektirebilir.

    ![R araçları Visual Studio (VS2017) için çalışma alanları penceresinde kapsayıcıları komutuyla](media/container-workspaces-window.png)

1. İçinde **kapsayıcıları** penceresinde, seçin **oluşturma**:

    ![Kapsayıcıları penceresinde komutu oluşturun](media/containers-window-create.png)

1. Seçin ve iletişim gerekli bilgileri tamamlayın **oluşturma**. Girdiğiniz kimlik bilgileri ile daha sonra oturum Linux üzerinde bir hesap oluşturmak için de kullanılır.

    ![Bir kapsayıcı oluşturma sırasında bir kapsayıcı adı ve kimlik bilgilerini girme](media/containers-window-create-fill.png)

1. Görüntü oluşturmak RTVS biraz zaman alabilir. **Çıkış** Visual Studio'daki gösterir ilerleme, ancak çok uzun görüntü sırasında yapmamanın gibi görünebilir yükler; endişelenmeyin hazırlıklı olun. Görüntü yerleşik sonra RTVS kapsayıcı başlatır ve görünür **kapsayıcı** penceresi. Doğru Durma denetimlere kaldırın veya kapsayıcı yeniden başlatın.

    ![Tamamlanmış bir kapsayıcı gösteren kapsayıcıları penceresi](media/containers-window-created.png)

## <a name="connecting-to-a-container"></a>Bir kapsayıcıya bağlanma

1. **Yerel çalışan kapsayıcılar** bölümünü **çalışma alanları** penceresinde kapsayıcıları 5444 bağlantı noktasında RTVS arka plan programı çalışmıyor. (Bkz [uzak R Server Linux için](workspaces-remote-r-service-for-linux.md) arka plan programı nasıl yapılandırılacağı ile ilgili ayrıntılar için.)

    ![Çalışma alanları penceresi gösteren kullanılabilir kapsayıcıları](media/workspaces-window-running-containers.png)

1. Bir kapsayıcıya bağlanmak için kapsayıcı adına çift tıklayın veya Sağdakiyle İleri okunu seçin. Bağlandığınızda, gördüğünüz bir **R etkileşimli** penceresi (bkz [R etkileşimli penceresiyle çalışma](interactive-repl.md)):

    ![Çalışma alanları ve REPL penceresinde için bir kapsayıcı açılmış](media/workspaces-window-container-connected.png)

## <a name="using-custom-built-images"></a>Özel olarak geliştirilmiş görüntüleri kullanma

RTVS algılar ve microsoft/rtvs görüntünün docker dosyasında açıklandığı gibi özel olarak geliştirilmiş görüntüleri kullanılarak oluşturulan kapsayıcıları yönetilmesine izin verir. Burada kullanılan temel görüntü rtvs arka plan programı, R 3.4.2 ve önceden yüklenmiş ortak R paketleri vardır. **Not**: kullanıcı adı ve gerektiğinde burada gösterilen parolasını değiştirin.

```docker
FROM microsoft/rtvs:1.3-ub1604-r3.4.2
RUN useradd --create-home ruser1
RUN echo "ruser1:foobar" | chpasswd

#Install additional R packages. You may have to install OS dependencies, see package info or error messages during build.
#RUN Rscript --vanilla -e "install.packages(c('AzureML','wordcloud'), repos = 'http://cran.us.r-project.org');"
```

Kapsayıcı adının değiştirilmesi bir görüntü oluşturmak için aşağıdaki komutu kullanın ( `--name` bağımsız değişkeni) istenen şekilde:

```bash
docker build -t my-rtvs-image:latest .
docker run -p 6056:5444 --name my-rtvs-container my-rtvs-image:latest rtvsd
```

`-p 6056:5444` Bağımsız değişken eşlemeleri rtvs arka plan programı algılamak için RTVS kullanan 6056 oluşturun iç bağlantı noktasına 5444, bağlantı noktası. Kapsayıcı bağlantı noktası 5444 sunan herhangi bir kapsayıcısına listelenen **çalışma alanları** penceresi. Daha sonra **çalışma alanları** kullanarak bir kapsayıcı bağlanmak için pencere `<<unix>>\ruser1` kullanıcı adı ve parola olarak "foobar" olarak docker dosyasında farklı kimlik bilgileri belirtilmediği sürece.
