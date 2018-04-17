---
title: Gelişmiş Güvenlik Ayarları iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.err.debug_in_zone_no_hostproc
helpviewer_keywords:
- Advanced Security Settings dialog box
ms.assetid: 2e7aefe9-6d20-4f3e-b257-aee1ebcc6f5d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1dad7843d42aeaf0c2871f8b76c840a12cd4186
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="advanced-security-settings-dialog-box"></a>Gelişmiş Güvenlik Ayarları İletişim Kutusu
Bu iletişim kutusu bölgesinde hata ayıklama için ilgili güvenlik ayarları belirtmenize olanak sağlar.  
  
 Bu iletişim kutusunu erişmek için bir proje düğümünde seçin **Çözüm Gezgini**ve ardından **proje** menüsünde tıklatın **özellikleri**. Zaman **Proje Tasarımcısı** görünen tıklatın **güvenlik** sekmesi. Üzerinde **güvenlik** sayfasında, **ClickOnce güvenlik ayarlarını etkinleştir**, tıklatın **kısmi güven uygulamasıdır**ve ardından **Gelişmiş**.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Bu uygulama seçili izin kümesi ile hata ayıklama**  
 Bu onay kutusunu seçerseniz, izin kümesi seçili **güvenlik** sayfası, hata ayıklama sırasında kullanılır. Varsayılan olarak, bu seçenek seçilidir.  
  
 İş için bir güvenlik bölgesi hata ayıklama için bu seçeneği etkinleştirilmelidir; Ayrıca, **barındırma işlemi Visual Studio'nun** seçeneği (kullanılabilir **hata ayıklama** sayfasında **Proje Tasarımcısı**) etkinleştirilmiş olması gerekir.  
  
 WPF Web tarayıcı uygulaması projeleri için **seçili izin kümesi ile bu uygulamanın hatalarını ayıklama** seçeneği işaretli ve devre dışı.  
  
 **Kaynak siteye uygulama erişim**  
 Bu onay kutusunu seçerseniz, uygulama Web sitesi veya sunucu paylaşımı üzerinde yayımlanır erişebilir. Varsayılan olarak, bu seçenek seçilidir.  
  
 **Aşağıdaki URL'yi yüklenen gibi bu uygulamanın hatalarını ayıklama**  
 Web sitesi veya karşılık gelen sunucu paylaşımı erişmesine izin vermek varsa **yükleme URL'si** , belirtilen **Yayımla** sayfasında, bu URL'yi buraya yazın. Bu seçenek yalnızca olan **kaynak siteye uygulama erişim** seçilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Güvenlik Sayfası, Proje Tasarımcısı](../../ide/reference/security-page-project-designer.md)