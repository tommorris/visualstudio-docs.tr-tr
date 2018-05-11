---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: c22ba73b464f91bf3036541304cdf94e8660970d
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2018
---
1. Web dağıtımı Visual Studio ile uygulamalarınızı dağıtmak istiyorsanız, sunucuda Web Dağıtımı'nın en son sürümünü yükleyin.

    Web dağıtımı yüklemek için kullandığınız [Web Platformu Yükleyicisi (Webpı)](https://www.microsoft.com/web/downloads/platform.aspx). (Web Platformu yükleyicisi bağlantı IIS'den bulmak için seçin **IIS** Sunucu Yöneticisi'nin sol bölmesinde. Sunucuya sağ tıklayın ve seçin **Internet Information Services (IIS) Yöneticisi'ni**.)

    Web Platformu Yükleyicisi'nde, Web Dağıtımı'nın uygulamalar sekmesinde bulun. Doğrudan bir yükleyici edinebilirsiniz [Microsoft Download Center](https://www.microsoft.com/search/result.aspx?q=webdeploy&form=dlc). 

2. Web dağıtımı doğru açarak çalıştığından emin olun **Denetim Masası > Sistem ve Güvenlik > Yönetim Araçları > Hizmetler** emin olun **Web Dağıtım Aracı hizmeti** çalıştıran ( Hizmet adı eski sürümlerinde farklıdır).

    Aracı hizmeti çalışmıyorsa başlatın. Hiç yoksa, Git **Denetim Masası > Programlar > program Kaldır**, bulma **Microsoft Web dağıtımı <version>** . Tercih **değişiklik** yükleme ve, seçtiğinizden emin olun **yerel sabit sürücüye yüklenecek** Web dağıtımı bileşenleri için. Değişikliği yükleme adımlarını tamamlayın.