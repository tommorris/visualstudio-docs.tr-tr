---
title: "Yardım İçerik Yöneticisi geçersiz kılmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-help-viewer
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 143bc6af5aa42eb480d5eff736633c2df6e68979
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2017
---
# <a name="help-content-manager-overrides"></a>Yardım İçerik Yöneticisi Geçersiz Kılmaları
Yardım Görüntüleyicisi'ni ve Visual Studio IDE Yardım ilgili özellikleri varsayılan davranışını değiştirebilirsiniz. Bazı seçenekler oluşturarak belirtilir bir [.pkgdef](https://blogs.msdn.microsoft.com/visualstudio/2009/12/18/whats-a-pkgdef-and-why/) çeşitli kayıt defteri anahtarı değerlerini ayarlamak için dosya. Başkalarının doğrudan kayıt defterinde ayarlanır.

## <a name="how-to-control-help-viewer-behavior-by-using-a-pkgdef-file"></a>Yardım Görüntüleyici davranışı .pkgdef dosyasını kullanarak denetleme

1. Bir .pkgdef dosyası ilk satırı ile oluşturmak `[$RootKey$\Help]`.

2. Kayıt defteri anahtarı değerlerini açıklandığı gibi ayrı satırlara aşağıdaki tabloda bir bölümünü veya tamamını eklemek `“UseOnlineHelp”=dword:00000001`.

3. % ProgramFiles (x86) %\Microsoft Visual Studio\2017 dosyasını kopyalayın\\< edition\>\Common7\IDE\CommonExtensions.

4. Çalıştırma `devenv /updateconfiguration` Geliştirici komut istemindeki.

### <a name="registry-key-values"></a>Kayıt defteri anahtarı değerleri
|Kayıt defteri anahtarı değeri|Tür|Veri|Açıklama|  
|------------------|----|----|-----------|  
|NewContentAndUpdateService|dize|\<Hizmet uç noktası için http URL'si\>|Benzersiz bir hizmet uç noktası tanımlayın|
|UseOnlineHelp|DWORD|`0`Yerel Yardım belirtmek için `1` çevrimiçi Yardım belirtmek için|Çevrimiçi veya çevrimdışı Yardım varsayılan tanımlayın|
|OnlineBaseUrl|dize|\<Hizmet uç noktası için http URL'si\>|Benzersiz bir F1 bitiş noktasını tanımlayın|
|OnlineHelpPreferenceDisabled|DWORD|`0`etkinleştirmek için veya `1` çevrimiçi Yardım tercih seçeneği devre dışı bırakmak için|Çevrimiçi Yardım tercih seçeneği devre dışı bırak|
|DisableManageContent|DWORD|`0`etkinleştirmek için veya `1` devre dışı bırakmak için **içeriği Yönet** Yardım Görüntüleyici'de sekmesi|İçeriği Yönet sekmesini devre dışı bırak|
|DisableFirstRunHelpSelection|DWORD|`0`etkinleştirmek için veya `1` Visual Studio başlatır ilk kez yapılandırılmış Yardım özellikleri devre dışı bırakmak için|Visual Studio'nun ilk kez başlatıldığında içerik yüklenmesini devre dışı bırak|

### <a name="example-pkgdef-file-contents"></a>Örnek .pkgdef dosya içerikleri
```
[$RootKey$\Help]
“NewContentAndUpdateService”=”https://some.service.endpoint”
“UseOnlineHelp”=dword:00000001
“OnlineBaseUrl”=”https://some.service.endpoint”
“OnlineHelpPreferenceDisabled”=dword:00000000
“DisableManageContent”=dword:00000000
“DisableFirstRunHelpSelection”=dword:00000001
```

## <a name="using-registry-editor-to-change-help-viewer-behavior"></a>Yardım Görüntüleyici davranışını değiştirmek için Kayıt Defteri Düzenleyicisi'ni kullanarak
Aşağıdaki iki davranışları, Kayıt Defteri Düzenleyicisi'nde kayıt defteri anahtarı değerlerini ayarlayarak denetlenebilir.  
  
|Görev|Kayıt Defteri Anahtarı|Değer|Veri|  
|----------|-----|------|----|
|BITS iş önceliği geçersiz kıl|(Bulunan bir 64-bit machine)\Microsoft\Help\v2.3 HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node|Bıtsönceliği|**ön plan**, **yüksek**, **normal**, veya **düşük**|
|Yerel içerik deposu ağ paylaşımına işaret|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\v2.3\Catalogs\VisualStudio15|LocationPath|"*ContentStoreNetworkShare*"|
  
## <a name="see-also"></a>Ayrıca bkz.
[Yardım Görüntüleyicisi Yönetici Kılavuzu](../ide/help-viewer-administrator-guide.md)  
[Komut satırı bağımsız değişkenleri için Yardım İçerik Yöneticisi](../ide/command-line-arguments-for-the-help-content-manager.md)  
[Microsoft Yardım Görüntüleyicisi](../ide/microsoft-help-viewer.md)  
[Yalıtılmış Kabuk .pkgdef dosyasını kullanarak değiştirme](../extensibility/shell/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)