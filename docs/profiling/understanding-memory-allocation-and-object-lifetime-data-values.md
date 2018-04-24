---
title: Bellek ayırma ve nesne yaşam verisi değerlerini anlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- .NET memory profiling method
- Profiling Tools, .NET memory method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9b7569b36b954553dbb03e8a3934c375012a4349
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="understanding-memory-allocation-and-object-lifetime-data-values"></a>Bellek Ayırma ve Nesne Yaşam Verisi Değerlerini Anlama

*.NET bellek ayırma* profili oluşturma yöntemi, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] profil oluşturma araçları boyut ve bir ayırma oluşturulan veya bir atık toplama zarar nesnelerin sayısı ve ek hakkında bilgi toplar işlevi hakkında bilgi *çağrı yığını* zaman olayı oluştu. A *çağrı yığını* işlemci yürütülen işlevler hakkında bilgi depolar dinamik bir yapıdır.

Bellek profil oluşturucuyu bir .NET Framework nesnesinin profili uygulamadaki her ayırma bilgisayar işlemci keser. Nesne yaşam verisi ayrıca toplandığında, profil oluşturucu işlemci her .NET Framework atık toplama sonra kesintiye uğratır. Veriler, her nesne türü ve her profili işlevi için toplanır.

## <a name="allocation-data"></a>Ayırma veri

.Memory olay ortaya çıktığında, toplam sayıları ve boyutları ayrılmış veya yok bellek nesnelerin artırılır.

.Memory ayırma olay ortaya çıktığında, profil oluşturucu çağrı yığınında her işlevi örnek sayısını artırır. Veri toplandığında, çağrı yığınında yalnızca bir işlevi kodu kendi işlev gövdesi gerçekleştirmektedir. Diğer yığında döndürülecek olarak adlandırılan işlevleri için bekleyen işlev çağrılarını hiyerarşideki üst işlevlerdir.

- Profil Oluşturucu artışlarla ayırma olayı için *özel* örnek kendi yönergeleri yürütülmekte işlevi sayısı. Özel bir örnek de toplam parçası olduğundan (*dahil*) örnekleri işlevinin, şu anda etkin işlevi (bunlar dahil) örnek sayısı da artar.

- Profil Oluşturucu diğer işlevleri çağrı yığınında kapsayıcı örnek sayısını artırır.

## <a name="lifetime-data"></a>Yaşam verisi

.NET Framework Atık toplayıcısının ayırma ve sürüm, uygulamanız için bellek yönetir. Atık toplayıcının performansını optimize etmek için, yönetilen yığın üç nesle ayrılır: 0, 1 ve 2. Çalışma zamanı 's Atık toplayıcısının yeni nesneler kuşak 0 depolar. Koleksiyonları varlığını sürdürmesini nesneleri yükseltilmiş ve nesil 1 ve 2 depolanır.

Çöp toplayıcı, tüm nesil nesnelerin ayırmasını kaldırma bellek geri kazanır. Profili uygulama oluşturulan nesneler için nesne ömrü görünümü sayısına ve boyutuna nesnelerin ve zaman kazanılır nesil görüntüler.