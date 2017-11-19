---
title: "Bilinen sorunlar kapsayıcıları için | Microsoft Docs"
ms.custom: 
ms.date: 10/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: heaths
manager: ghogen
ms.openlocfilehash: 75825d368d0098c466c44a23fa18ac1af7b06e64
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2017
---
# <a name="known-issues-for-containers"></a>Kapsayıcıları için bilinen sorunlar

Var. birkaç Visual Studio Docker kapsayıcıya yüklerken verir.

## <a name="windows-container"></a>Windows kapsayıcısı

Aşağıdaki bilinen sorunlar, Visual Studio derleme araçları 2017 Windows kapsayıcıya yüklediğinizde oluşur.

* Görüntü microsoft/windowsservercore:10.0.14393.1593 üzerinde dayalı bir kapsayıcı Visual Studio yükleyemiyor. Daha eski veya yeni Windows sürümleri ile etiketlenmiş görüntü çalışması gerekir.
* Windows SDK sürümleri 10.0.14393 eski yükleyemezsiniz. Bazı paketler yüklenemedi ve bu paketlere bağımlı iş yükleri çalışmaz.
* Geçmesi gereken `-m 2GB` (veya daha fazla) görüntüyü oluştururken. Bazı iş yükleri varsayılandan daha fazla bellek gerektirir 1 yüklendiğinde GB.
* Docker varsayılandan büyük diskleri kullanacak şekilde yapılandırmalısınız 20 GB.
* Geçmesi gereken `--norestart` komut satırında. Bu yazma olduğu gibi bir Windows kapsayıcı içinden yeniden başlatılmaya çalışılıyor kapsayıcı döndürür `ERROR_TOO_MANY_OPEN_FILES` ana bilgisayara.

## <a name="build-tools-container"></a>Araçlar kapsayıcı oluşturma

Derleme araçları kapsayıcı kullandığınızda, aşağıdaki bilinen sorunlar ortaya çıkabilir. Sorunlar giderildi olup olmadığını veya diğer bilinen sorunlar olup olmadığını görmek için https://developercommunity.visualstudio.com ziyaret edin.

* IntelliTrace çalışmayabilir [bazı senaryolar](https://github.com/Microsoft/vstest/issues/940) bir kapsayıcıdaki.

## <a name="get-support"></a>Destek alma
Bazı durumlarda, şeyler yanlış gidebilirsiniz. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sorun giderme ipuçları için sayfa. Ürün sorunları bize de bildirebilirsiniz [bir sorun bildirmek](../ide/how-to-report-a-problem-with-visual-studio-2017.md) aracı Visual Studio IDE içinde veya üzerinde bir öneri bizimle paylaşın [UserVoice](https://visualstudio.uservoice.com/forums/121579). Ürün sorunları izleyebilir [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/), soru sorun ve yanıtlarını bulun. Bize ve diğer Visual Studio geliştiriciler aracılığıyla devreye bizim [Gitter topluluk Visual Studio konuşmada](https://gitter.im/Microsoft/VisualStudio) (gerektiren bir [GitHub](https://github.com/) hesabı).

## <a name="see-also"></a>Ayrıca bkz.

* [Bir kapsayıcıya derleme araçlarını yükleme](build-tools-container.md)
* [Gelişmiş örnek kapsayıcıları için](advanced-build-tools-container.md)
