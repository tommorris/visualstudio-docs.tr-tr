---
title: Yerel Visual Studio Yardım belgelerine yükleyin
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
f1_keywords:
- hv_manage
helpviewer_keywords:
- changing content installation source [Help Viewer]
- updating local content [Help Viewer]
- Help Viewer, content installation source
- Help Viewer, updating local content
- Help Viewer, changing content installation source
- installing local content [Help Viewer]
- content installation source [Help Viewer]
- downloading content [Help Viewer]
- removing local content [Help Viewer]
- Help Viewer, removing local content
- Help Viewer, installing local content
- Help Viewer, downloading content
ms.assetid: efd9df4c-2e69-4c50-992c-9678a8d8cf19
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 702c1124e3b14f8bfec4f514edd8e1e7def6b776
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947644"
---
# <a name="install-and-manage-local-content"></a>Yükleme ve yerel içeriği yönetme

Microsoft Yardım Görüntüleyicisi'ni kullanarak, Ekle, Kaldır, güncelleştirme ve yazılım geliştirme gereksinimlerinize uyacak şekilde bilgisayarınızda yüklü Yardım içeriği taşıma.

Yerel bilgisayarınızda içeriği yönetmek için yönetici izinlerine sahip bir hesapla oturum açmalısınız. Ayrıca, bir kuruluş ortamında çalışıyorsanız, sistem yöneticileri, kuruluşunuz için bu kararlar almanıza çünkü yerel içeriği yönetmek mümkün olmayabilir. Daha fazla bilgi için bkz: [Yardım Görüntüleyicisi Yönetici Kılavuzu'na](../ide/help-viewer-administrator-guide.md).

## <a name="change-the-content-installation-source"></a>İçerik yükleme kaynağını değiştirme

Varsayılan olarak, Yardım Görüntüleyici, içerik kaynağı olarak bir Microsoft online service kullanarak yükler. Kendisi için bir Sistem Yöneticisi içeriği başka bir konumda yüklü bir kuruluş ortamında iş sürece, genellikle, içerik kaynağı değiştirilmemesi gerekir.

### <a name="to-change-the-content-installation-source"></a>İçerik yükleme kaynağı değiştirmek için

1.  Üzerinde **içeriği Yönet** sekmesinde, seçin **Disk** seçenek düğmesi.

    > [!NOTE]
    > **Disk** seçeneği yöneticinize içerik yükleme kaynağını değiştirme engelledi kullanılabilir değil. Daha fazla bilgi için bkz: [Yardım Görüntüleyicisi Yönetici Kılavuzu'na](../ide/help-viewer-administrator-guide.md).

2.  Aşağıdaki adımlardan birini uygulayın:

    -   Yolunu girin bir *.msha* dosya veya bir hizmet uç noktası URL'si.

    -   Gözat'ı seçin (**...** ) düğmesine gitmek için bir *.msha* dosya.

    -   Listede, en son kullanılan giriş seçin.

## <a name="download-and-install-content-locally"></a>İçeriği yerel olarak indir ve yükle

Yerel bilgisayarınızda içerik yükleyip varsa, internet bağlantısı olmadığında konuları görüntüleyebilirsiniz.

> [!IMPORTANT]
> İçeriği yüklemek için yönetim izinlerine sahip bir hesapla oturum açmalısınız.

> [!NOTE]
> İngilizce dışında bir dil için Visual Studio IDE ayarlarsanız, İngilizce içerik, yerelleştirilmiş içeriği veya her ikisi de yükleyebilirsiniz. Yalnızca İngilizce sürümünü yüklerseniz, ancak içerik görünür ve **dahil İngilizce içerik tüm gezinme sekmeleri ve F1 istekleri** onay kutusuna **Görüntüleyici seçenekleri** iletişim kutusu temizlenir.

### <a name="to-download-and-install-content"></a>Karşıdan yükleme ve içeriği yüklemek için

1.  Seçin **içeriği Yönet** sekmesi.

2.  İçerik listede seçin **Ekle** kitap veya indirmek ve yüklemek için istediğiniz books yanındaki bağlantı.

     Kitap eklenen **bekleyen değişiklikler** listesi ve kitap ya da görünür bu liste belirtilen books tahmini boyutu. Bazı books konuları paylaştığından, birden çok books toplam indirme boyutu birlikte belirttiğiniz her kitap boyutlarını ekleme sonucunu küçük olabilir.

3.  Seçin **güncelleştirme** düğmesi.

     Kitap ya da belirttiğiniz books bilgisayarınızda zaten defterleri için herhangi bir güncelleştirme ile birlikte yüklenir. Yükleme süreleri değişir, ancak durum çubuğunda ilerleme durumunu görüntüleyebilirsiniz.

## <a name="remove-local-content"></a>Yerel içeriği kaldırma

Bilgisayarınızdan istenmeyen içerik kaldırarak disk alanından kazanabilirsiniz.

> [!IMPORTANT]
> İçeriği kaldırmak için yönetici izinleri olmalıdır.

> [!NOTE]
> İngilizce dışında bir dil için Visual Studio IDE ayarlarsanız, kaldırdığınız yerelleştirilmiş içeriği, içerik görünür ve **dahil İngilizce içerik tüm gezinti sekmesi ve F1 istekleri** onay kutusuna **Görüntüleyici seçenekleri** iletişim kutusu temizlenir.

### <a name="to-remove-content"></a>İçeriği kaldırmak için

1.  Seçin **içeriği Yönet** sekmesi.

2.  İçerik listede seçin **kaldırmak** kitap veya kaldırmak istediğiniz books yanındaki bağlantı.

     Kitap eklenen **bekleyen değişiklikler** listesi.

3.  Seçin **güncelleştirme** düğmesi.

     Kitap ya da belirttiğiniz books bilgisayarınızdan kaldırılır.

## <a name="update-local-content"></a>Yerel içeriği güncelleştirme

Durum çubuğu, güncelleştirmelerinin yüklü içeriğinize ne zaman kullanılabileceğini gösterir.

> [!IMPORTANT]
> İsterseniz **Yardım Görüntüleyici** otomatik olarak çevrimiçi güncelleştirmeleri denetlemek için açmalısınız **Görüntüleyici seçenekleri** iletişim kutusunu ve ardından **içerik güncelleştirmeleridenetlemekiçinçevrimiçi**onay kutusu.

### <a name="to-update-local-content"></a>Yerel içeriği güncelleştirmek için

-   Durum çubuğu sağ alt köşedeki seçin **şimdi yüklemek için burayı tıklatın** bağlantı.

 Güncelleştirme zamanlarını farklılık gösterebilir, ancak durum çubuğunda güncelleştirme ilerleme durumunu görüntüleyebilirsiniz.

## <a name="move-local-content"></a>Yerel içerik taşıma

Yüklü olan içeriğin yerel bilgisayarınızdan bir ağ paylaşımına veya başka bir bölüm için yerel bilgisayarınızda taşıyarak disk alanından kazanabilirsiniz.

> [!IMPORTANT]
> İçeriği taşımak için yönetim izinlerine sahip bir hesapla oturum açmalısınız.

### <a name="to-move-local-content"></a>Yerel içerik taşımak için

1.  Üzerinde **içeriği Yönet** sekmesinde, seçin **taşıma** altında düğmesini **yerel deposu yolu**.

     **Taşıma içerik** iletişim kutusu açılır.

2.  İçinde **için** metin kutusuna içerik için farklı bir konum girin ve ardından **Tamam** düğmesi.

3.  Seçin **Kapat** içeriği taşındıklarında düğmesine tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft Yardım Görüntüleyicisi](../ide/microsoft-help-viewer.md)