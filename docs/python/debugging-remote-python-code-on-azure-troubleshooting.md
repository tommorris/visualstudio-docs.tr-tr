---
title: Python için hata ayıklama Azure Uzak sorunlarını giderme
description: Visual Studio kullanarak Azure App Service içinde çalışan bir Python uygulama hatalarını ayıklamak çalışırken sorunlarını gidermek nasıl.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: f545fa223aa929b79016352e799d112bceddaf1c
ms.sourcegitcommit: 4f82c178b1ac585dcf13b515cc2a9cb547d5f949
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39341469"
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Python ve Azure için uzaktan hata ayıklama sorun giderici

Visual Studio başarısız iliştirmek bir [Azure App Service'ı uzaktan hata ayıklama](debugging-remote-python-code-on-azure.md) herhangi biri:

| Neden | Çözüm |
| --- | --- |
| Bilgisayarınızda Visual Studio 2013 Update 4 veya sonraki bir sürümü yüklü. | Uygun bir sürümü [visualstudio.microsoft.com](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017). |
| App Service'e dağıtılır proje Visual Studio'da bir açık eşleşmiyor. | Doğru proje Visual Studio'ya yükleyin. |
| Proje ile dağıtılan değildi **hata ayıklama** yapılandırma. | Projeye sağ tıklayarak uygulamanın yeniden **Çözüm Gezgini** seçerek **Yayımla**. İçinde **ayarları** sekmesinde, emin **hata ayıklama** seçili bir yapılandırmadır. |
| App Service çalışmıyor. | Buradan başlayın **Sunucu Gezgini** Visual Studio'da veya Azure portalından. |
| App Service web yuvaları için yapılandırılmamış. | Git [Azure portalı](https://portal.azure.com), açık, uygulamanızı App Service'e gidin **ayarları** > **uygulama ayarları**, kapatma **Genelayarlar**  >  **Web yuvaları** için **üzerinde**seçip **Kaydet**. (Unutmayın **hata ayıklama** bu dikey pencerede gösterilen seçenekler yapın *değil* Python hata ayıklama için geçerlidir.) |
| *Web.Debug.config* hata ayıklama proxy'si devre dışı bırakmak için değiştirildi. | Dosyayı silin ve hangi sırada Visual Studio dosyayı oluşturur. App Service, projeye yeniden yayımlayın. |

Ayrıca bkz:

- [Azure için Python hata ayıklama uzak](debugging-remote-python-code-on-azure.md)
