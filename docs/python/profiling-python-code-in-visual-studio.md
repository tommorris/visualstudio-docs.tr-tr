---
title: Python kodu performansını ölçme
description: Kod Python performansını denetlemek için Visual Studio profil oluşturucu kullanmak için nasıl ne zaman usnig CPython tabanlı yorumlayıcılar.
ms.date: 01/09/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 2f0bd25221f975cd8df122af51af20d125a43a65
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
ms.locfileid: "31584080"
---
# <a name="profiling-python-code"></a>Python kodu profili oluşturma

Python uygulama CPython tabanlı yorumlayıcılar kullanırken profil. (Bkz [özellikleri matris - profil](overview-of-python-tools-for-visual-studio.md#matrix-profiling) bu özellik, Visual Studio'nun farklı sürümleri için kullanılabilirliği.)

Profil oluşturma ile başlatıldığında **Çözümle > başlatma Python profil** yapılandırma iletişim kutusu açılır menü komutu:

![Profil oluşturma yapılandırma iletişim kutusu](media/profiling-start.png)

Seçtiğinizde, **Tamam**, profil oluşturucu çalıştırır ve üzerinden araştırmanız uygulamada harcanan zamanı nasıl bir performans raporu açar:

![Profil oluşturma performans raporu](media/profiling-results.png)

|   |   |
|---|---|
| ![video kamera simgesine film](../install/media/video-icon.png "bir videoyu izleyin") | [(Microsoft Virtual Academy) bir video izlemek](https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567) (3 m 00s) profil Python tanıtımı için.|

> [!Note]
> Günümüzde, Visual Studio tam uygulama profili oluşturma yalnızca bu düzeyde destekler, ancak kesinlikle özellikler gelecekte Geri bildiriminizi duymak istiyoruz. Kullanım [ **ürün geri bildirim verin** düğmesini](#feedback) bu sayfanın sonundaki.

## <a name="profiling-for-ironpython"></a>IronPython için profil oluşturma

IronPython CPython tabanlı yorumlayıcı olmadığı için yukarıdaki Profil özelliği çalışmıyor.

Bunun yerine, Visual Studio .NET başlatarak Profiler kullanarak `ipy.exe` doğrudan hedef uygulama, başlangıç betiği başlatmak için uygun bağımsız değişkenler kullanılarak. Dahil `-X:Debug` komut satırında, Python tümünün emin olmak için kod hata ayıklaması profili ve. Bu bağımsız değişken hem IronPython çalışma zamanı ve size kod harcanan süre dahil olmak üzere bir performans raporu oluşturur. Kodunuzu karıştırılmış adları kullanılarak tanımlanır.

Alternatif olarak, bazı kendi yerleşik profil IronPython sahiptir ancak şu anda daha iyi hiçbir Görselleştirici yoktur. Bkz: [bir IronPython profil oluşturucu](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (MSDN bloglarında) için kullanılabilir.