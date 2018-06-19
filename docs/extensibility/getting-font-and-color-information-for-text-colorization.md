---
title: Yazı tipi ve renk bilgi metni renklendirme için alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- text, coloring
- font and color control [Visual Studio SDK], coloring
ms.assetid: d1f985bd-743e-40b7-9458-d9af53647c91
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8c86e37d6d7da9da0a6b0978770bf7d7564fa19c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129702"
---
# <a name="getting-font-and-color-information-for-text-colorization"></a>Yazı tipi ve metin renklendirme için renk bilgilerini alma
İşler veya kullanıcı arabirimini (UI) öğeleri renklendirilen metni görüntüleyen işlem proje, teknoloji ve geliştirici Tercihler türüne bağlıdır. **Yazı tiplerini ve renkleri** özellik sayfası ayarları depolar.

 Renklendirilen metni görüntüle çoğu uygulamaları gereksinim <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> ve sunan, alınmasını ve metin depolama ayarlarını görüntülemek için arabirimleri ilişkili.

> [!NOTE]
>  Çekirdek Düzenleyici özelleştirirken (destekleyen **metin EditorCategory**), dil hizmetinde renklendirme teknolojisi kullanmanız önerilir. Daha fazla bilgi için bkz: [yazı tipi ve renk genel bakış](../extensibility/font-and-color-overview.md).

## <a name="getting-default-font-and-color-information"></a>Varsayılan yazı tipi ve renk bilgilerini alma
 Tüm **yazı tiplerini ve renkleri** metin görüntüleme penceresi ayarları belirtilmelidir **öğeleri görüntüleme** bir **kategori**. Daha fazla bilgi için bkz: [yazı tipleri ve renkler, ortam, Seçenekler iletişim kutusu](../ide/reference/fonts-and-colors-environment-options-dialog-box.md).

Bir VSPackage renklendirme geçerli edinmeniz gerekir **yazı tiplerini ve renkleri** ayarlar. Bir VSPackage kendi gereksinimlerine bağlı olarak aşağıdaki yollarla geçerli ayarları elde edebilirsiniz:

-   Yazı tipi ve renk Kalıcılık mekanizması saklı veya geçerli durumunu almak için kullanın. Daha fazla bilgi için bkz: [erişme depolanan yazı tipi ve renk ayarlarını](../extensibility/accessing-stored-font-and-color-settings.md).

-   Kullanım <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> örneğini almak için yazı tipi ve renk veri sağlayan bir hizmet arabiriminin <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>VSPackage de yazı tipi ve renk sağlayıcı değilse.

-   Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> arabirimi.

Yoklama tarafından elde edilen sonuçlar güncel olan, kullanılacak yararlı olabilir emin olmak için <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> alma yöntemlerini çağırmadan önce bir güncelleştirme gerekli olup olmadığını belirlemek için arabirimi <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> arabirimi.

Sonra yazı tipi ve renk bilgilerini aldıysanız, renklendirme gerektiren öğeleri tanımlamak için görüntülenecek metni ayrıştırılamadı. Metin uygun yazı tipleri ve renkler kullanarak penceresinde görüntüler.

## <a name="see-also"></a>Ayrıca Bkz.

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>
- [Yazı Tipleri ve Metin Kullanma](/dotnet/framework/winforms/advanced/using-fonts-and-text)
- [Renklerle çalışma](/cpp/windows/working-with-color-image-editor-for-icons)
- [GDI (grafik cihaz arabirimi)](http://msdn.microsoft.com/en-us/7e1d4540-bb2e-4257-8eee-eee376acba83)