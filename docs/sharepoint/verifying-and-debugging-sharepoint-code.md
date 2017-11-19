---
title: "Doğrulama ve SharePoint kodda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- unit testing [SharePoint development in Visual Studio]
- IntelliTrace [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, IntelliTrace
- SharePoint development in Visual Studio, unit testing
ms.assetid: b5f3bce2-6a51-41b1-a292-9e384bae420c
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8ab25807ffaf62773b6c02f22c548fb5e5c769ff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="verifying-and-debugging-sharepoint-code"></a>SharePoint Kodunu Doğrulama ve Hata Ayıklama
  IntelliTrace ve birim testi kullanarak, daha kolay SharePoint çözümlerini hata ayıklama ve bunları her bir yöntemin düzgün çalıştığından emin olun. SharePoint projeleri için bu özellikleri kullanan [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] diğer proje türleri için aynı yordamları izleyerek.  
  
## <a name="intellitrace"></a>IntelliTrace  
 IntelliTrace kullanarak, yalnızca geçerli durumu, SharePoint çözüm aynı zamanda geçmiş ve gerçekleşen bağlam oluşan olaylarla belirleyebilirsiniz. Çeşitli noktalara zamanında olaylarının nerede kaydedilmiş bir SharePoint çözüm içinde ileri ve geri gidin ve durumları ve her noktada değişkenlerin değerleri gözden geçirin. Bu dinamik Gezinti kullanarak, daha hızlı ve kolay bir şekilde SharePoint çözümlerini çok sayıda kesme noktalarını ayarlayın gerek kalmadan ayıklayabilirsiniz. Ayrıca hata ayıklama oturumu bir IntelliTrace günlüğü (.iTrace) dosyasına kaydedin, daha sonra Visual Studio Ultimate'ta açın ve sonrası crash hata ayıklama gerçekleştirin. Böylece hatalara neden çıkışı daha kolay hesaplayabilir .iTrace dosyanın ne zaman ve nerede belirli SharePoint hataları oluştu hakkında ayrıntılı bilgi içerir. .İTrace dosyasındaki bilgiler Birleşik Günlük sistem (ULS) SharePoint oluşturur tam hata günlüğü bir alt kümesidir. Bu bilgiler SharePoint'e bir kullanıcı profili açık veya kapalı gibi ve özelliklerini bir SharePoint Proje yüklenir, okuma, veya değiştirildiğinde, belirli olayları içerir. IntelliTrace kayıtları olayları yapılandırabilirsiniz. Daha fazla bilgi için bkz: [IntelliTrace verilerini kaydedilmiş kullanma](/visualstudio/debugger/using-saved-intellitrace-data) ve [yapılandırma IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
 SharePoint'te bir hata ortaya çıkarsa, söz konusu hatayla için bir "bağıntı kimliği" tanımlayıcı hata iletişim kutusu görüntüler. .İTrace dosyasında listelenen olaylarından bağıntı kimlikleri de alabilirsiniz. Verilen bağıntı Kimliğine sahip olayları tümünün listesini görüntülemek için Kimliğinde girebilirsiniz **analiz** IntelliTrace Özet sayfasını bölümü. Bu bölümde, yalnızca oluşan olaylarla adlarını veya işlev adı, çıkış ve giriş noktaları, parametreler ve dönüş değerleri gibi kendi çağrısı bilgilerle birlikte olayların adları görüntülenip görüntülenmeyeceğini seçebilirsiniz.  
  
 Visual Studio olayları seçerek IntelliTrace elde edebilirsiniz **F5** anahtarı. SharePoint'e özgü olaylar almak için ancak, SharePoint çözümlerinde IntelliTrace verilerini Microsoft Monitoring Agent'ı kullanarak toplamanız gerekir. Bu araç, IntelliTrace verilerini toplar ve Visual Studio dışında dağıtılan uygulamalar için .iTrace dosyaları oluşturur. Daha fazla bilgi için bkz: [IntelliTrace özellikleri](/visualstudio/debugger/intellitrace-features) ve [IntelliTrace tek başına toplayıcıyı kullanma](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector).  
  
## <a name="unit-testing"></a>Birim testi  
 Hata, yazma ve test yöntemleri içinde test kod çalıştırma birim testi, gerçekleştirerek kodunuzu daha kolay bulabilirsiniz. Bu yöntem boş değişkenleri ve mantık ve SharePoint nesne modelini temel alan projenizi işlevselliğini doğrulamak için kullanabileceğiniz bir onay deyimi içerir. Daha fazla bilgi için bkz: [Birim Test kodunuzu](/visualstudio/test/unit-test-your-code).  
  
### <a name="support-for-microsoft-fakes-framework"></a>Microsoft Fakes Framework Desteği  
 SharePoint projeleri desteği, .NET Framework temel alınarak uygulamalarda saplamalar ve dolgular temsilci tabanlı oluşturabilirsiniz bir yalıtım Framework Microsoft Fakes sınayın. Fakes framework kullanarak oluşturmak, korumanıza ve sahte uygulamaları için birim testleri ekleme. Bu saplamalar ve dolgular ortamından birim testleri yalıtma. Korumalı olmayan sınıfları veya arabirimleri ile geçersiz kılınabilir yöntemleri tüketir kodu test etmek için yer tutucular oluşturabilirsiniz. Bir alternatif dolgu uygulanması için sabit kodlanmış çağrıları sealed sınıfları statik veya kılınamaz yöntemleriyle yönlendirmek için dolgular oluşturabilirsiniz. Ayrıca temsilciler saplama türlerini ve dolgusu türleri ile dinamik olarak tek tek saplama üyeleri davranışını özelleştirmek için kullanabilirsiniz. Daha fazla bilgi için bkz: [yalıtma kodu altında Microsoft Fakes ile Test](/visualstudio/test/isolating-code-under-test-with-microsoft-fakes).  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[IntelliTrace](/visualstudio/debugger/intellitrace)|IntelliTrace'i kullanarak Visual Studio çözümleri daha kolay hata ayıklama açıklar.|  
|[İzlenecek yol: IntelliTrace'i kullanarak SharePoint uygulama hata ayıklama](../sharepoint/walkthrough-debugging-a-sharepoint-application-by-using-intellitrace.md)|Bulunacak gösterilmiştir IntelliTrace'i kullanarak SharePoint Proje hatalarını kodlama.|  
|[Kodunuza birim testi](/visualstudio/test/unit-test-your-code)|Birim testleri kullanarak kodunuzda mantık hataları bulmak açıklar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kod kalitesini geliştirme](/visualstudio/test/improve-code-quality)  
  
  