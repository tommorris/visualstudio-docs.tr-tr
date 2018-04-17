---
title: Bilinen sorunlar kapsayıcıları için | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2017
ms.technology:
- vs-acquisition
ms.topic: conceptual
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4052be27d5be1298f78c3e736fd5039cf69f7c07
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="known-issues-for-containers"></a>Kapsayıcıları için bilinen sorunlar

Visual Studio Docker kapsayıcıya yüklerken bazı sorunlar vardır.

## <a name="windows-container"></a>Windows kapsayıcısı

Aşağıdaki bilinen sorunlar, Visual Studio derleme araçları 2017 Windows kapsayıcıya yüklediğinizde oluşur.

* Görüntü microsoft/windowsservercore:10.0.14393.1593 üzerinde dayalı bir kapsayıcı Visual Studio yükleyemiyor. Daha eski veya yeni Windows sürümleri ile etiketlenmiş görüntü çalışması gerekir.
* Windows SDK sürümleri 10.0.14393 eski yükleyemezsiniz. Bazı paketler yüklenemedi ve bu paketlere bağımlı iş yükleri çalışmaz.
* Geçmesi gereken `-m 2GB` (veya daha fazla) görüntüyü oluştururken. Bazı iş yükleri varsayılandan daha fazla bellek gerektirir 1 yüklendiğinde GB.
* Docker varsayılandan büyük diskleri kullanacak şekilde yapılandırmalısınız 20 GB.
* Geçmesi gereken `--norestart` komut satırında. Bu yazma olduğu gibi bir Windows kapsayıcı içinden yeniden başlatılmaya çalışılıyor kapsayıcı döndürür `ERROR_TOO_MANY_OPEN_FILES` ana bilgisayara.

## <a name="build-tools-container"></a>Araçlar kapsayıcı oluşturma

Derleme araçları kapsayıcı kullandığınızda, aşağıdaki bilinen sorunlar ortaya çıkabilir. Diğer bilinen bir sorun varsa ziyaret edin veya sorunlar giderildi olup olmadığını görmek için https://developercommunity.visualstudio.com.

* IntelliTrace çalışmayabilir [bazı senaryolar](https://github.com/Microsoft/vstest/issues/940) bir kapsayıcıdaki.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı, bize yükleme Yardımı (yalnızca İngilizce) için canlı sohbet tarafından başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfası](https://www.visualstudio.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:
* Ürün sorunları bize bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem Visual Studio Yükleyicisi ve Visual Studio IDE görünür aracı.
* Üzerinde bir ürün önerisi bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun.
* ABD ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio).  (Bu seçenek gerektiren bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Derleme Araçlarını Bir Kapsayıcıya Yükleme](build-tools-container.md)
* [Kapsayıcılar için İleri Düzey Örnek](advanced-build-tools-container.md)
* [Visual Studio derleme araçları 2017 iş yükü ve Bileşen kimlikleri](workload-component-id-vs-build-tools.md)
