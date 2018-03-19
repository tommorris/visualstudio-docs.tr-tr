---
title: "Yük testi API'si Visual Studio'da | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- code, load tests
- plug-ins, load test
- APIs, load tests
ms.assetid: e15567bc-1f21-4feb-b81d-f17ba35cfde5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 4cb66166b65ae93d75cee50efa6a677a5ea61cc2
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-use-the-load-test-api"></a>Nasıl yapılır: Yük Testi API'si Kullanma

Visual Studio Yük testi denetlemek veya bir yük testi geliştirmek eklentileri destekler. Yük testi eklentileri kullanıcı tanımlı sınıflardır uygulayan <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> arabirimi bulunan <xref:Microsoft.VisualStudio.TestTools.LoadTesting> ad alanı. Yük testi eklentileri, özel yük testi denetimi için gibi bir sayaç veya hata eşiği karşılandığında bir yük testi denetimlerine imkan tanır. Özellikleri kullanın <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest> almak veya kullanıcıdan yükleme testi parametrelerini ayarlamak için sınıf tanımlanan kodu. Olayları kullanın <xref:Microsoft.VisualStudio.TestTools.LoadTesting.LoadTest> yük testi çalışırken bildirimlere temsilciler iliştirmek için sınıf.

> [!TIP]
> İncelemek için nesne tarayıcısı kullanın <xref:Microsoft.VisualStudio.TestTools.LoadTesting> ad alanı. Visual C# ve Visual Basic düzenleyicileri ad alanındaki sınıflar ile kodlamak için IntelliSense desteği sunar.

Web performans testleri için eklentileri de oluşturabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Web performans testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md) ve [nasıl yapılır: istek düzeyi eklentisi oluşturma](../test/how-to-create-a-request-level-plug-in.md).

## <a name="to-use-the-loadtesting-namespace"></a>LoadTesting ad alanını kullanmak için

1.  Bir Web performansı ve yük testi içeren bir yük testi projesi açın.

2.  Visual C# veya Visual Basic sınıf kitaplığı proje test çözümünüze ekleyin.

3.  Bir başvuru sınıf kitaplığı projesi için Web performansı ve yük testi projeye ekleyin.

4.  Sınıf kitaplığı projesinde Microsoft.VisualStudio.QualityTools.LoadTestFramework DLL için bir başvuru ekleyin.

5.  Sınıf kitaplığı projesinde bulunan sınıf dosyasında eklemek bir `using` bildirimi <xref:Microsoft.VisualStudio.TestTools.LoadTesting> ad alanı.

6.  Uygulayan ortak bir sınıf oluşturun <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin> arabirimi.

7.  Projeyi oluşturun.

8.  Yeni Yük testi Yük Testi Düzenleyicisini kullanarak eklentisini ekleyin:

    1.  Yük testi kök düğümünü sağ tıklatın ve ardından **Yük Testi Eklentisi Ekle**.

    2.  **Yük Testi Eklentisi Ekle** iletişim kutusu görüntülenir.

    3.  Seçili eklenti bölmesinde özelliklerini çalışma zamanında kullanmak eklenti için başlangıç değerlerini ayarlayın.

        > [!NOTE]
        > Eklentilerinizi istediğiniz sayıda özellikler getirebilir. Yalnızca bunları ortak, ayarlanabilir ve tamsayı, Boole veya dize gibi bir temel türden yapın. Daha sonra Özellikler penceresini kullanarak yük testi eklentisi özelliklerini de düzenleyebilirsiniz.

9. Yük testi çalıştırın.

     Bir uygulama için <xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>, bkz: [nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md).

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.LoadTesting>
- [Özel kod ve eklentiler yük testleri için oluşturma](../test/create-custom-code-and-plug-ins-for-load-tests.md)
- [Nasıl yapılır: Web başarım testi API'si kullanma](../test/how-to-use-the-web-performance-test-api.md)
- [Nasıl yapılır: yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md)