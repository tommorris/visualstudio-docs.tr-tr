---
title: TF sürüm denetimi
description: Team Foundation Server veya Visual Studio Team Services Team Foundation sürüm denetimi ile bağlanma.
author: asb3993
ms.author: amburns
ms.date: 05/03/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 58d0fc5c31b02574661f8b86a4ae8bcaf393be3a
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34693779"
---
# <a name="connecting-to-team-foundation-version-control"></a>Team Foundation sürüm denetimi bağlama 

> [!NOTE]
> **Not**: Team Foundation sürüm denetimi desteği şu anda önizlemede ve bazı işlevler henüz tam olarak çalışmıyor. Herhangi bir sorunla sizden geribildirim memnuniyet duyarız [Geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/41/index.html). Daha fazla değişiklik hala gelen üzeresiniz!

Visual Studio Team Services (VSTS) ve Team Foundation Server (TFS) iki modeli sürüm denetimi sağlar: dağıtılan Git sürüm denetimi ve Team Foundation sürüm denetimi (olan TFVC'yi), sürüm denetimi Merkezi. Mac için Visual Studio ile Team Foundation sürüm denetimi kullanmak için bu makalede genel bir bakış ve bir başlangıç noktası sağlar

## <a name="requirements"></a>Gereksinimler

* Mac 7.5 veya sonraki bir sürümü için Visual Studio.
* Visual Studio Team Services veya Team Foundation Server 2013 ve üstü
* Visual Studio Team Services veya Team Foundation Server, Team Foundation sürüm denetimi kullanmak üzere yapılandırılmış bir proje.

## <a name="installation"></a>Yükleme

Mac için Visual Studio'da, **Visual Studio > uzantıları...**  menüsünde. İçinde **galeri** sekmesine **sürüm denetimi > TFS ve VSTS için Team Foundation sürüm denetimi** tıklatıp **yükle...** :

  ![Uzantı Yöneticisi](media/tfvc-install.png) 

Uzantıyı yüklemek için istemleri izleyin. Bir kez yüklenir, IDE yeniden başlatın.

## <a name="using-the-add-in"></a>Eklenti kullanma

Uzantısı yüklendikten sonra Seç **sürüm denetimi > TFS/VSTS > Team Foundation sürüm denetimi Bağlan...**  menü öğesi. Tıklatın **Ekle** yeni bir hesap eklemek için: 

![TFVC'yi sunucu ekleme](media/tfvc-add-remove-server.png)

Visual Studio Team Services veya Team Foundation Server başlamak için seçin:

![TFVC'yi Server ile bağlanma](media/tfvc-choose-server-type.png)

Kimlik bilgilerinizi girin ve tıklayın **oturum**: 

![TFVC'yi sunucuya oturum açın](media/tfvc-login.png)

Başarıyla oturum oluşturulduktan sonra erişim ve basın istediğiniz projeleri seçin **Tamam**: 

![Projeleri seçin](media/tfvc-choose-projects.png)

Seçin **sürüm denetimi > TFS/VSTS > Kaynak Denetim Gezgini** , kaynak göz atmanıza izin vererek Kaynak Denetim Gezgini'ni açmak için kullanılan menü öğesi.

> [!IMPORTANT]
> **Bilinen sorun**: önizleme sürümünü ilk kez, Kaynak Denetim Gezgini'ni açmak, zorunda kalırsınız [yeni bir çalışma alanı oluşturma](#creating-a-new-workspace).

![Kaynak Gezgini](media/tfvc-source-explorer.png)

Kaynak kodu Gezgini'nden sunucuda, kaynak kodu bulun ve aşağıdaki eylemleri gerçekleştirin:

- Çalışma alanları (Oluştur, Düzenle veya Sil) yönetin.
- Proje yapısı arasında gidin.
- Projeleri eşleyin.
- Projeleri alın.
- Kilit & Unlock dosyaları.
- Dosyalarını yeniden adlandırın.
- Dosyaları silin.
- Yeni dosya ekleyin.
- Kontrol etme.
- Teslim etme.
- Geçmiş değişiklikleri görüntüleyin.
- Değişiklikleri karşılaştırın.

## <a name="creating-a-new-workspace"></a>Yeni bir çalışma alanı oluşturma

Kaynak Denetim Gezgini tıklayın **çalışma alanlarını yönet** düğmesi. 

![Çalışma alanlarını yönet](media/tfvc-manage-workspaces.png)

Tıklatın **Ekle** yeni bir çalışma alanı oluşturmak için düğmesi.

![Çalışma alanı oluşturma](media/tfvc-create-workspace.png)

Çalışma alanı için bir ad sağlayın ve ardından **çalışma klasörü Ekle** proje bilgisayarınızdaki yerel bir klasöre eşleştirmek için.

İşiniz bittiğinde, tıklatın **Tamam**, çalışma alanlarını yönet iletişim kutusunu kapatın. Artık dosyaları kaynak kod Gezgini ancak almak ve başlamak hazırsınız.

## <a name="troubleshooting"></a>Sorun giderme

### <a name="problems-using-basic-authentication"></a>Temel kimlik doğrulaması kullanarak sorunları

Bir sunucu ile kimlik doğrulaması gerçekleştirmek için kullanılabilir farklı seçenekler vardır:

- OAuth
- Temel
- NTLM

Temel kimlik doğrulamasını kullanabilmek için bunu etkinleştirmek için gerekli olan **alternatif kimlik doğrulama bilgilerini** aşağıdaki adımları izleyerek VSTS içinde:

1. VSTS hesabınıza (https://{youraccount}.visualstudio.com) hesap sahibi olarak oturum açın.
2. Hesap araç çubuğundan dişli simgesini seçin ve Seç **İlkesi**: ![seçili İlkesi ayarları seçeneği](media/tfvc-auth2.png) 
3. Uygulama bağlantı ayarlarınızı gözden geçirin. Güvenlik ilkelerine bağlı olarak, bu ayarları değiştirmek: ![seçili İlkesi ayarları seçeneği](media/tfvc-auth.png)  

### <a name="i-do-not-see-anything-in-tfvc"></a>Her şeyi TFVC'yi görmüyorum

Geliştirme makinenizde Team Foundation sürüm denetimi (TFVC'yi) ayarlamak için **gerekir** açıklandığı gibi bir çalışma alanı oluşturma [yeni bir çalışma alanı oluşturma](#creating-a-new-workspace) bölümü.

Kaynak Denetim Gezgini'nde basın **çalışma alanlarını yönet** düğmesi. Geliştirme makinenizde bir klasöre takım projesi eşlemek için adımları izleyin.

### <a name="i-do-not-see-any--all-of-my-projects"></a>Görmüyorum / all my projeleri

Kimlik doğrulamasından sonra projelerinin listesini görmeniz gerekir. Varsayılan olarak, yalnızca TFS projelerine gösterilir. Diğer projeler türlerini görmek için "tüm projeleri bkz" kutuyu işaretleyin.

Doğru ayrıcalıklara sahip değilseniz, sunucu üzerinde olan projeler görünmez göz önünde bulundurun.

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>Hata "çalışma alanı oluşturamazsınız. alıyorum Lütfen yeniden deneyin"

Çalışırken [yeni bir çalışma alanı oluşturma](#creating-a-new-workspace), aşağıdaki koşulların yerine getirildiğinden emin olmanız gerekir:

- Çalışma alanı adı geçersiz karakterler hiçbir kullanımı.
- Ad 64 karakterden kısa olmalıdır.
- Yerel yol diğer çalışma alanları tarafından kullanılamaz.