---
title: "Visual Studio'da Python kodu performansını ölçmek | Microsoft Docs"
description: "Kod Python performansını denetlemek için Visual Studio profil oluşturucu kullanmak için nasıl ne zaman usnig CPython tabanlı yorumlayıcılar."
ms.custom: 
ms.date: 01/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: 
ms.topic: article
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 0faae917aba237a85c6a01743d89cf66adf06296
ms.sourcegitcommit: a07b789cc41ed72664f2c700c1f114476e7b0ddd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
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

## <a name="profiling-for-ironpython"></a>IronPython için profil oluşturma

IronPython CPython tabanlı yorumlayıcı olmadığı için yukarıdaki Profil özelliği çalışmıyor.

Bunun yerine, Visual Studio .NET başlatarak Profiler kullanarak `ipy.exe` doğrudan hedef uygulama, başlangıç betiği başlatmak için uygun bağımsız değişkenler kullanılarak. Dahil `-X:Debug` komut satırında, Python tümünün emin olmak için kod hata ayıklaması profili ve. Bu bağımsız değişken hem IronPython çalışma zamanı ve size kod harcanan süre dahil olmak üzere bir performans raporu oluşturur. Kodunuzu karıştırılmış adları kullanılarak tanımlanır.

Alternatif olarak, bazı kendi yerleşik profil IronPython sahiptir ancak şu anda daha iyi hiçbir Görselleştirici yoktur. Bkz: [bir IronPython profil oluşturucu](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (MSDN bloglarında) için kullanılabilir.