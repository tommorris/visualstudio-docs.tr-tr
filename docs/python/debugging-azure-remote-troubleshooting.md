---
title: "Azure uzak Visual Studio'da Python için hata ayıklama sorunlarını giderme | Microsoft Docs"
ms.custom: 
ms.date: 07/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b723b343-dffb-457e-9af7-ee48c1451e30
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 5f8c27eb0c1360e2bd0fcf0593a8438383b6fd69
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Uzaktan sorun gidericisini Python ve Azure için hata ayıklama

Visual Studio başarısız eklemek bir [uzaktan hata ayıklama için Azure App Service](debugging-azure-remote.md) aşağıdaki nedenlerden biriyle için:

| Neden | Çözüm |
| --- | --- |
| Bilgisayarınızda Visual Studio 2013 güncelleştirme 4 veya sonraki bir sürümü yüklü. | Uygun bir sürümden yüklemek [visualstudio.com](https://www.visualstudio.com/downloads/). | 
| Uygulama hizmeti dağıtılan projeyi Visual Studio'da bir açık eşleşmiyor. | Doğru projeyi Visual Studio'ya yükleyin. |
| Proje ile hata ayıklama yapılandırmasını dağıtılan değildi. | Çözüm Gezgini'nde projeye sağ tıklayıp seçerek uygulamayı yeniden Dağıt **Yayımla**. İçinde **ayarları** sekmesinde, emin olun **hata ayıklama** seçili yapılandırmadır. |
| Uygulama hizmeti çalışmıyor. | Başlatın Visual Studio'da Sunucu Gezgini'nden veya Azure portalından. |
| App Service web yuvalarını için yapılandırılmamış. | Gidin [Azure portal](https://portal.azure.com), açık, App Service'e gidin **ayarlar > Uygulama ayarları** dikey penceresinde Aç **genel ayarları > Web yuvaları** için**Üzerinde**seçip **kaydetmek**. (Unutmayın **hata ayıklama** bu dikey pencerede gösterilen seçenekler yapın *değil* Python hata ayıklama için geçerlidir.) |
| `web.debug.config`hata ayıklama proxy devre dışı bırakmak için değiştirildi. | Dosyayı silin ve hangi sırada Visual Studio dosyasını yeniden oluşturur. uygulama hizmeti projesine yeniden yayımlayın. |

Ayrıca bkz.:

- [Azure uzaktan Python için hata ayıklama](debugging-azure-remote.md)
