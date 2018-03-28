---
title: Visual Studio'da Python kodu performansını ölçmek | Microsoft Docs
description: Kod Python performansını denetlemek için Visual Studio profil oluşturucu kullanmak için nasıl ne zaman usnig CPython tabanlı yorumlayıcılar.
ms.custom: ''
ms.date: 01/09/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 4faa050056296b7dde625268c7ff1112b2c0c6c0
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
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