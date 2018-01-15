---
title: "Visual Studio için R araçları ile uzak çalışma alanları | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: data-science
ms.openlocfilehash: 45b12e0e6d9c26cd6fa13c1398e983087ee375e1
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2018
---
# <a name="setting-up-remote-workspaces"></a>Uzak çalışma alanları ayarlama

Bu konu, uzak sunucu SSL ve uygun bir R hizmeti ile nasıl yapılandırılacağını açıklar. Bu, R araçları için Visual Studio (sunucu üzerindeki uzak bir çalışma alanına bağlanmak için RTVS) sağlar.

- [Uzak bilgisayar gereksinimleri](#remote-computer-requirements)
- [Bir SSL sertifikası yükleme](#install-an-ssl-certificate)
- [Windows üzerinde bir SSL sertifikası yükleme](#install-an-ssl-certificate-on-windows)
- [Ubuntu üzerinde bir SSL sertifikası yükleme](#install-an-ssl-certificate-on-ubuntu)
- [Windows üzerinde R hizmetlerini yükleyin](#install-r-services-on-windows)
- [Linux'ta R hizmetlerini yükleme](#install-r-services-on-Linux)
- [R hizmetlerini yapılandırma](#configure-r-services)
- [Sorun giderme](#troubleshooting)

## <a name="remote-computer-requirements"></a>Uzak bilgisayar gereksinimleri

- Windows 10, Windows Server 2016 veya Windows Server 2012 R2. RTVS de gerektirir
- [.NET framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) veya daha büyük

## <a name="install-an-ssl-certificate"></a>Bir SSL sertifikası yükleme

Sunucu üzerindeki bir SSL sertifikası gerektirir HTTP üzerinden uzak bir sunucu ile tüm iletişimler olur RTVS gerektirir. (Önerilen) güvenilir bir sertifika yetkilisi tarafından imzalanmış bir sertifika ya da kendinden imzalı bir sertifika kullanabilirsiniz. (Otomatik olarak imzalanan bir sertifika bağlıyken sorunu uyarıları RTVS neden olur). Herhangi biriyle, ardından bilgisayara yükleyin ve özel anahtarını erişmesine izin vermek ihtiyacınız var.

### <a name="obtaining-a-trusted-certificate"></a>Güvenilen bir sertifika edinme

Güvenilen bir sertifika bir sertifika yetkilisi tarafından verilen (bkz [sertifika yetkilileri wikipedia'da](https://en.wikipedia.org/wiki/Certificate_authority) arka planı için). Kamu kimlik kartı alma gibi güvenilir bir sertifika, daha fazla işlem ve olası ücretleri içerir ancak istek ve istek sahibinin özgünlüğünü doğrular.

Sertifikada olması gereken anahtar alanı R server bilgisayarınızın tam etki alanı adıdır. Sertifika yetkilisi etki alanı için yeni bir sunucu oluşturma yetkiniz kanıt gerektirir, sunucunun ait olduğu için.

Daha fazla arka plan için bkz: [ortak anahtar sertifikaları](https://en.wikipedia.org/wiki/Public_key_certificate) wikipedia'da.

## <a name="install-an-ssl-certificate-on-windows"></a>Windows üzerinde bir SSL sertifikası yükleme

SSL sertifikası windows elle yüklenmesi gerekir. Bir SSL sertifikası yüklemek için aşağıdaki yönergeleri izleyin.

### <a name="obtaining-a-self-signed-certificate-windows"></a>(Windows) otomatik olarak imzalanan sertifika edinme

Güvenilen bir sertifika varsa bu bölüm atlayın. Güvenilir bir yetkili bir sertifika ile karşılaştırıldığında, kendinden imzalı bir sertifika bir kimlik kartı kendiniz oluşturmak kadar kolaydır. Bu işlem, kuşkusuz güvenilir bir yetkili ile çalışmayı daha çok daha basit olduğu ancak güçlü kimlik doğrulaması, bir saldırgan, kendi sertifika imzasız sertifika için yedek ve istemci arasındaki tüm trafiği yakalama anlamına da eksik ve Sunucu. Bu nedenle, *yalnızca senaryoları, güvenilen bir ağa ve hiçbir zaman üretimde test etmek için otomatik olarak imzalanan sertifika kullanılmalıdır.*

Bu nedenle, RTVS her zaman otomatik olarak imzalanan bir sertifika sahip bir sunucuya bağlanırken aşağıdaki uyarı verir:

![Kendinden imzalı bir sertifika Uyarısı iletişim kutusu](media/workspaces-remote-self-signed-certificate-warning.png)

Otomatik olarak imzalanan bir sertifika vermek için:

1. R sunucu bilgisayara bir yönetici hesabı kullanarak oturum açın.
1. Yeni bir yönetici PowerShell komut istemi açın ve aşağıdaki sorunu komutu, değiştirme `"remote-machine-name"` server bilgisayarınızın tam etki alanı adı.

    ```ps
    New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "remote-machine-name"
    ```

1. R server bilgisayarda Powershell önce hiçbir zaman çalıştırdıysanız, komutların açıkça çalışmasını etkinleştirmek için aşağıdaki komutu çalıştırın:

    ```ps
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
    ```

Arka plan için bkz: [otomatik olarak imzalanan sertifikalar](https://en.wikipedia.org/wiki/Self-signed_certificate) wikipedia'da.

### <a name="installing-the-certificate"></a>Sertifikayı yükleme

Uzak bilgisayarda sertifika yüklemek için `certlm.msc` (Sertifika Yöneticisi) bir komut isteminden. Sağ tıklayın **kişisel** klasörü ve select **tüm görevler > içeri aktarma** komutu:

![İçeri aktarma sertifika komutu](media/workspaces-remote-certificate-import.png)

### <a name="granting-permissions-to-read-the-ssl-certificates-private-key"></a>SSL sertifikasının özel anahtarının okuma izni verme

Sertifika içeri aktarıldığında vermek `NETWORK SERVICE` hesap özel anahtarı aşağıdaki yönergelerde açıklandığı gibi okuma izni. `NETWORK_SERVICE`Hesap, sunucu bilgisayara gelen SSL bağlantılarını sonlandırır hizmet R Hizmetleri Aracısı çalıştırmak için kullanılır.

1. Çalıştırma `certlm.msc` (Sertifika Yöneticisi) bir yönetici komut isteminden.
1. Genişletme **kişisel > sertifikaları**sertifikanızı sağ tıklatın ve seçin **tüm görevler > özel anahtarları Yönet**.
1. Sertifikayı sağ tıklatın ve özel anahtarları Yönet komutu tüm görevler'in altında seçin
1. Görüntülenen iletişim kutusunda, seçin **Ekle** ve girin `NETWORK SERVICE` hesap adı olarak:

    ![Özel anahtarlar iletişim network_servıce ekleme, yönetme](media/workspaces-remote-manage-private-key-dialog.png)

1. Seçin **Tamam** iki kez iletişimi kapatın ve değişikliklerinizi uygulamak için.

## <a name="install-an-ssl-certificate-on-ubuntu"></a>Ubuntu üzerinde bir SSL sertifikası yükleme

`rtvs-daemon` Paket yükleme otomatik olarak imzalanan bir sertifika varsayılan yüklemesinin bir parçası olarak.

### <a name="obtaining-a-self-signed-certificate-ubuntu"></a>Kendinden imzalı bir sertifika (Ubuntu) alma

Faydaları ve otomatik olarak imzalanan sertifika kullanarak riskleri için windows açıklamasına bakın. `rtvs-daemon` Paket oluşturur ve yükleme sırasında otomatik olarak imzalanan sertifika yapılandırır. Yalnızca otomatik olarak oluşturulan otomatik olarak imzalanan sertifikayı değiştirmek istiyorsanız bunu yapmak gerekir.

Kendi vermek için sertifika kendiniz imzalanmış:

1. SSH veya linux makinenizi oturum açın.
1. Yükleme `ssl-cert` paketi:
    ```sh
    sudo apt-get install ssl-cert
    ```
1. Çalıştırma `make-ssl-cert` varsayılan otomatik olarak imzalanan SSL sertifikasını oluşturmak için:
    ```sh
    sudo make-ssl-cert generate-default-snakeoil --force-overwrite
    ```
1. PEM dosyaları ve oluşturulan anahtarı için PFX dönüştürün. Oluşturulan PFX giriş klasörünüzde olmalıdır:
    ```sh
    openssl pkcs12 -export -out ~/ssl-cert-snakeoil.pfx -inkey /etc/ssl/private/ssl-cert-snakeoil.key -in /etc/ssl/certs/ssl-cert-snakeoil.pem -password pass:SnakeOil
    ```

### <a name="configuring-rtvs-daemon"></a>RTVS arka plan programı yapılandırma

SSL sertifika dosyası yolu (PFX yoluna) ayarlanmalıdır `/etc/rtvs/rtvsd.config.json`. Güncelleştirme `X509CertificateFile` ve `X509CertificatePassword` dosya yolu ve parola ile sırasıyla.

```json
{
  "logging": { "logFolder": "/tmp" },
  "security": {
    "allowedGroup": "",
    "X509CertificateFile": "/etc/rtvs/ssl-cert-snakeoil.pfx",
    "X509CertificatePassword": "SnakeOil"
  },
  "startup": { "name": "rtvsd" },
  "urls": "https://0.0.0.0:5444"
}
```

Dosyayı kaydedin ve arka plan programı, yeniden `sudo systemctl restart rtvsd`.

## <a name="install-r-services-on-windows"></a>Windows üzerinde R hizmetlerini yükleyin

R kodu çalıştırmak için uzak bilgisayarda bir R yorumlayıcı gibi yüklü olması gerekir:

1. Karşıdan yüklemek ve aşağıdakilerden birini yükleyin:

    - [Microsoft R Aç](https://mran.microsoft.com/open/)
    - [Windows için CRAN R](https://cran.r-project.org/bin/windows/base/)

    Her ikisi de aynı işlevselliğe sahiptir, ancak ek donanım Microsoft R açık avantajları hızlandırılmış Lineer Cebir kitaplıklarının courtesy [Intel Math çekirdek Kitaplığı](https://software.intel.com/intel-mkl).

1. Çalıştırma [R Services yükleyici](https://aka.ms/rtvs-services) ve istendiğinde yeniden başlatın. Yükleyici aşağıdakileri yapar:

    - Bir klasör oluşturun `%PROGRAMFILES%\R Tools for Visual Studio\1.0\` ve tüm gerekli ikili dosyaları kopyalayın.
    - Yükleme `RHostBrokerService` ve `RUserProfileService` ve otomatik olarak başlayacak şekilde yapılandırın.
    - Yapılandırma `seclogon` hizmetini otomatik olarak başlatılacak şekilde.
    - Ekleme `Microsoft.R.Host.exe` ve `Microsoft.R.Host.Broker.exe` Güvenlik Duvarı'na gelen kuralları varsayılan bağlantı noktası 5444.

Bilgisayar yeniden başlatıldığında R hizmetleri otomatik olarak Başlat:

- **R konak Aracısı hizmeti** R kodu bilgisayar üzerinde çalıştığı işlem ile Visual Studio arasındaki tüm HTTPS trafiğini işler.
- **R kullanıcı profili hizmeti** , Windows kullanıcı profili oluşturma işleme ayrıcalıklı bir bileşenidir. Yeni bir kullanıcı ilk R server bilgisayara oturum açtığında hizmet adı verilir.

Bu hizmetler services yönetim konsolunda görebilirsiniz (`compmgmt.msc`).

## <a name="install-r-services-on-linux"></a>Linux'ta R hizmetlerini yükleme

R kodu çalıştırmak için uzak bilgisayarda bir R yorumlayıcı gibi yüklü olması gerekir:

1. Karşıdan yüklemek ve aşağıdakilerden birini yükleyin:

    - [Microsoft R Aç](https://mran.microsoft.com/open/)
    - [Windows için CRAN R](https://cran.r-project.org/bin/linux/ubuntu/)

    Her ikisi de aynı işlevselliğe sahiptir, ancak ek donanım Microsoft R açık avantajları hızlandırılmış Lineer Cebir kitaplıklarının courtesy [Intel Math çekirdek Kitaplığı](https://software.intel.com/intel-mkl).

1. Yönergeleri izleyerek [Linux uzak R Hizmeti'ni](workspaces-remote-r-service-for-linux.md), fiziksel Ubuntu bilgisayarları, Azure Ubuntu VM, Windows Subsystem for Linux (WSL) ve Azure kapsayıcı deposuna üzerinde çalışan dahil olmak üzere, Docker kapsayıcı kapsar.

## <a name="configure-r-services"></a>R hizmetlerini yapılandırma

Uzak bilgisayarda çalışan R Hizmetleri ile Ayrıca kullanıcı hesapları oluşturmak için güvenlik duvarı kuralları ayarlamak, Azure ağı yapılandırma ve SSL sertifikası yapılandırma.

1. Kullanıcı hesapları: uzak bilgisayarda erişen her kullanıcı için hesapları oluşturun. Her iki standart (ayrıcalıklı olmayan) yerel kullanıcı hesaplarını oluşturabilir veya R server bilgisayarınızın etki alanınıza ekleyin ve uygun güvenlik gruplarına ekleme `Users` güvenlik grubu.

1. Güvenlik duvarı kuralları: varsayılan olarak, `R Host Broker` 5444 numaralı TCP bağlantı noktasını dinler. Bu nedenle, Windows Güvenlik duvarı kurallarının gelen ve giden trafik için etkinleştirilmiş olduğundan emin olun (giden paketler ve benzer senaryoları yüklemek için gerekli değildir).  R Hizmetleri yükleyicisi bu kurallar yerleşik Windows Güvenlik Duvarı için otomatik olarak ayarlar. Ancak, bir üçüncü taraf güvenlik duvarı kullanıyorsanız, bağlantı noktası 5444 için'ni açın `R Host Broker` el ile.

1. Azure yapılandırma: Azure sanal makinede uzak bilgisayarın olması durumunda bağlantı noktası 5444 gelen trafik için de, Windows Güvenlik duvarını bağımsız olarak Azure ağ içinde açın. Ayrıntılar için bkz [filtre ağ güvenlik grubu ile ağ trafiği](https://docs.microsoft.com/azure/virtual-network/virtual-networks-nsg) Azure belgelerinde.

1. R konak Aracısı'nı yüklemek için hangi SSL sertifikası söyleyin: sertifikanın bir Intranet sunucusunda yüklüyorsanız, sunucunuzun tam etki alanı adı NetBIOS adıyla aynı olduğundan emin olabilir. Bu durumda, bir şey yok Bu yüklenen varsayılan sertifika olduğu gibi gerçekleştirmeniz gereken.

    Ancak, sertifikanızı (örneğin, bir Azure VM) bir Internet'e yönelik sunucuda yüklüyorsanız, Internet'e yönelik sunucusunun FQDN'sini hiçbir zaman NetBIOS adıyla aynı olduğundan sunucunuzun tam etki alanı adını (FQDN) kullanın.

    FQDN kullandığınız, R Hizmetleri yüklendiği gidin (`%PROGRAM FILES%\R Remote Service for Visual Studio\1.0` varsayılan olarak), açık `Microsoft.R.Host.Broker.Config.json` dosyasını bir metin düzenleyicisinde açın ve içeriği ne olursa olsun, sunucunuzun FQDN, olduğu gibi kullanıcının için aşağıdaki, atama CN değiştirin `foo.westus.cloudapp.azure.com`:

    ```json
    {
      "server.urls": "https://0.0.0.0:5444",
      "security": {
        "X509CertificateName": "CN=your-server-fully-qualified-domain-name"
      }
    }
    ```

    Dosyayı kaydedin ve değişikliklerin uygulanması için bilgisayarı yeniden başlatın.

## <a name="troubleshooting"></a>Sorun giderme

**R server bilgisayarı yanıt vermiyor, ne yapmalıyım?**

Komut satırından uzak bilgisayara ping işlemi yapmayı deneyin: `ping remote-machine-name`. Ping başarısız olursa, bilgisayarı çalıştığından emin olun.

**Q. R etkileşimli penceresini uzak bilgisayar açık, ancak neden hizmeti çalışmıyor görünüyor?**

Üç olası nedenler şunlardır:

- [.NET framework 4.6.1](https://www.microsoft.com/download/details.aspx?id=49981) veya daha fazla bilgisayarda yüklü değil.
- Güvenlik duvarı kurallarını `Microsoft.R.Host.Broker` ve `Microsoft.R.Host` 5444 bağlantı noktasından gelen ve giden bağlantıları için etkin değil.
- Bir SSL sertifikası ile `CN=<remote-machine-name>` yüklü değil.

Yukarıdaki değişiklikleri yaptıktan sonra bilgisayarı yeniden başlatın. Ardından olduğundan emin olun `RHostBrokerService` ve `RUserProfileService` ya da Görev Yöneticisi (Hizmetleri sekmesi) üzerinden çalışan veya `services.msc`.

**Q. Neden R etkileşimli pencere, R sunucusuna bağlanırken "401 Erişim engellendi" dediği?**

İki olası nedeni vardır:

- Yüksek oranda olasıdır, `NETWORK SERVICE` hesap SSL sertifikası özel anahtarına erişime sahip değil. Vermek için önceki yönergeleri `NETWORK SERVICE` özel anahtara erişim.
- Olduğundan emin olun `seclogon` hizmetinin çalıştığından. Kullanım `services.msc` yapılandırmak için `seclogon` otomatik olarak başlatılacak.

**Q. Neden R etkileşimli pencere, R sunucusuna bağlanırken "404 bulunamadı" dediği?**

Bu hata muhtemelen Visual C++ yeniden dağıtılabilir kitaplıkları nedeniyle eksik. Eksik library(DLL) ilgili bir ileti olup olmadığını görmek için R etkileşimli penceresini denetleyin. Ardından VS 2015 redistributable yüklenir ve de yüklü R olduğunu denetleyin.

**Q. I erişemiyor Internet/kaynak R etkileşimli penceresinden, ne yapmalıyım?**

Güvenlik Duvarı için kuralları olun `Microsoft.R.Host.Broker` ve `Microsoft.R.Host` 5444 bağlantı noktasında giden erişim izni. Değişiklikler uygulandıktan sonra bilgisayarı yeniden başlatın.

**Q. Bu çözümlerin çalışmış olabilirsiniz ve hala çalışmamaktadır. Şimdi ne yapmalıyım?**

Günlük dosyalarına bakın `C:\Windows\ServiceProfiles\NetworkService\AppData\Local\Temp`. Bu klasör çalıştırıldığı R Aracısı hizmetini her örneği için farklı günlük dosyaları içerir. Hizmet yeniden başlatıldığında yeni bir günlük dosyası oluşturulur. Yanlış neler hakkında ipuçları için en son günlük dosyasını denetleyin.
