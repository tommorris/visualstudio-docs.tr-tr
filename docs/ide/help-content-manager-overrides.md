---
title: Yardım İçerik Yöneticisi geçersiz kılar
ms.date: 11/01/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: conceptual
ms.assetid: 95fe6396-276b-4ee5-b03d-faacec42765f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7a10004227a7979d72f167bcc51abdb741c0370d
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="help-content-manager-overrides"></a>Yardım İçerik Yöneticisi geçersiz kılar

Yardım Görüntüleyicisi'ni ve Visual Studio IDE Yardım ilgili özellikleri varsayılan davranışını değiştirebilirsiniz. Bazı seçenekler oluşturarak belirtilir bir [.pkgdef](https://blogs.msdn.microsoft.com/visualstudio/2009/12/18/whats-a-pkgdef-and-why/) çeşitli kayıt defteri anahtarı değerlerini ayarlamak için dosya. Başkalarının doğrudan kayıt defterinde ayarlanır.

## <a name="how-to-control-help-viewer-behavior-by-using-a-pkgdef-file"></a>Yardım Görüntüleyici davranışı .pkgdef dosyasını kullanarak denetleme

1. Oluşturma bir *.pkgdef* ilk satır olarak dosyasıyla `[$RootKey$\Help]`.

2. Kayıt defteri anahtarı değerlerini açıklandığı gibi ayrı satırlara aşağıdaki tabloda bir bölümünü veya tamamını eklemek `“UseOnlineHelp”=dword:00000001`.

3. Dosyaya Kopyala *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\< edition\>\Common7\IDE\CommonExtensions*.

4. Çalıştırma `devenv /updateconfiguration` Geliştirici komut istemindeki.

### <a name="registry-key-values"></a>Kayıt defteri anahtarı değerleri

|Kayıt defteri anahtarı değeri|Tür|Veri|Açıklama|
|------------------|----|----|-----------|
|NewContentAndUpdateService|dize|\<Hizmet uç noktası için http URL'si\>|Benzersiz bir hizmet uç noktası tanımlayın|
|UseOnlineHelp|dword|`0` Yerel Yardım belirtmek için `1` çevrimiçi Yardım belirtmek için|Çevrimiçi veya çevrimdışı Yardım varsayılan tanımlayın|
|OnlineBaseUrl|dize|\<Hizmet uç noktası için http URL'si\>|Benzersiz bir F1 bitiş noktasını tanımlayın|
|OnlineHelpPreferenceDisabled|dword|`0` etkinleştirmek için veya `1` çevrimiçi Yardım tercih seçeneği devre dışı bırakmak için|Çevrimiçi Yardım tercih seçeneği devre dışı bırak|
|DisableManageContent|dword|`0` etkinleştirmek için veya `1` devre dışı bırakmak için **içeriği Yönet** Yardım Görüntüleyici'de sekmesi|Devre dışı **içeriği Yönet** sekmesi|
|DisableFirstRunHelpSelection|dword|`0` etkinleştirmek için veya `1` Visual Studio başlatır ilk kez yapılandırılmış Yardım özellikleri devre dışı bırakmak için|Visual Studio'nun ilk kez başlatıldığında içerik yüklenmesini devre dışı bırak|

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

## <a name="use-registry-editor-to-change-help-viewer-behavior"></a>Yardım Görüntüleyici davranışını değiştirmek için Kayıt Defteri Düzenleyicisi'ni kullanın

Aşağıdaki iki davranışları, Kayıt Defteri Düzenleyicisi'nde kayıt defteri anahtarı değerlerini ayarlayarak denetlenebilir.

|Görev|Kayıt Defteri Anahtarı|Değer|Veri|
|----------|-----|------|----|
|BITS iş önceliği geçersiz kıl|(Bulunan bir 64-bit machine)\Microsoft\Help\v2.3 HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node|Bıtsönceliği|**ön plan**, **yüksek**, **normal**, veya **düşük**|
|Yerel içerik deposu ağ paylaşımına işaret|HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Help\ v2.3\Catalogs\VisualStudio15|LocationPath|"*ContentStoreNetworkShare*"|

## <a name="see-also"></a>Ayrıca bkz.

- [Yardım Görüntüleyicisi Yönetici Kılavuzu](../ide/help-viewer-administrator-guide.md)
- [Komut satırı bağımsız değişkenleri için Yardım içeriği Yöneticisi](../ide/command-line-arguments-for-the-help-content-manager.md)
- [Microsoft Yardım Görüntüleyicisi](../ide/microsoft-help-viewer.md)
- [Yalıtılmış Kabuk .pkgdef dosyasını kullanarak değiştirme](../extensibility/shell/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)