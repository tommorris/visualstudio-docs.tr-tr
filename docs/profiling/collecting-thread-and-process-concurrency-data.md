---
title: İş parçacığı ve işlem eşzamanlılık verileri toplama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- concurrency profiling method
- Profiling Tools, concurrency method
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 424675726dd91664923cde0a3a5ad5573d51b4d5
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2018
---
# <a name="collect-thread-and-process-concurrency-data"></a>İş parçacığı ve işlem eşzamanlılık verileri toplama

Visual Studio profil oluşturma araçları eşzamanlılık profili oluşturma yöntemi, bir işlev bir kaynağa erişim için beklenecek profili uygulama neden olan her eşitleme olay hakkında bilgi içerir kaynak çakışması veri toplamanıza olanak sağlar.

Aşağıdaki yordamlardan birini kullanarak profili oluşturma yöntemi eşzamanlılık belirtebilirsiniz:

- Profil Oluşturma Sihirbazı'nın ilk sayfasında, tıklatın **eşzamanlılık**
- Üzerinde **genel** sayfa performans oturumu için Özellikler iletişim kutusunda tıklatın **eşzamanlılık**.
- Üzerinde **performans Gezgini** araç, **yöntemi** tıklatın **eşzamanlılık**.

## <a name="common-tasks"></a>Ortak görevler

Ek seçenekler belirtebilirsiniz *Performans oturumunu *** özellik sayfaları** performans oturumunun iletişim kutusu. Bu iletişim kutusunu açmak için:

- İçinde **performans Gezgini**, performans oturumu adına sağ tıklayın ve ardından **özellikleri**.

Aşağıdaki tabloda yer alan görevler, belirtebilirsiniz seçenekleri açıklanmıştır *Performans oturumunu *** özellik sayfaları** eşzamanlılık yöntemi kullanarak profil, iletişim kutusu.

|Görev|İlgili içerik|
|----------|---------------------|
|Üzerinde **genel** sayfasında, oluşturulan profil oluşturma veri (.vsp) dosyası adlandırma ayrıntılarını belirtin.|- [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|
|Üzerinde **başlatma** sayfasında, birden çok .exe proje kodunu çözümünüzde varsa başlatmak için uygulama belirtin.|- [Nasıl yapılır: başlatmak için ikili belirtin](../profiling/how-to-specify-the-binary-to-start.md)|
|Üzerinde **katman etkileşim** sayfasında, çalıştırmak profil ADO.NET çağrısı veri ekleyin.|- [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|
|Üzerinde **Windows sayaçları** sayfasında, profil oluşturma verileri işaretleri olarak eklemek için bir veya daha fazla işletim sistemi performans sayaçları belirtin.|- [Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)|
|Üzerinde **Gelişmiş** sayfasında, birden çok sürümü, uygulama modülleri kullanırsanız, .NET Framework çalışma zamanı profiline sürümünü belirtin. Varsayılan olarak yüklenen ilk sürüm profili.|- [Nasıl yapılır: .NET Framework çalışma zamanı belirtin](../profiling/how-to-specify-the-dotnet-framework-runtime.md)|