---
title: Bir Web sitesi için yayımlama
ms.custom: ''
ms.date: 06/22/2018
ms.technology: vs-ide-deployment
ms.topic: quickstart
helpviewer_keywords:
- deployment, website
ms.assetid: fc82b1f1-d342-4b82-9a44-590479f0a895
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ede36baefa71e352f6f7e4960403ecbaa6b304b2
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36757228"
---
# <a name="publish-a-web-app-to-a-web-site-using-visual-studio"></a>Visual Studio kullanarak bir web sitesi için bir web uygulaması yayımlama

Kullanabileceğiniz **Yayımla** ASP.NET, ASP.NET Core, .NET Core ve Python uygulamaları Visual Studio'dan bir Web sitesine yayımlamak için aracı. Node.js için adımları desteklenmektedir, ancak kullanıcı arabirimi farklıdır.

[!INCLUDE [quickstart-prereqs](includes/quickstart-prereqs.md)]

## <a name="publish-to-a-web-site"></a>Bir web sitesi için yayımlama

1. Çözüm Gezgini'nde projeye sağ tıklayın ve seçin **Yayımla** (veya **yapı** > **Yayımla** menü öğesi).

    ![Çözüm Gezgini'nde proje bağlam menüsünde Yayımla komutunu](../deployment/media/quickstart-publish.png "seçin yayımlama")

1. Tüm yayımlama profillerini daha önce yapılandırdıysanız **Yayımla** bölmesinde görünür. Seçin **yeni profil oluşturmak**.

1. İçinde **yayımlama hedefi çekme** iletişim kutusunda, seçin **IIS, FTP, vb**.

    ![IIS, FTP, vb.'ı seçin.](../deployment/media/quickstart-publish-iis-ftp.png "IIS seçin, FTP, vs.")

1. Seçin **yayımlama**. Profil yayımlama Ayarları iletişim kutusu açılır.

    ![Klasörü seçin](../deployment/media/quickstart-publish-settings-web.png "klasörü seçin")

1. İçinde **yayımlama yöntemi** alanında, aşağıdaki gibi bir yöntem seçin **Web dağıtımı** veya **FTP**. Gördüğünüz ayarları sonraki yayımlama yönteminize karşılık gelir. Web dağıtımı IIS sunucuları için Web uygulamaları ve Web siteleri dağıtımını basitleştirir ve sunucu üzerindeki bir uygulama olarak yüklenmesi gerekir. Kullanım [Web Platformu yükleyicisi](https://www.microsoft.com/web/downloads/platform.aspx) yükleyin.

1. Yayımlama yöntemi için gereken ayarları yapılandırın ve seçin **bağlantıyı doğrula**. Sunucu veya hedef kullanılabilir ve ayarlarınızın doğru olduğunu, bağlantı belirten bir ileti doğrulanır ve yayımlamak hazırsınız.

    ![Bağlantınızı doğrulama](../deployment/media/quickstart-publish-web-deploy.png "bağlantınızı doğrulama")

1. Seçin **ayarları** Debug veya Release bir yapılandırma dağıtmanız ve ardından gibi diğer dağıtım ayarlarını yapılandırmak için **kaydetmek**. Uzaktan hata ayıklama, bir hata ayıklama yapılandırması gereklidir.

1. Yayımlamak için seçin **Yayımla**. Çıktı penceresi dağıtımının ilerleme durumunu ve sonuçlarını gösterir.

## <a name="next-steps"></a>Sonraki adımlar

Bu hızlı başlangıç Visual Studio yayımlama profili oluşturmak için nasıl kullanılacağı hakkında bilgi edindiniz. Ayrıca bir yayımlamayı yapılandırabilirsiniz alarak profili yayımlama ayarları.

> [!div class="nextstepaction"]
> [Yayımlama ayarlarını içeri aktarma ve IIS’ye dağıtma](tutorial-import-publish-settings-iis.md)
