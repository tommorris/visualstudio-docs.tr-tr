---
title: "Linux üzerinde uzak R hizmet ayarlama | Microsoft Docs"
description: "Ubuntu ve Windows alt uzak R hizmette Linux için nasıl ayarlanacağı."
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
dev_langs:
- R
ms.tgt_pltfrm: 
ms.topic: article
author:
- kraigb
- karthiknadig
ms.author:
- kraigb
- karthiknadig
manager: ghogen
ms.workload:
- data-science
ms.openlocfilehash: 80f7f82baf194070ff3e34bcbf8776f9109c925d
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="remote-r-service-for-linux"></a>Linux için Uzak R hizmeti

Linux için Uzak R Hizmet şu anda rtvs-arka plan programı gibi paketlenmiştir. Arka plan programı desteklenen ve Ubuntu 16.04, 16.10 LTS Masaüstü, sunucu ve Windows alt sistemi üzerinde çalışan Ubuntu Linux için test edilmiştir. Bu makalede toplu uzaktan R hizmeti bu farklı sistemlerde ayarlamak için yönergeler sağlar.

Uzak makinede yapılandırdıktan sonra aşağıdaki adımları R araçları Visual Studio (RTVS için) bu hizmete bağlanabilir:

1. Seçin **R Araçlar > Windows > çalışma alanları** açmak için **çalışma alanları** penceresi.
1. Seçin **Bağlantı Ekle**.
1. Connect bir ad verin ve kendi URL sağlayın `https://localhost:5444` (Linux için Windows alt) veya `https://public-ip:5444` (Azure kapsayıcı). Seçin **kaydetmek** tamamlandığında.
1. Bağlantı simgesini seçin veya bağlantı öğesini çift tıklatın.
1. Oturum açma kimlik bilgilerini sağlayın. Kullanıcı adı ile eklenmelidir `<<unix>>\` olarak `<<unix>>\ruser1` (Linux uzak bilgisayarlara tüm bağlantılar için gerektiği gibi).
1. Kendinden imzalı bir sertifika kullanıyorsanız, bir uyarı görebilirsiniz. İleti uyarı düzeltmek için yönergeler sağlar.

## <a name="setting-up-remote-r-service"></a>Uzak R hizmet ayarlama

Bu bölümde aşağıdaki seçenekler açıklanmaktadır:

- [Fiziksel Ubuntu bilgisayar](#physical-ubuntu-computer)
- [Ubuntu Server VM veya veri bilimi Azure VM](#ubuntu-server-vm-or-data-science-vm-on-azure)
- [Yerel veya uzak Docker kapsayıcısı (temiz derleme)](#local-or-remote-docker-container-clean-build)
- [Azure kapsayıcı örnekleri üzerinde çalışan kapsayıcısı](#container-running-on-azure-container-instances)

Her durumda, uzak bilgisayarda yüklü aşağıdaki R yorumlayıcılar biri olması gerekir:

- [Microsoft R Open](https://mran.microsoft.com/open/)
- [Windows için CRAN R](https://cran.r-project.org/bin/linux/ubuntu/)

### <a name="physical-ubuntu-computer"></a>Fiziksel Ubuntu bilgisayar

1. Bilgisayara oturum sonra rtvs arka plan programı tarball indirin:

    ```bash
    wget -O rtvs-daemon.tar.gz https://aka.ms/r-remote-services-linux-binary-current
    tar -xvzf rtvs-daemon.tar.gz
    ```

1. Yükleme komut dosyasını çalıştırın:

    ```bash
    sudo ./rtvs-install
    ```

    Sessiz bir Otomasyon için kullanmak `sudo ./rtvs-install -s`.

1. Etkinleştirin ve hizmeti başlatın:

    ```bash
    sudo systemctl enable rtvsd
    sudo systemctl start rtvsd
    ```

1. SSL sertifikası (üretim için gerekli) yapılandırın. Varsayılan olarak, rtvs arka plan programı kullanır `ssl-cert-snakeoil.pem` ve `ssl-cert-snakeoil.pem` tarafından oluşturulan `ssl-cert` paket. Yükleme sırasında bunlar içinde bir araya `ssl-cert-snakeoil.pfx`. Üretim amaçları doğrultusunda, yöneticiniz tarafından sağlanan SSL sertifikası kullanın. SSL sertifikası sağlayarak yapılandırılabilir bir `.pfx` dosya ve isteğe bağlı alma Parolada: `/etc/rtvs/rtvsd.config.json`.

1. (İsteğe bağlı) Hizmetinin çalıştığını kontrol edin:

    ```bash
    ps -A -f | grep rtvsd
    ```

    Kullanıcı adı altında çalışan bir işlemi görmüyorsanız, `rtvssvc`. Başlatın aşağıdaki komutu kullanarak:

    ```bash
    sudo systemctl start rtvsd
    ```

1. Daha fazla rtvs daemon yapılandırmak için bkz: `man rtvsd`.

### <a name="ubuntu-server-vm-or-data-science-vm-on-azure"></a>Ubuntu Server VM veya veri bilimi Azure VM

#### <a name="create-a-vm"></a>Bir VM oluşturma

1. Oturum [Azure portal](https://portal.azure.com).
1. Sanal makinelere gidin ve ardından **Ekle**.
1. Kullanılabilir VM görüntülerinin listesinde aramak ve aşağıdakilerden birini seçin:
    - Ubuntu Server: `Ubuntu Server 16.04 LTS`
    - Veri bilimi VM: `Linux Data Science` (bkz [veri bilimi sanal makineleri](https://azure.microsoft.com/services/virtual-machines/data-science-virtual-machines/) Ayrıntılar için)
1. Dağıtım modeli kümesine `Resource manager` seçip **oluşturma**.
1. VM için bir ad seçin, bir kullanıcı adı ve parola sağlayın (parola gereklidir, olarak SSH ortak anahtarı oturum açma desteklenmez).
1. VM yapılandırması diğer istediğiniz değişiklikleri yapın.
1. Bir VM boyutu seçin, yapılandırmasını doğrulayın ve seçin **oluşturma**. VM oluşturulduktan sonra bir sonraki bölüme geçin.

#### <a name="configure-the-vm"></a>VM yapılandırma

1. VM içinde **ağ** bölümünde, 5444 izin verilen gelen bağlantı noktası ekleyin. Farklı bir bağlantı noktasını kullanacak biçimde RTVS arka plan programı config dosyasına ayarını (`/etc/rtvs/rtvsd.config.json`).
1. (İsteğe bağlı) Bir DNS adı ayarlayın; IP adresini de kullanabilirsiniz.
1. WIndows için PuTTY gibi bir SSH istemcisi kullanarak VM bağlayın.
1. Yönergeleri izleyin bir [fiziksel Ubuntu bilgisayar](#physical-ubuntu-computer) üstünde.

### <a name="windows-subsystem-for-linux-wsl"></a>Linux (WSL) için Windows alt sistem

1. Ya da WSL yükleme yönergelerini izleyin [Windows 10](https://msdn.microsoft.com/commandline/wsl/install-win10) veya [Windows Server](https://msdn.microsoft.com/en-us/commandline/wsl/install-on-server).
1. Windows bash'i başlatın ve önceki yönergeleri izleyerek bir [fiziksel Ubuntu bilgisayar](#physical-ubuntu-computer) bir özel durum oluştu. Adım 3 komutunu kullanarak hizmeti başlatmak `rtvsd`yerine WSL systemd/systemctl arabirimleri şu anda desteklemediği için.

### <a name="local-or-remote-docker-container-clean-build"></a>Yerel veya uzak Docker kapsayıcısı (temiz derleme)

1. Uzak R hizmeti arka plan programı ve r en son sürümünü yükleyen aşağıdaki içeriği Docker dosya oluştur **Not**: Bu komut dosyası içinde istediğiniz gibi değiştirebilirsiniz "foobar" parolayla "ruser1" adlı bir kullanıcı oluşturur Son iki `RUN` deyimleri.

    ```docker
    FROM ubuntu:16.04

    ARG DEBIAN_FRONTEND=noninteractive

    RUN apt-get update \
     && apt-get install -y software-properties-common python-software-properties \
     && apt-get install -y apt-transport-https \
     && rm -rf /var/lib/apt/lists/*

    RUN sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' \
     && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 417A0893 \
     && sh -c 'echo "deb https://cran.revolutionanalytics.com/bin/linux/ubuntu xenial/" > /etc/apt/sources.list.d/cran-r.list' \
     && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9 \
     && rm -rf /var/lib/apt/lists/* \
     && apt-get clean

    RUN apt-get update --fix-missing && apt-get update \
     && apt-get install -y dotnet-dev-1.0.4 libexplain51 libzip4 libc6 git lshw ssl-cert wget \
     && rm -rf /var/lib/apt/lists/*

    # install R
    RUN apt-get update && apt-get install -y r-base-dev
    RUN apt upgrade -y

    # install rtvs-daemon
    RUN wget -O rtvs-daemon.tar.gz https://aka.ms/r-remote-services-linux-binary-current && tar -xvzf rtvs-daemon.tar.gz && ./rtvs-install -s

    RUN useradd --create-home ruser1
    RUN echo "ruser1:foobar" | chpasswd

    EXPOSE 5444
    ```

1. Derleme ve docker dosyasını çalıştırın:

    ```bash
    docker build -t myrimage .
    docker run -p 5444:5444 myrimage rtvsd
    ```

1. Bağlanmak için kullanım RTVS içeren `https://localhost:5444` yolu, kullanıcı adı olarak `<<unix>>\ruser1`ve parola `foobar`. Kapsayıcı uzak bir bilgisayarda çalışıyorsa, kullanın `https://remote-host-name:5444` yolu olarak bunun yerine. Bağlantı noktası güncelleştirerek değiştirilebilir `/etc/rtvs/rtvsd.config.json`.

### <a name="container-running-on-azure-container-instances"></a>Azure kapsayıcı örnekleri üzerinde çalışan kapsayıcısı

1. ' Ndaki yönergeleri izleyin [yerel veya uzak Docker kapsayıcısı (temiz derleme)](#local-or-remote-docker-container-clean-build) görüntüsü oluşturulamadı.
1. Kapsayıcı, Docker hub'a veya Azure kapsayıcı deposuna iletin.
1. Azure CLI başlatın ve oturum `az login` komutu.
1. Kullanım `az container create` kapsayıcı oluşturmak için komutu kullanarak `--command-line "rtvsd"` çalıştırmak için kapsayıcısı ayarlama ayarlamadıysanız `rtvsd` olarak bir `systemd` hizmet. Aşağıdaki komutu görüntü Docker hub'ına olması beklenir. Azure kapsayıcı deposuna kapsayıcı depo kimlik bilgisi bağımsız değişken komut satırına ekleyerek de kullanabilirsiniz.

    ```bash
    az container create --image myimage:latest --name myaz-container --resource-group myaz-container-res --ip-address public --port 5444 --cpu 2 --memory 4 --command-line "rtvsd"
    ```
1. Kullanım `az container list` durumunu denetlemek için komutu. Ara `provisioningState`: `Succeeded`.
1. Sağlama işlemi başarılı olursa, şimdi kapsayıcıya bağlanabilirsiniz. Ortak IP adresi olarak arayın `ipAddress` docker dosyasındaki kimlik bilgileriyle kapsayıcıya RTVS bağlanmak için kullandığınız alan.

