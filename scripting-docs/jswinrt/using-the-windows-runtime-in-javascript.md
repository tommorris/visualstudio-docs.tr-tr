---
title: "Windows çalışma zamanı JavaScript kullanma | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c81f5d83056ceb87987e263f09c0d5e5017dbb6f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="using-the-windows-runtime-in-javascript"></a>Windows çalışma zamanı JavaScript kullanma
Evrensel Windows Platformu (UWP) uygulamasını yazarken yerel JavaScript nesneleri, yöntemleri ve özellikleri kullanırsınız benzer şekilde Windows çalışma zamanı sınıfları, yöntemleri ve özellikleri kullanabilirsiniz. Bu konu, giriş bilgilerini ve nasıl Windows çalışma zamanı türleri, zaman uyumsuz Windows çalışma zamanı yöntemlerinin nasıl temsil edildiğini bir açıklama da dahil olmak üzere JavaScript'te Windows çalışma zamanı API'lerini kullanarak temel kavramları açıklayan konulara bağlantılar sağlar, ve dinleyecek ve Windows çalışma zamanı olayları işlemek nasıl.  
  
 JavaScript başvurusu belgeleri bulabilirsiniz [JavaScript dil başvurusu](../javascript/javascript-language-reference.md).  
  
> [!IMPORTANT]
>  Windows çalışma zamanı özellikleri, Internet Explorer'da çalışan uygulamalar kullanılabilir değil.  
  
## <a name="windows-runtime-reference-documentation"></a>Windows çalışma zamanı başvuru belgeleri  
 Başvuru belgelerine bakın [Windows çalışma zamanı başvurusu](https://msdn.microsoft.com/en-us/library/windows/apps/br211377.aspx). Kod örnekleri, JavaScript ve ayrıca C++, C# ve Visual Basic kullanılabilir.  
  
## <a name="writing-windows-runtime-components-in-c-c-or-visual-basic"></a>C++, C# veya Visual Basic'te yazma Windows çalışma zamanı bileşenleri  
 Yönergeler ve tüketilebilir Windows çalışma zamanı bileşenleri JavaScript'te yazma yönergeleri için bkz: [C++'da Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp) ve [C# ve Visual Windows çalışma zamanı bileşenleri oluşturma Temel](/windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic).  
  
## <a name="casing-conventions-with-windows-runtime-features"></a>Windows çalışma zamanı özellikleri ile büyük/küçük harf kuralları  
 JavaScript'te Windows çalışma zamanı özellikleri için büyük/küçük harf kuralları diğer diller için kullanılanlardan biraz farklılık gösterir:  
  
-   Ad alanları ve sınıfları Pascal durumda şunlardır:  
  
    ```JavaScript  
    Windows.Deployment.PackageInfo;  
    ```  
  
-   Sınıfları, yöntemleri ve özellikleri ve yapılar ve numaralandırmalar, üyeleri de dahil olmak üzere üyeleri ortası büyük şunlardır:  
  
    ```JavaScript  
    Deployment.PackageInfo.createPackage();  
    ```  
  
-   Olay adları küçük harf olarak şunlardır:  
  
    ```JavaScript  
    dataTransferManager.ontargetapplicationchosen;  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows çalışma zamanı API kullanmayla ilgili konular](../jswinrt/considerations-when-using-the-windows-runtime-api.md)   
 [Windows çalışma zamanı zaman uyumsuz yöntemler kullanma](../jswinrt/using-windows-runtime-asynchronous-methods.md)   
 [JavaScript'te Windows çalışma zamanı olayları işleme](../jswinrt/handling-windows-runtime-events-in-javascript.md)   
 [Windows çalışma zamanı türleri JavaScript gösterimi](../jswinrt/javascript-representation-of-windows-runtime-types.md)   
 [Windows çalışma zamanı DateTime ve TimeSpan JavaScript projeksiyonu](../jswinrt/windows-runtime-datetime-and-timespan-representations.md)