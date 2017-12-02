---
title: "Visual Studio'da Python kodu performansını ölçmek | Microsoft Docs"
ms.custom: 
ms.date: 07/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 1f873ab7b8954f9ac8ebf089a3719e34be8e03ba
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2017
---
# <a name="profiling-python-code"></a>Python kodu profili oluşturma

Visual Studio CPython tabanlı yorumlayıcılar kullanırken bir Python uygulaması profil destekler.

Profil oluşturma ile başlatıldığında **Çözümle > başlatma Python profil** yapılandırma iletişim kutusu açılır menü komutu:

![Profil oluşturma yapılandırma iletişim kutusu](media/profiling-start.png)

Seçtiğinizde, **Tamam**, profil oluşturucu çalıştırır ve üzerinden araştırmanız uygulamada harcanan zamanı nasıl bir performans raporu açar:

![Profil oluşturma performans raporu](media/profiling-results.png)

Video tanıtımı için bkz [profil Python](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=hb46k6LWE_405918567) (Microsoft Virtual Academy, 3m00s).

> [!VIDEO https://mva.microsoft.com/en-US/training-courses-embed/python-tools-for-visual-studio-2017-18121/Video-Testing-Python-hb46k6LWE_405918567]


## <a name="profiling-for-ironpython"></a>IronPython için profil oluşturma

IronPython CPython tabanlı yorumlayıcı olmadığı için yukarıdaki Profil özelliği çalışmıyor.

Bunun yerine, Visual Studio .NET başlatarak Profiler kullanarak `ipy.exe` doğrudan hedef uygulama, başlangıç betiği başlatmak için uygun bağımsız değişkenler kullanılarak. Dahil `-X:Debug` tüm debuggable ve profilable olmasını Python kodunuzu zorlamak için komut satırında. Bu bağımsız değişken hem IronPython çalışma zamanı ve size kod harcanan süre dahil olmak üzere bir performans raporu oluşturur. Kodunuzu karıştırılmış adları kullanılarak tanımlanır.

Alternatif olarak, bazı kendi yerleşik profil IronPython sahiptir ancak şu anda daha iyi hiçbir Görselleştirici yoktur. Bkz: [bir IronPython profil oluşturucu](http://blogs.msdn.com/b/curth/archive/2009/03/29/an-ironpython-profiler.aspx) (MSDN bloglarında) için kullanılabilir.