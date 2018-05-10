---
title: Yardım Görüntüleyicisi Yönetici Kılavuzu
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
ms.assetid: 4340c69f-b96b-4932-bb82-38b16a5ab149
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bccbd4f1365ea42b3e0331283a5659502038e133
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="help-viewer-administrator-guide"></a>Yardım Görüntüleyicisi Yönetici Kılavuzu

Yardım Görüntüleyicisi'ni ağ ortamları olan veya internet erişimi olmayan yerel Yardım yüklemelerinde yönetmenize olanak sağlar. Yerel Yardım içeriğinin bir makine başına temelinde yapılandırılır. Varsayılan olarak, kullanıcılar kendi yerel Yardım yüklemesini güncelleştirmek için yönetici haklarına sahip olmalıdır.

Ağ ortamınızı Internet'e erişmek istemciler izin veriyorsa kullanabilirsiniz **Yardım içeriği Yöneticisi** Internet'ten yerel Yardım içeriği dağıtmak için çalıştırılabilir. Hakkında daha fazla bilgi için *HlpCtntMgr.exe* komut satırı sözdizimi için bkz: [komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi](../ide/command-line-arguments-for-the-help-content-manager.md).

Bir intranet Hizmeti uç noktası ve etkinlikleri, benzer türde içerik oluşturma hakkında daha fazla bilgi için bkz [Yardım Görüntüleyicisi SDK](../extensibility/internals/microsoft-help-viewer-sdk.md).

Ağ ortamınızda internet erişimi yoksa, Yardım Görüntüleyici intranet veya bir ağ paylaşımına yerel Yardım içeriğini dağıtabilirsiniz. Kullanarak da Visual Studio IDE Help seçenekleri devre dışı bırakabilirsiniz [kayıt defteri anahtarı geçersiz kılar](../ide/help-content-manager-overrides.md) gibi işlevler için:

- çevrimiçi çevrimdışı Yardım karşılaştırması

- IDE ilk kez başlatıldığında içerik yükleme

- bir intranet içerik hizmeti belirtme

- içeriği yönetme

## <a name="deploy-local-help-content-from-the-internet"></a>İnternet'ten yerel Yardım içeriği dağıtma

Kullanabileceğiniz **Yardım içeriği Yöneticisi** (*HlpCtntMgr.exe*) yerel Yardım içeriği Internet'ten istemci bilgisayarlara dağıtmak için. Aşağıdaki sözdizimini kullanın:

```cmd
\\%ProgramFiles(x86)%\Microsoft Help Viewer\v2.3\HlpCtntmgr.exe /operation \<*name*> /catalogname \<*catalog name*> /locale \<*locale*>
```

Hakkında daha fazla bilgi için *HlpCtntMgr.exe* komut satırı sözdizimi için bkz: [komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi](../ide/command-line-arguments-for-the-help-content-manager.md).

Gereksinimleri:

-   İstemci bilgisayarların internet erişimi olması gerekir.

-   Kullanıcılar, güncelleştirme, ekleme veya yüklendikten sonra yerel Yardım içeriğini kaldırmak için yönetici haklarına sahip olmalıdır.


Uyarılar:

-   Varsayılan kaynak Yardım için çevrimiçi olmaya devam eder.

### <a name="example"></a>Örnek

Aşağıdaki örnek İngilizce içerik Visual Studio için bir istemci bilgisayara yükler.

#### <a name="to-install-english-content-from-the-internet"></a>İnternet'ten İngilizce içeriği yüklemek için

1.  Seçin **Başlat** ve ardından **çalıştırmak**.

2.  Aşağıdakileri yazın:

     `C:\Program Files (x86)\Microsoft Help Viewer\v2.3\hlpctntmgr.exe /operation install /catalogname VisualStudio15 /locale en-us`

3.  Tuşuna **girin**.

## <a name="deploy-pre-installed-local-help-content-on-client-computers"></a>İstemci bilgisayarlarda önceden yüklenmiş yerel Yardım içeriği dağıtma

İçerik kümesinin Online'dan tek bir bilgisayara yükleyin ve ardından o yüklü bir içerik kümesinin diğer bilgisayarlara kopyalayın.

Gereksinimleri:

-   İçin içerik kümesinin yüklediğiniz bilgisayar, internet erişimi olması gerekir.

-   Kullanıcılar, güncelleştirme, ekleme veya yüklendikten sonra yerel Yardım içeriğini kaldırmak için yönetici haklarına sahip olmalıdır.

    > [!TIP]
    > Kullanıcıların yönetici hakları yoksa, devre dışı bırakmanız önerilir **içeriği Yönet** Yardım Görüntüleyici sekmesindedir. Daha fazla bilgi için bkz: [Yardım İçerik Yöneticisi geçersiz kılmaları](../ide/help-content-manager-overrides.md).

Uyarılar:

-   Varsayılan kaynak Yardım için çevrimiçi olmaya devam eder.

### <a name="create-the-content-set"></a>İçerik kümesi oluşturma

Temel içerik kümesi oluşturmadan önce hedef bilgisayardaki tüm yerel Visual Studio İçerik kaldırmanız gerekir.

#### <a name="to-uninstall-local-help"></a>Yerel Yardım'ı kaldırmak için

1.  Yardım Görüntüleyici'de seçin **içeriği Yönet** sekmesi.

2.  Visual Studio belge kümesine gidin.

3.  Seçin **kaldırmak** her alt öğenin yanındaki.

4.  Seçin **güncelleştirme** kaldırmak için.

5.  Gözat *%ProgramData%\Microsoft\HelpLibrary2\Catalogs\VisualStudio15* ve klasörü yalnızca dosya içerdiğini doğrulayın *catalogType.xml*.

 Tüm önceden yüklenmiş yerel Visual Studio Yardım içeriğine kaldırıldıktan sonra temel içerik kümesi yüklemeye hazırsınız demektir.

#### <a name="to-download-the-content"></a>İçerik indirmek için

1.  Yardım Görüntüleyici'de seçin **içeriği Yönet** sekmesi.

2.  Altında **önerilen belgelerine** veya **mevcut belgeleri**, indirin ve ardından istediğiniz belge kümelerinde gezinmeyi **Ekle**.

3.  Seçin **güncelleştirme**.


Ardından, istemci bilgisayarlara dağıtılabilir şekilde içerik paketini gerekir.

#### <a name="to-package-the-content"></a>Paket içeriği

1.  Sonraki dağıtım için içeriği kopyalamak için bir klasör oluşturun. Örneğin: *C:\VSHelp*.

2.  Açık *cmd.exe* yönetici izinlerine sahip.

3.  1. adımda oluşturduğunuz klasöre gidin.

4.  Aşağıdakileri yazın:

     `Xcopy %ProgramData%\Microsoft\HelpLibrary2 \<*foldername*>\ /y /e /k /o `

     Örneğin: `Xcopy %ProgramData%\Microsoft\HelpLibrary2 c:\VSHelp\ /y /e /k /o`

### <a name="deploy-the-content"></a>İçerik dağıtma

1.  Bir ağ paylaşımı oluşturmanız ve Yardım içeriği bu konuma kopyalayın.

     Örneğin, içeriği Kopyala *C:\VSHelp* için  *\\\myserver\VSHelp*.

2.  Oluşturma bir *.bat* Yardım içeriği için dağıtım betiğini içeren dosya. İstemci itme bir parçası olarak silinen dosyalardan birini üzerinde okuma kilidi olabilir beri güncelleştirmelerini iletme önce kapatıldı istemci olması gerekir. Örneğin:

    ```cmd
    REM - copy pre-ripped content to ProgramData
    Xcopy %~dp0HelpLibrary2 %SYSTEMDRIVE%\ProgramData\Microsoft\HelpLibrary2\ /y /e /k /o
    if ERRORLEVEL 1 ECHO *** ERROR COPYING Help Library files to ProgramData (%ERRORLEVEL%)
    ```

3.  Çalıştırma *.bat* Yardım içeriği yüklemek istediğiniz yerel makinede dosya.

## <a name="see-also"></a>Ayrıca bkz.

- [Komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi](../ide/command-line-arguments-for-the-help-content-manager.md)
- [Yardım İçerik Yöneticisi geçersiz kılar](../ide/help-content-manager-overrides.md)
- [Microsoft Yardım Görüntüleyicisi](../ide/microsoft-help-viewer.md)
- [Yardım Görüntüleyicisi SDK](../extensibility/internals/microsoft-help-viewer-sdk.md)