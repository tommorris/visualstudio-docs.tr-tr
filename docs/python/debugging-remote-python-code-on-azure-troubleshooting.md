---
title: Python için hata ayıklama Azure Uzak sorunlarını giderme
description: Visual Studio kullanarak Azure App Service içinde çalışan bir Python uygulama hatalarını ayıklama çalışılırken sorunlarını gidermek nasıl.
ms.date: 07/12/2017
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
ms.openlocfilehash: 3d792a411867686abe0734fc67dfe654320d8b38
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Uzaktan hata ayıklama sorun gidericisini Python ve Azure

Visual Studio başarısız eklemek bir [uzaktan hata ayıklama için Azure App Service](debugging-remote-python-code-on-azure.md) aşağıdaki nedenlerden biriyle için:

| Neden | Çözüm |
| --- | --- |
| Bilgisayarınızda Visual Studio 2013 güncelleştirme 4 veya sonraki bir sürümü yüklü. | Uygun bir sürümden yüklemek [visualstudio.com](https://www.visualstudio.com/downloads/). | 
| Uygulama hizmeti dağıtılan projeyi Visual Studio'da bir açık eşleşmiyor. | Doğru projeyi Visual Studio'ya yükleyin. |
| Proje ile hata ayıklama yapılandırmasını dağıtılan değildi. | Çözüm Gezgini'nde projeye sağ tıklayıp seçerek uygulamayı yeniden Dağıt **Yayımla**. İçinde **ayarları** sekmesinde, emin olun **hata ayıklama** seçili yapılandırmadır. |
| Uygulama hizmeti çalışmıyor. | Başlatın Visual Studio'da Sunucu Gezgini'nden veya Azure portalından. |
| App Service web yuvalarını için yapılandırılmamış. | Gidin [Azure portal](https://portal.azure.com), açık, App Service'e gidin **ayarlar > Uygulama ayarları** dikey penceresinde Aç **genel ayarları > Web yuvaları** için**Üzerinde**seçip **kaydetmek**. (Unutmayın **hata ayıklama** bu dikey pencerede gösterilen seçenekler yapın *değil* Python hata ayıklama için geçerlidir.) |
| `web.debug.config` hata ayıklama proxy devre dışı bırakmak için değiştirildi. | Dosyayı silin ve hangi sırada Visual Studio dosyasını yeniden oluşturur. uygulama hizmeti projesine yeniden yayımlayın. |

Ayrıca bkz.:

- [Azure uzaktan Python için hata ayıklama](debugging-remote-python-code-on-azure.md)
