---
title: "Bir güvenlik duvarı veya proxy sunucunun arkasındaki Visual Studio yükleme | Microsoft Docs"
description: 
ms.custom: 
ms.date: 08/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 4b203bbc3512ebc59a73a4e1420388a28fdf166b
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="install-visual-studio-behind-a-firewall-or-proxy-server"></a>Bir güvenlik duvarı veya proxy sunucunun arkasındaki Visual Studio yükleme

Visual Studio yükleyicisi, çeşitli etki alanlarına ve indirme sunucularını dosyaları indirir. Bu sayfa, dağıtım betikleri güvenilir olarak "Beyaz" isteyebilirsiniz etki alanı URL'leri listeler.

Ortamınız için Mümkünse, HTTP ve HTTPS protokolleri aşağıdaki alanlarıyla eklemeyi düşünün.

## <a name="microsoft-domains"></a>Microsoft etki alanları
| Etki Alanı | Amaç |
| ------ | ------- |
| go.microsoft.com | Kurulum URL çözümleme |
| aka.MS | Kurulum URL çözümleme |
| download.VisualStudio.microsoft.com | Paketleri indirme konumu Kurulumu |
| download.microsoft.com | Paketleri indirme konumu Kurulumu |
| download.VisualStudio.com | Paketleri indirme konumu Kurulumu |
| DL.xamarin.com | Paketleri indirme konumu Kurulumu |
| visualstudiogallery.msdn.microsoft.com | Visual Studio uzantıları konumu indirin |
| www.VisualStudio.com | Belge konumu |
| docs.microsoft.com | Belge konumu |
| MSDN.microsoft.com | Belge konumu |
| www.microsoft.com | Belge konumu |
| *.windows.net | Oturum açma konumu |
| *.microsoftonline.com | Oturum açma konumu |
| *.live.com | Oturum açma konumu |


## <a name="non-microsoft-domains"></a>Microsoft olmayan etki alanları
| Etki Alanı | Bu iş yükleri yükler |
| ------ | ------- |
| Archive.apache.org |  JavaScript ile Mobil Geliştirme <br />(Cordova) |
| cocos2d x.org | C++ ile oyun geliştirme <br />(Cocos) |
| download.epicgames.com | C++ ile oyun geliştirme <br />(Unreal Engine) |
| download.Oracle.com | JavaScript ile Mobil Geliştirme <br />(Java SDK'sı) <br /><br />.NET ile Mobil Geliştirme <br />(Java SDK'sı) |
| download.unity3d.com | Unity ile oyun geliştirme <br />(Unity) |
| netstorage.unity3d.com | Unity ile oyun geliştirme <br /> (Unity) |
| DL.Google.com | JavaScript ile Mobil Geliştirme <br />(Android SDK ve NDK, öykünücüsü) <br /><br />.NET ile Mobil Geliştirme <br />(Android SDK ve NDK, öykünücüsü) |
| www.incredibuild.com | C++ ile oyun geliştirme <br />(IncrediBuild) |
| incredibuildvs2017i.azureedge.NET | C++ ile oyun geliştirme <br />(IncrediBuild) |
| www.Python.org | Python geliştirme <br />(Python) <br /><br />Veri bilimi ve analitik uygulamalar <br />(Python) |

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.
* [Visual Studio 2017 yükleyin](install-visual-studio.md)
* [Visual Studio 2017 yüklemek için komut satırı parametreleri kullanın](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
  * [İş yükü ve bileşen kimliği başvurusu](workload-and-component-ids.md)
* [Visual Studio 2017 ağ tabanlı yüklemesini oluşturma](create-a-network-installation-of-visual-studio.md)
  * [Visual Studio çevrimdışı yükleme için gerekli sertifikaları yükleyin](install-certificates-for-visual-studio-offline.md)
* [Visual Studio yükleme yanıt dosyası ile otomatikleştirme](automated-installation-with-response-file.md)
* [Visual Studio'yu dağıtırken ürün anahtarlarını otomatik olarak Uygula](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Visual Studio 2017 Kurumsal dağıtımlar için Varsayılanlarını Ayarla](set-defaults-for-enterprise-deployments.md)
* [Devre dışı bırakmak veya paket önbellek taşıma](disable-or-move-the-package-cache.md)
* [Visual Studio ağ tabanlı yüklemesini güncelleştirme](update-a-network-installation-of-visual-studio.md)
* [Visual Studio 2017 dağıtımları denetim güncelleştirmeleri](controlling-updates-to-visual-studio-deployments.md)
* [Algılama ve Visual Studio Örnekleri yönetmek için Araçlar](tools-for-managing-visual-studio-instances.md)
