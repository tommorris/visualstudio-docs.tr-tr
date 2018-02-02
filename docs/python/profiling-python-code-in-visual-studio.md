---
title: "Visual Studio'da Python kodu performansını ölçmek | Microsoft Docs"
description: "Kod Python performansını denetlemek için Visual Studio profil oluşturucu kullanmak için nasıl ne zaman usnig CPython tabanlı yorumlayıcılar."
ms.custom: 
ms.date: 01/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: 
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
ms.openlocfilehash: 7f9fb355d35a5c2dcebff6fc1c94c52234e672a0
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="profiling-python-code"></a>Python kodu profili oluşturma

Visual Studio CPython tabanlı yorumlayıcılar kullanırken bir Python uygulaması profil destekler.

Profil oluşturma ile başlatıldığında **Çözümle > başlatma Python profil** yapılandırma iletişim kutusu açılır menü komutu:

![Profil oluşturma yapılandırma iletişim kutusu](media/profiling-start.png)

Seçtiğinizde, **Tamam**, profil oluşturucu çalıştırır ve üzerinden araştırmanız uygulamada harcanan zamanı nasıl bir performans raporu açar:

![Profil oluşturma performans raporu](media/profiling-results.png)

Video tanıtımı için bkz [profil Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=s6FoC6LWE_1005918567) (Microsoft Virtual Academy, 3m00s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Profiling-Python-s6FoC6LWE_1005918567]

## <a name="profiling-for-ironpython"></a>IronPython için profil oluşturma

IronPython CPython tabanlı yorumlayıcı olmadığı için yukarıdaki Profil özelliği çalışmıyor.

Bunun yerine, Visual Studio .NET başlatarak Profiler kullanarak `ipy.exe` doğrudan hedef uygulama, başlangıç betiği başlatmak için uygun bağımsız değişkenler kullanılarak. Dahil `-X:Debug` komut satırında, Python tümünün emin olmak için kod hata ayıklaması profili ve. Bu bağımsız değişken hem IronPython çalışma zamanı ve size kod harcanan süre dahil olmak üzere bir performans raporu oluşturur. Kodunuzu karıştırılmış adları kullanılarak tanımlanır.

Alternatif olarak, bazı kendi yerleşik profil IronPython sahiptir ancak şu anda daha iyi hiçbir Görselleştirici yoktur. Bkz: [bir IronPython profil oluşturucu](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (MSDN bloglarında) için kullanılabilir.