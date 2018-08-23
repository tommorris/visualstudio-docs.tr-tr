---
title: TF sürüm denetimi
description: Team Foundation Server veya Visual Studio Team Services, Team Foundation sürüm denetimi ile bağlanma.
author: conceptdev
ms.author: crdun
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 101f002f6c311fe5aaefa78c246602fd45514603
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624076"
---
# <a name="connecting-to-team-foundation-version-control"></a>Team Foundation sürüm denetimine bağlama 

> [!NOTE]
> **Not**: Team Foundation sürüm denetimi desteği şu anda Önizleme aşamasındadır ve bazı işlevler henüz tam olarak çalışmıyor. Sizden geri bildirim herhangi bir sorun üzerinde isteriz [Geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/41/index.html). Daha fazla değişiklik hala gelen üzeresiniz!

Visual Studio Team Services (VSTS) ve Team Foundation Server (TFS), sürüm denetimi iki modeli sağlar: dağıtılan Git sürüm denetimi ve Team Foundation sürüm denetimi (olan TFVC), merkezi sürüm denetimi. Mac için Visual Studio Team Foundation sürüm denetimi kullanmak için bu makalede bir genel bakış ve bir başlangıç noktası sağlar

## <a name="requirements"></a>Gereksinimler

* Visual Studio Community, Professional veya Enterprise Mac 7.5 veya sonraki bir sürümü için.
* Visual Studio Team Services veya Team Foundation Server 2013 ve üzeri sürümler.
* Visual Studio Team Services veya Team Foundation Server, Team Foundation sürüm denetimi kullanmak üzere yapılandırılmış bir proje.

## <a name="installation"></a>Yükleme

Mac için Visual Studio'da **Visual Studio > uzantılar...**  menüsünde. İçinde **galeri** sekmesinde **sürüm denetimi > Team Foundation sürüm denetimi için TFS ve VSTS** tıklatıp **yükle...** :

  ![Uzantı Yöneticisi](media/tfvc-install.png) 

Uzantıyı yüklemek için istemleri izleyin. Yüklendikten sonra IDE yeniden başlatın.

## <a name="updating-the-extension"></a>Uzantıyı güncelleştirirken

TFVC uzantı güncelleştirmeleri düzenli olarak gerçekleştirilir. Güncelleştirmeleri erişmek, seçin **Visual Studio > uzantılar...**  seçin ve menüden **güncelleştirmeleri** sekmesi. Uzantı listesi ve ENTER tuşuna seçin **güncelleştirme** düğmesi:

  ![Uzantı Yöneticisi'ni gösteren güncelleştirme](media/tfvc-update.png) 

Tuşuna **yükleme** sonraki iletişim kutusunda eski paketi kaldırın ve yenisini yükleyin.

Her sürümdeki yenilikler hakkında daha fazla bilgi için bkz: [sürüm notları](https://docs.microsoft.com/visualstudio/releasenotes/vs2017-mac-preview-relnotes#team-foundation-version-control-extension--release-notes).

## <a name="using-the-add-in"></a>Eklenti kullanma

Uzantıyı yükledikten sonra seçin **sürüm denetimi > TFS/VSTS > Uzak depodan açık** menü öğesi. 

Visual Studio Team Services veya Team Foundation Server kullanmaya başlayın ve basın seçin **devam**:

  ![Bir sunucuyla bağlanma](media/tfvc-choose-server-type.png)

### <a name="vsts-authentication"></a>VSTS kimlik doğrulaması

VSTS üzerinde barındırılan bir proje seçtiğinizde, Microsoft hesabı ayrıntılarını girin istenir:

  ![Bir VSTS Server'a bağlanma](media/tfvc-vsts-login.png)

### <a name="tfs-authentication"></a>TFS kimlik doğrulaması

TFS'ye bağlanmak için sunucu ayrıntıları ve hesap kimlik bilgilerinizi girin. Aksi takdirde temel kimlik doğrulaması kullanmak için boş bırakın, NTLM kimlik doğrulaması kullanmak için bir etki alanını girin. Seçin **sunucusu ekleme**: 

![Bir TFS sunucusuna oturum açın](media/tfvc-login.png)

## <a name="selecting-a-project"></a>Bir proje seçme

Başarıyla kimlik doğrulaması yaptınız sonra hesabı ile ilişkili olan depolar listesini görebilirsiniz **kaynak denetiminden Aç** iletişim:

  ![Kaynak denetimi iletişim kutusunda görüntülenen projeleri ile Aç](media/tfvc-vsts-projects.png)

Bu iletişim kutusunda, aşağıdaki düğümleri düzenlenmiştir:

- VSTS hesabı veya koleksiyon – oturum açtığınız Microsoft hesabı için bağlı olan tüm hesapları bu görüntüler.
- Takım projeleri takım projelerine – her VSTS, bir dizi olabilir. Bir takım projesi, kaynak kodu, iş öğeleri ve otomatik yapılara barındırıldığı ' dir.

Bu noktada, arama filtre ve bir proje veya hesap adı.

### <a name="adding-a-new-server"></a>Yeni bir sunucu ekleme

Listeye yeni bir sunucu eklemek için basın **konak Ekle** düğmesini **kaynak denetiminden Aç** iletişim:

![Vurgulanmış yeni sunucu listesine eklemek için düğme ekleme](media/tfvc-add-new-server.png)

Listeden sağlayıcıyı seçin ve kimlik bilgilerinizi girin:

![Kaynak denetimi sağlayıcısı için seçeneğini gösteren iletişim](media/tfvc-add-new-creds.png)

## <a name="creating-a-new-workspace"></a>Yeni bir çalışma alanı oluşturma

Bir proje ile çalışmaya başlamak için ihtiyacınız bir _çalışma_. Bir çalışma alanı yoksa, bir oluşturabilirsiniz **çalışma** combobox içinde **kaynak denetiminden Aç** iletişim:

![Yeni çalışma alanı combobox seçenek oluştur](media/tfvc-create-new-workspace.png)

Yeni bir çalışma alanınız için yerel yolunu ve adını ayarlar ve **çalışma alanı oluştur**:

![Yeni çalışma alanı için bir ad ve yerel yol girme](media/tfvc-local-workspace.png)

## <a name="using-the-source-code-explorer"></a>Kaynak kod Gezgini kullanma

Bir çalışma alanı oluşturup projenizi eşlenen ile çalışmaya başlayabilir _kaynak kod Gezgini_.

Kaynak kod gezginini açmak için seçmeniz **sürüm denetimi > TFS/VSTS > Kaynak Denetim Gezgini**:

![Kaynak kod gezginini açmak için menü öğesi](media/tfvc-source-control-explorer.png)

Kaynak kod Gezgini eşlenen tüm projeler, dosyalar ve klasörler gitmenizi sağlar. Ayrıca gibi tüm temel kaynak denetim eylemleri gerçekleştirmenize olanak sağlar:

- En son sürümü Al
- Belirli Sürümü Al
- Dosyaları kullanıma alma ve iade etme
- Kilitleme ve dosyaları kilidini açma
- Ekleme, silme ve dosyaları yeniden adlandırma
- Geçmişi görüntüle
- Değişiklikleri Karşılaştır.

Bu eylemlerin çoğunu, projenin bağlam eylemleri aracılığıyla sunulur:

![Bir proje için bağlam menüsünü eylemleri](media/tfvc-sourcecode-actions.png)

## <a name="managing-workspaces"></a>Çalışma alanlarını yönetme

Henüz yapmadıysanız, açıklandığı bir çalışma alanı oluşturma [çalışma alanı oluşturma](#creating-a-new-workspace) bölümünde seçeneğinde kaynak kod Gezgini boştur:

![boş bir kaynak kod Gezgini](media/tfvc-setup-empty-sce.png) 

Uzak bir yerel çalışma alanı projenizle ayarlamak için aşağıdaki adımları kullanın:

1. Seçin **sunucu** Açılır kutudan.
1. Yerel yol "Eşlenmemiş" ise ve "çalışma alanı" olduğunu unutmayın. Seçin **eşlenmedi** görüntülemek için bağlantıyı **yeni çalışma alanı oluşturma** iletişim.
1. Çalışma alanı için bir ad belirtin ve ardından **çalışma klasörü Ekle** bilgisayarınızdaki bir yerel klasör proje eşlemek için:
    
    ![Varsayılan seçenekleri gösteren yeni bir çalışma alanı iletişim kutusu oluşturma](media/tfvc-workspace1.png) 

1. Sunucunuzdaki tüm takım projeleri aynı çalışma alanına eşleme her bir proje seçin veya tıklayın "$" klasörü seçin **Tamam**:
    
    ![Tüm projeler gösteren klasör iletişim kutusu için Gözat](media/tfvc-workspace2.png) 

1. Mp projeleri için istediğiniz ve yerel makinenizdeki konumu seçin **Klasör Seç**.
1. Yeni çalışma alanı ayrıntılarını tuşlarına basarak onaylayın **Tamam**
    
    ![Eklenen çalışma klasörü ile yeni çalışma alanı iletişim kutusu oluşturma](media/tfvc-workspace3.png) 

Çalışma alanınızı ayarladıktan sonra onu değiştirilebilir ya tıklayarak kaldırıldı **çalışma alanlarını yönet** düğmesi kaynak kod gezginindedir.

![Çalışma alanlarını yönetme](media/tfvc-workspace4.png)

## <a name="troubleshooting"></a>Sorun giderme

### <a name="problems-using-basic-authentication"></a>Temel kimlik doğrulaması kullanma ile ilgili sorunlar

Bir sunucunun kimliğini doğrulamak için aşağıdaki seçenekler kullanılabilir:

- OAuth
- Temel
- NTLM

Bunu etkinleştirmek için gereken temel kimlik doğrulaması kullanacak şekilde **alternatif kimlik doğrulama bilgilerini** vsts'de aşağıdaki adımları izleyerek:

1. VSTS hesabınız (https://{youraccount}.visualstudio.com) için hesap sahibi olarak oturum açın.
2. Hesap, araç çubuğunda, dişli simgesini seçin ve seçin **ilke**:
    
    ![Seçili İlkesi ayarları seçeneği](media/tfvc-auth2.png) 

3. Uygulama bağlantı ayarlarınızı gözden geçirin. Güvenlik ilkelerine bağlı olarak, bu ayarları değiştirin:
    
    ![Seçili İlkesi ayarları seçeneği](media/tfvc-auth.png)  

### <a name="i-do-not-see-anything-in-tfvc"></a>Tfvc'de herhangi bir şey göremiyorum

Geliştirme makinenizde Team Foundation sürüm denetimi (TFVC) kurmak ayarlamak için **gerekir** açıklandığı bir çalışma alanı oluşturma [çalışma alanlarını yönetme](#managing-workspaces) bölümü.

Kaynak denetimi Gezgini'nde basın **çalışma alanlarını yönet** düğmesi. Takım projesini geliştirme makinenizde bir klasörü eşlemek için adımları izleyin.

### <a name="i-do-not-see-any--all-of-my-projects"></a>Göremiyorum / all, projelerim

Kimlik doğrulandıktan sonra projelerinin listesini görmeniz gerekir. Varsayılan olarak, yalnızca TFS projelerine gösterilmektedir. Diğer proje türleri görmek için "tüm projeleri bkz" kutusunu işaretleyin.

Doğru ayrıcalıklara sahip değilseniz, sunucu üzerinde olan projeler görünmez göz önünde bulundurun.

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>Hatası "çalışma alanı oluşturulamıyor. alıyorum Lütfen yeniden deneyin"

Çalışırken [yeni bir çalışma alanı oluşturma](#creating-a-new-workspace), aşağıdaki koşulların yerine getirildiğinden emin olmanız gerekir:

- Çalışma alanı adı geçersiz karakterler markaları kullanılamaz.
- Ad 64 karakterden kısa olmalıdır.
- Yerel yol diğer çalışma alanları tarafından kullanılamaz.