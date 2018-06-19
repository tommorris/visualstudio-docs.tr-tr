---
title: Uzak Linux bilgisayarlarda Python kodda hata ayıklama
description: Visual Studio uzaktan Linux bilgisayarlar üzerinde çalışan, gerekli yapılandırma adımları, güvenlik dahil olmak üzere ve sorun giderme Python kodda hata ayıklama için nasıl kullanılacağını.
ms.date: 07/12/2017
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 1a5a4f5b0400c4bf3896e2d1c1ec7ec3e8664d31
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31582819"
---
# <a name="remotely-debugging-python-code-on-linux"></a>Uzaktan hata ayıklama Linux'ta Python kodu

Visual Studio'yu başlatın ve Python uygulamaları bir Windows bilgisayarda yerel olarak ve uzaktan hata ayıklama (bkz [uzaktan hata ayıklama](../debugger/remote-debugging.md)). Bu da uzaktan farklı işletim sistemi, cihaz veya Python uygulaması CPython kullanma dışındaki ayıklayabilirsiniz [ptvsd Kitaplığı](https://pypi.python.org/pypi/ptvsd).

Ptvsd kullanırken, Visual Studio ekleyebilir miyim hata ayıklama sunucu ayıklanacak Python kodu barındırır. Bu barındırma kodunuzu almak ve sunucu etkinleştirme ve ağ gerektirir veya yapılandırmaları TCP bağlantılara izin vermek için uzak bilgisayarda güvenlik duvarı için küçük bir değişiklik gerektirir.

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | Uzaktan hata ayıklama için giriş için bkz [derinlemesine: platformlar arası uzaktan hata ayıklama](https://youtu.be/y1Qq7BrV6Cc) (youtube.com, 6m22s), Visual Studio 2015 ve 2017 için geçerli olduğu. |

## <a name="setting-up-a-linux-computer"></a>Bir Linux bilgisayar ayarlama

Aşağıdaki öğeler bu kılavuzda izlemek için gereklidir:

- Python Mac OSX ya da Linux gibi bir işletim sistemi çalıştıran bir uzak bilgisayar.
- Bağlantı noktası 5678 (uzaktan hata ayıklama için varsayılan olan, bu bilgisayarın güvenlik duvarında açılan gelen).

Kolayca [Linux sanal makineleri Azure üzerinde](/azure/virtual-machines/linux/creation-choices) ve [Uzak Masaüstü kullanarak erişim](/azure/virtual-machines/linux/use-remote-desktop) Windows. Bir Ubuntu VM için uygun olduğundan Python varsayılan olarak yüklenir; Aksi takdirde, üzerinde listesine bakın [tercih ettiğiniz bir Python yorumlayıcısı yüklemek](installing-python-interpreters.md) ek Python karşıdan yükleme konumları için.

Bir Azure VM için bir güvenlik duvarı kuralı oluşturma hakkında daha fazla bilgi için bkz: [Azure portal kullanarak Azure'da bir VM için bağlantı noktaları açma](/azure/virtual-machines/windows/nsg-quickstart-portal).

## <a name="preparing-the-script-for-debugging"></a>Komut dosyası hata ayıklama için hazırlanıyor

1. Uzak bilgisayarda adlı bir Python dosyası oluşturun `guessing-game.py` aşağıdaki kod ile:

    ```python
    import random

    guesses_made = 0
    name = input('Hello! What is your name?\n')
    number = random.randint(1, 20)
    print('Well, {0}, I am thinking of a number between 1 and 20.'.format(name))

    while guesses_made < 6:
        guess = int(input('Take a guess: '))
        guesses_made += 1
        if guess < number:
            print('Your guess is too low.')
        if guess > number:
            print('Your guess is too high.')
        if guess == number:
            break
    if guess == number:
        print('Good job, {0}! You guessed my number in {1} guesses!'.format(name, guesses_made))
    else:
        print('Nope. The number I was thinking of was {0}'.format(number))
    ```

1. Yükleme `ptvsd` ortam kullanarak paket `pip3 install ptvsd`. (Not: sorun giderme için; gerektiğinde yüklediğiniz ptvsd sürümü kaydetmek için iyi bir fikirdir [ptvsd listeleme](https://pypi.python.org/pypi/ptvsd) kullanılabilir sürümleri de gösterir.)

1. En erken olası noktada aşağıdaki kodu ekleyerek uzaktan hata ayıklamayı etkinleştirme `guessing-game.py`, önce başka bir kod. (Kesin bir gereklilik de, önce kökenli herhangi bir arka plan iş parçacıkları hata ayıklamak mümkün değildir `enable_attach` işlevi çağrıldığında.)

   ```python
   import ptvsd
   ptvsd.enable_attach('my_secret')
   ```

   Geçirilen ilk bağımsız değişken `enable_attach` ("gizli" olarak adlandırılır) çalışan komut dosyasına erişimi kısıtlayan ve uzaktan hata ayıklayıcı eklerken bu parolayı girin. (Önerilmez ancak herkes bağlanma, kullanmak izin verebilir `enable_attach(secret=None)`.)

1. Dosyayı kaydedin ve Çalıştır `python3 guessing-game.py`. Çağrı `enable_attach` arka planda çalışır ve aksi durumda programla etkileşimli olarak gelen bağlantılar için bekler. İsterseniz, `wait_for_attach` işlevi, sonra çağrılamaz `enable_attach` hata ayıklayıcı ekler kadar programı engelleyecek.

> [!Tip]
> Ek olarak `enable_attach` ve `wait_for_attach`, ptvsd de yardımcı bir işlev sağlar `break_into_debugger`, hata ayıklayıcı bağlıysa programlı bir kesme noktası hizmet. Ayrıca bir `is_attached` döndüren bir işlev `True` hata ayıklayıcısı ekli varsa (diğer çağırmadan önce bu sonucu denetlemek için gerekli olduğuna dikkat edin `ptvsd` işlevleri).

## <a name="attaching-remotely-from-python-tools"></a>Python Araçları'ndan uzaktan ekleme

Bu adımlarda, uzak işlemi durdurmak için basit bir kesme noktası ayarlayın.

1. Yerel bilgisayarda Uzak dosyanın bir kopyasını oluşturun ve Visual Studio'da açın. Burada dosya bulunur, ancak uzak bilgisayardaki komut dosyasının adını adıyla eşleşmelidir önemli değildir.

1. (İsteğe bağlı) Yerel bilgisayarınızda ptvsd için IntelliSense sağlamak için Python ortamınıza ptvsd paketini yükleyin.

1. Seçin **hata ayıklama > işleme iliştirilemiyor**.

1. İçinde **ekleme işlemi için** görünür, iletişim ayarlayın **bağlantı türü** için **Python uzaktan (ptvsd)**. (Daha eski Visual Studio sürümlerinde bu komutları adlı **aktarım** ve **Python uzaktan hata ayıklama**.)

1. İçinde **bağlantı hedef** alan (**niteleyicisi** eski sürümlerinde), girin `tcp://<secret>@<ip_address>:5678` nerede `<secret>` geçirilen dize `enable_attach` Python kodu `<ip_address>` budur (olabilen bir açık adresi ya da bir ad myvm.cloudapp.net gibi) uzak bilgisayarın ve `:5678` uzaktan hata ayıklama bağlantı noktası numarası.

    > [!Warning]
    > Ortak internet üzerinden bir bağlantı yapıyorsanız kullanılmalı `tcps` bunun yerine ve yönerge için aşağıdaki [hata ayıklayıcı bağlantı SSL ile güvenli hale getirme](#securing-the-debugger-connection-with-ssl).

1. Bu bilgisayarda kullanılabilir ptvsd işlemlerin listesini doldurmak için Enter tuşuna basın:

    ![Bağlantı hedefi girerek ve işlemleri listeleme](media/remote-debugging-qualifier.png)

    Bu liste, select doldurduktan sonra uzak bilgisayarda başka bir program başlatmaya görülüyorsa **yenileme** düğmesi.

1. Hata ayıklama işlemini seçin ve ardından **Attach**, veya işlemi çift tıklatın.

1. Visual Studio sonra anahtarları betik uzak bilgisayarda çalışmaya devam ederken hata ayıklama modu içine tüm olağan sağlama [hata ayıklama](debugging-python-in-visual-studio.md) özellikleri. Örneğin, üzerinde bir kesme noktası belirleyerek `if guess < number:` satır, sonra uzak bilgisayara geçebilir ve başka bir tahmin girin. Bunu, Visual Studio, kesme, yerel bilgisayar durur yaptıktan sonra yerel değişkenleri ve benzeri gösterir:

    ![Kesme noktası isabet](media/remote-debugging-breakpoint-hit.png)

1. Hata ayıklama durdurduğunuzda, uzak bilgisayarda çalıştırmaya devam programdan Visual Studio ayırır. ptvsd herhangi bir zamanda yeniden işleme iliştirebilirsiniz böylece hata ayıklayıcıları, ekleme için dinleme devam eder.

### <a name="connection-troubleshooting"></a>Bağlantı sorunlarını giderme

1. Seçtiğinizden emin olun **Python uzaktan (ptvsd)** için **bağlantı türü** (**Python uzaktan hata ayıklama** için **aktarım** ile eski sürümleri.)
1. Denetleyin gizliliği **bağlantı hedef** (veya **niteleyicisi**) uzaktan kod gizliliği tam olarak eşleşir.
1. IP adresi onay **bağlantı hedef** (veya **niteleyicisi**), uzak bilgisayarın eşleşir.
1. Uzak bilgisayarda uzaktan hata ayıklama bağlantı noktası açıldı, bağlantı noktası soneki bağlantı hedef gibi dahil ettiğiniz olduğunu denetleyip `:5678`.
    - Farklı bir bağlantı noktası kullanmanız gerekiyorsa, bunu belirtebilirsiniz `enable_attach` çağrıda `address` bağımsız değişkeni olarak da `ptvsd.enable_attach(secret = 'my_secret', address = ('0.0.0.0', 8080))`. Bu durumda, Güvenlik Duvarı'nda bu bağlantı noktasını açın.
1. Tarafından döndürülen gibi uzak bilgisayarda yüklü ptvsd sürümü onay `pip3 list` aşağıdaki tabloda Visual Studio'da kullanmakta olduğunuz Python araçları sürümü tarafından kullanılan eşleşir. Gerekirse, uzak bilgisayarda ptvsd güncelleştirin.

    | Visual Studio sürümü | Python araçları/ptvsd sürümü |
    | --- | --- |
    | 2017 15.3 | 3.2.0 |
    | 2017 15.2 | 3.1.0 |
    | 2017 15.0, 15.1 | 3.0.0 |
    | 2015 | 2.2.6 |
    | 2013 | 2.2.2 |
    | 2012, 2010 | 2.1 |

## <a name="securing-the-debugger-connection-with-ssl"></a>Hata ayıklayıcı bağlantı SSL ile güvenli hale getirme

Varsayılan olarak, ptvsd uzaktan hata ayıklama sunucu bağlantısını yalnızca gizli tarafından korunmaktadır ve tüm veriler düz metin olarak geçirilir. Daha güvenli bir bağlantı için aşağıdaki gibi ayarladığınız SSL ptvsd destekler:

1. Uzak bilgisayarda ayrı otomatik olarak imzalanan sertifika ve anahtar dosyalarını openssl kullanarak oluştur:

    ```command
    openssl req -new -x509 -days 365 -nodes -out cert.cer -keyout cert.key
    ```

    İstendiğinde, ana bilgisayar adı veya IP adresi (hangisi bağlanmak için kullandığınız) kullanılmaya **ortak ad** openssl tarafından istendiğinde.

    (Bkz [otomatik olarak imzalanan sertifikalar](http://docs.python.org/3/library/ssl.html#self-signed-certificates) python'da `ssl` ek ayrıntılar için modülü belgeleri. Bu belgeleri komutta yalnızca tek bir birleşik dosyası oluşturur unutmayın.)

1. Çağrısı kodda değişiklik `enable_attach` içerecek şekilde `certfile` ve `keyfile` değerleri olarak dosya adları kullanılarak bağımsız değişkenler (Bu bağımsız değişkenler standart için olduğu gibi aynı anlama sahip `ssl.wrap_socket` Python işlevi):

    ```python
    ptvsd.enable_attach(secret='my_secret', certfile='cert.cer', keyfile='cert.key')
    ```

    Yerel bilgisayarda kod dosyasındaki aynı değişiklik yapabilir, ancak aslında bu kodu çalıştırmak değil çünkü kesinlikle gerekli değildir.

1. Hata ayıklama için hazır hale getirme uzak bilgisayarda Python programını yeniden başlatın.

1. Visual Studio ile Windows bilgisayarındaki güvenilen kök CA sertifikası ekleyerek güvenli kanal:

    1. Sertifika dosyası uzak bilgisayardan yerel bilgisayara kopyalayın.
    1. Denetim Masası'nı açın ve gidin **Yönetimsel Araçlar > bilgisayar sertifikalarını yönetmek**.
    1. Görüntülenen penceresinde genişletin **güvenilen kök sertifika yetkilileri** sol tarafta sağ **sertifikaları**seçip **tüm görevler > içeri aktarma...** .
    1. Gidin ve seçin `.cer` dosya kopyalanmış uzak bilgisayardan, alma işlemini tamamlamak için iletişim kutularını ' ye tıklayın.

1. Şimdi kullanarak daha önce açıklandığı gibi Visual Studio'da ekleme işlemi yineleyin `tcps://` protokolü olarak **bağlantı hedef** (veya **niteleyicisi**).

    ![SSL ile uzaktan hata ayıklama taşıma seçme](media/remote-debugging-qualifier-ssl.png)

### <a name="warnings"></a>Uyarılar

Visual Studio hakkında olası Sertifika sorunları, aşağıda açıklandığı gibi SSL üzerinden bağlanırken ister. Uyarılarını yoksayın ve devam etmek, ancak kanal olmasına rağmen hala şifrelenmesi gizlice dinlemeye karşı daha man-in--middle saldırılara açık olabilir.

1. Aşağıdaki "uzak sertifikası güvenilir değil" uyarıyı görürseniz, doğru sertifika için güvenilen kök CA'ın eklemediniz anlamına gelir. Bu adımları denetleyin ve yeniden deneyin.

    ![SSL güvenilen sertifika Uyarısı](media/remote-debugging-ssl-warning.png)

1. Aşağıdaki "uzak sertifika adı ana bilgisayar adı eşleşmiyor" uyarıyı görürseniz, kullanmayan uygun konak adı veya IP adresi olarak demektir **ortak ad** sertifika oluştururken.

    ![SSL sertifika hostname Uyarısı](media/remote-debugging-ssl-warning2.png)

> [!Warning]
> Bu uyarılar yoksay, şu anda, Visual Studio 2017 askıda kalır. Bağlanmayı denemeden önce tüm sorunları düzeltmek emin olun.
