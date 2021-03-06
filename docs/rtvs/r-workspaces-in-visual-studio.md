---
title: R çalışma alanları
description: Visual Studio çalışma alanları kullanarak R kodu çalıştığı kontrol etme.
ms.date: 01/24/2018
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: 859e44c912ed98a50d5127675eb2c1bed699ede6
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238386"
---
# <a name="control-where-r-code-runs-with-workspaces"></a>R kodu ile çalışma alanları çalıştığı denetimi

R araçları için Visual Studio (RTVS) çalışma bir R oturumu, hangi hem yerel hem de uzak bilgisayarlarda oluşabilir çalıştığı yapılandırmanıza olanak sağlar. Hedef ya da potansiyel olarak daha güçlü bulut tabanlı bilgisayarlar yararlanmak olanağı sağlayan bir karşılaştırılabilir kullanıcı deneyimi ile çalışmak izin vermektir.

Açmak için **çalışma alanları** penceresi, kullanım **R Araçları** > **Windows** > **çalışma alanları** komut veya tuşlarına basın **Ctrl**+**9**.

![Visual Studio (VS2017) için R Araçları penceresinde çalışma alanları](media/workspaces-window.png)

Bu pencerede, yeşil onay işareti RTVS bağlandığı etkin çalışma alanı gösterir. Mavi ok seçerek etkin çalışma alanı ayarlar. Her çalışma sağındaki ayarları (dişli) simgesini adını, konumunu ve komut satırı bağımsız değişkenleri değiştirmenize izin verir. Kırmızı X el ile eklenen bir çalışma alanı kaldırır.

## <a name="save-and-reset-a-workspace"></a>Kaydet ve bir çalışma alanı Sıfırla

Bir proje kapatıp, varsayılan olarak, çalışma durumu RTVS kaydetmez. Bu davranışı değiştirebilirsiniz ancak aracılığıyla [çalışma alanı seçenekleri](options-for-r-tools-in-visual-studio.md#workspace).

**R Araçları** > **oturum** > **sıfırlama** komut ve etkileşimli penceresinde sıfırlama araç çubuğu düğmesini ayrıca herhangi çalışma durumu Sıfırla süre. Uzaktan çalışma ile sıfırlama ilk etkili bir şekilde var. birikmiş tüm dosyaları siler bir uzak sunucuya bağlanırken oluşturulan kullanıcı profili siler.

## <a name="local-workspaces"></a>Yerel çalışma alanları

Yerel çalışma alanları, bilgisayarınızda yüklü tüm R yorumlayıcılar görüntüler. 

Visual Studio başlatıldığında tüm bakarak yüklediğiniz R sürümlerinin otomatik olarak algılamak çalışır **HKEY_LOCAL_MACHINE\Software\R çekirdek\**  kayıt defteri anahtarı. Bu denetim yalnızca başlangıçta yapıldığından, yeni bir R yorumlayıcı yüklerseniz, Visual Studio yeniden başlatmanız gerekir.

RTVS standart olmayan bir şekilde (örneğin, yalnızca dosya bir yükleyici çalıştırmak yerine bir klasöre kopyalarken) yüklü bir R yorumlayıcı algılayamayabilir. Bu durumda, el ile yeni bir yerel R çalışma alanı gibi oluşturun:

1. Seçin **Ekle** çalışma alanları penceresinde düğmesini.
1. Yeni bir çalışma alanı için bir ad girin.
1. İçeren olan R kök klasörün yolunu girin *bin* RTVS başladığında yorumlayıcısı geçirmek için tüm isteğe bağlı komut satırı bağımsız değişkenleri birlikte yorumlayıcı klasörüyle.
1. Seçin **kaydetmek** tamamladığınızda.

![Yeni bir çalışma alanı ekleme](media/workspaces-add-new.png)

## <a name="remote-workspaces"></a>Uzak çalışma alanları

Uzak çalışma alanları bir R oturumu uzak bir bilgisayara bağlamanızı sağlar. (Bkz [uzak çalışma alanlarınızı ayarlamalarına](setting-up-remote-r-workspaces.md) nasıl bu amaç için bir bilgisayarı yapılandırmak.)

Visual Studio otomatik olarak algılamıyor uzak çalışma alanları, bunları kullanarak el ile eklemeniz gerekir böylece **Ekle** önceki bölümde açıklandığı gibi çalışma alanları penceresinde düğme. Bu durumda, bir yerel yol yerine uzak bilgisayarın URI girin.

> [!Important]
> Uzak çalışma alanları bir URI tarafından tanımlanan, *HTTPS protokolünü kullanmalıdır* gizlilik ve uzak bilgisayarla iletişim bütünlüğünü sağlamak için. Visual Studio HTTPS desteklemeyen bir uzak bilgisayara bağlanamıyor.

> [!Note]
> Uzak çalışma alanları etkili bir şekilde önizlemede. Biz dosya eşitleme sorun gelecekteki bir yayın için daha iyi bir uygulama üzerinde çalıştığınız ve fikir ve geri bildirim Hoş Geldiniz.

## <a name="remote-workspace-logon"></a>Uzaktan çalışma oturum açma

Uzaktan çalışma alanına bir kullanıcı adı ve parola oturum açma için kullanmanız gerekir.

### <a name="logon-to-windows-workspace"></a>Windows çalışma alanına oturum açma

Uzak makine etki alanı hesabı kullanmak için Kurulum ise, bir uzak çalışma alanına erişmek için etki alanı oturum açma kullanabilirsiniz. Değil sonra kullanmak zorunda `machine-name\username` uzak makinede bir makine hesabı kullanarak oturum açmak için biçimi.

### <a name="logon-to-linux-workspace"></a>Linux çalışma alanına oturum açma

Oturum açmak için bir linux hesap kullanımı `<<unix>>\username` biçimi. Ada göre bir hesabınız varsa, örneğin, `ruser`, kullanıcı adı olarak yazmanız sonra `<<unix>>\ruser`.

## <a name="switch-between-workspaces"></a>Çalışma alanları arasında geçiş

RTVS aynı anda yalnızca tek bir çalışma alanına bağlı. İlişkili çalışma çalışma alanları penceresinde küçük yeşil onay işareti ile belirtilir. Varsayılan olarak, önceki bir oturumda açık bir son yerel çalışma RTVS bağlar.

Etkin çalışma alanı değiştirmek için istenen çalışma alanını yanındaki mavi oku seçin. Bunun yapılması, oturumunuz kaydetmek isteyip istemediğinizi sorar geçerli çalışma alanı sonlandırır ve ardından yeni bir geçiş yapar.

> [!Tip]
> Kaydetme devre dışı bırakmak için komut istemi, select **R Araçları** > **seçenekleri** komut ve ayarlayın **çalışma alanları geçmeden önce göster onay iletişim kutusu** seçeneği`No`. Bkz: [çalışma alanı seçenekleri](options-for-r-tools-in-visual-studio.md#workspace).

Kaldırıldı, veya deftere kullanılamıyor, RTVS oluşturulmaması bir uzak çalışma alanına herhangi bir çalışma alanına bağlı bir yerel çalışma geçmek çalışır. Sonuç olarak, etkileşimli pencerede kodu girin veya aksi halde kodu çalıştırmak çalıştığınızda bir hata görebilirsiniz:

![Çalışma alanı için RTVS bağlı olduğunda hata](media/workspaces-disconnected-interactive-window.png)

Bu sorunu gidermek için çalışma alanları penceresinde başka bir çalışma alanına geçin. Bir çalışma alanınız varsa, bir R yorumlayıcı yüklemeniz gerekir. Ayrıca, Visual Studio çalışırken bir yorumlayıcı yüklediyseniz Visual Studio'yu yeniden başlatmayı deneyebilirsiniz.

### <a name="switch-to-a-remote-workspace"></a>Bir uzak çalışma alanına geçin

RTVS bir uzak çalışma alanı için ilk bağlandığında, kimlik bilgilerini ister ve ardından sonraki oturumlar için (güvenli Windows kimlik bilgileri kasası kullanarak) bu kimlik bilgilerini önbelleğe alır. Uzak sunucu ile iletişim, (gerekli olan) HTTPS üzerinden güvenli bir şekilde gerçekleştirilir.

Sunucu yapılandırmasına bağlı olarak, "Uzaktan R Hizmetleri tarafından sunulan güvenlik sertifikası (ad) makineye gerçekten bağlanan kanıtlamak için bize izin vermiyor." Bu okuma bağlanırken uyarı sertifika görebilirsiniz.

![Bir uzak çalışma alanına bağlanırken otomatik olarak imzalanan sertifika Uyarısı](media/workspaces-remote-self-signed-certificate-warning.png)

Sertifika için RTVS bağlanmaya çalıştığınız bilgisayar tarafından sunulan bir belgedir. Sertifika, o bilgisayardaki URI tanımlayan bir alan içeriyor. RTVS sertifika URI ve sunucunun güvenlik tehlikede olduğunu olduğunu belirten bilgisayara bağlanmak için kullanılan URI arasında bir uyuşmazlık algıladığında bir uyarı görüntülenir.

Ancak, bu uyarıyı de görünür bir *otomatik olarak imzalanan sertifika* güvenilen bir sağlayıcı birinden kullanmak yerine uzak bilgisayarda HTTPS'yi etkinleştirmek için kullanıldı. Daha fazla bilgi için bkz: [uzak çalışma alanlarınızı ayarlamalarına](setting-up-remote-r-workspaces.md).

## <a name="directories-on-local-and-remote-computers"></a>Yerel ve uzak bilgisayarlarda dizinleri

Varsayılan olarak, yerel çalışma alanında, yeni bir R yorumlayıcı başlattığınızda, geçerli çalışma dizini olan *%userprofile%\Documents*. Dizini kullanarak istediğiniz zaman değiştirebilirsiniz **R Araçları** > **çalışma dizini** komutlar, veya göre Visual Studio Çözüm Gezgini'nde projeye sağ tıklayıp gibikomutlarıseçerek **Dizin burada çalışma kümesi**.

Bir uzak bilgisayara ilk bağlandığında RTVS çalışma dizini ayarlar için bir kullanıcı profili, kimlik bilgilerine göre otomatik olarak oluşturur. *belgeleri* bu profili altında bir klasör. Bu klasör, aynı kimlik bilgilerini kullanan tüm sonraki uzak oturumlar için kullanılır.

Sonuç olarak, kodunuzun çalıştığı tam konumu yerel ve uzak çalışma alanları arasında değişebilir. Kodunuzun çalışma alanları arasında taşınabilir olmasını sağlamak, kodunuzda sonra her zaman veri dosyaları ve gibi göreli yollar kullanın.

Uzaktan çalışma alanlarını Ayrıca, aynı kullanıcı profili için oturumlar arasında çalışma dizinindeki tüm dosyaları yerinde kalır. Daha önce belirtildiği gibi kullanarak bu dosyaları silebilirsiniz **R Araçları** > **oturum** > **sıfırlama** komutu (veya Sıfırla düğmesini Etkileşimli pencere) bir uzak çalışma alanı kullanırken. Bu komut, kullanıcı profili yeniden bağladığınızda, yeniden sunucudan yeniden siler.

## <a name="copy-project-files-to-remote-workspaces"></a>Uzaktan çalışma alanlarına proje dosyalarını kopyalayın

Bile bir uzak çalışma alanı kullanırken Visual Studio'da R projeleri ile çalışırken, yerel bilgisayarda her zaman en son proje dosyalarını vardır. Visual (yani genellikle proje içeren bir çözüm açma) Studio'da bir projeyi açtığınızda, diğer bir deyişle, projenin içeriği tamamen yerel bilgisayarda bulunabilir RTVS varsayar. Uzaktan çalışma, etkili, projenin dosyaları ve tüm için yalnızca geçici bir konak olduğu koddan çıktı. Bu, örneğin, kullanarak bir dosyaya yüklenirken anlamına `source` etkileşimli penceresinde, bu dosya zaten yolundaki uzak bilgisayarda sağladığınız ya da uzak R yorumlayıcı geçerli çalışma dizininde olması gerekir olmalıdır ( ileayarlamak`setwd()`</c2>işlevi).

Dosyalar aşağıdaki gibi uzak sunucuya kopyalanır:

- Etkileşimli pencere üzerinden uzaktan dosyalarıyla çalışmak için önce bunları el ile bu dosyaları (veya proje) Çözüm Gezgini'nde sağ tıklayıp seçerek kopyalamanız gerekir **kaynak seçili**. Tek tek dosyalar için bunlar sunucuda çalışma dizinine kopyalanır; bir proje kopyalarken RTVS proje için bir klasör oluşturur.

- Dosyaları sonra Çözüm Gezgini'nde ve ardından seçerek kopyalayabilirsiniz **kaynak seçili dosyaları (s)**. Bu eylem, etkileşimli penceresine yükler ve orada çalıştırır. Oturumu bir uzak bilgisayara bağlıysa, dosyalar var. önce kopyalanır.

- Ne zaman RTVS bir uzak çalışma alanına bağlı ve tuşlarına basarak **F5**seçin **hata ayıklama** > **hata ayıklamayı Başlat**, veya aksi takdirde varsayılan RTVS kodunuzu çalıştırmaya başlayın Proje dosyası uzak çalışma alanına otomatik olarak kopyalar (aşağıda bu davranışı denetlemek için bkz.).

- Sunucuda zaten mevcut dosyaların üzerine yazılır.

> [!Note]
> RTVS tüm R işlev çağrılarını güvenilir bir şekilde müdahale edemez çünkü işlevleri gibi çağırma `source()` veya `runApp()` (için parlak uygulamalar) etkileşimli pencereye mu *değil* dosyaları uzak çalışma alanına kopyalayın.

[Proje Özellikleri](r-projects-in-visual-studio.md#project-properties) Denetim dosyalarını bir proje zaman RTVS kopyalar olup Çalıştır ve tam olarak hangi dosyalar kopyalanır. Bu sayfayı açın, seçin **proje** > **(ad) özellikleri** menü komutu ya da sağ tıklatma seçip Çözüm Gezgini proje **özellikleri**.

![Proje Özellikleri sekmesi ile dosya aktarımı çalışma ayarları](media/workspaces-remote-file-transfer-filter-settings.png)

Burada, **aktarım çalıştırmada dosyaları** özelliği, RTVS proje dosyalarını otomatik olarak kopyalar olup olmadığını belirler. **Aktarılacak dosyaları** tam olarak hangi dosyaların aktarıldığını filtreleri değeri. Yalnızca kopyalamak için varsayılan değer *. R*, *. Rmd*, *.sql*, *.md*, ve *.cpp* dosyaları. Bu davranış, yanlışlıkla her çalıştırılışında sunucusuyla büyük veri dosyaları kopyalanıyor önler. 

## <a name="copy-files-from-a-remote-workspace"></a>Bir uzak çalışma alanından dosyaları Kopyala

R betiği dosyaları sunucu üzerinde oluşturursa, bu dosyaları kullanarak istemciye kopyalayabilirsiniz `rtvs::fetch_file` işlevi. Bu işlev, en az, uzak bilgisayarınıza kopyalamak istediğiniz dosyanın yolunu ve isteğe bağlı olarak, bilgisayarınızdaki hedef yolu kabul eder. Bir yol belirtmezseniz, dosyanın kopyalanır, *%userprofile%\Downloads* klasör.
