---
title: 'Nasıl yapılır: hata ayıklama için .NET Framework sürümünü belirtin. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- .NET Framework, specifying version for debugging
- debugging [Visual Studio], specifying .NET Framework version
ms.assetid: 7a4893ba-4620-4774-893f-378d4ca28893
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 2cb8da54b53814e7f044c67855e8071c627cf2e1
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
---
# <a name="how-to-specify-a-net-framework-version-for-debugging"></a>Nasıl Yapılır: Hata Ayıklama İçin .NET Framework Sürümü Belirtme
[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] Hata ayıklayıcı destekleyen Microsoft eski sürümleri hata ayıklama [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] geçerli sürümü yanı sıra. Visual Studio'dan bir uygulama başlatırsanız, hata ayıklayıcı doğru sürümü her zaman tanımlayabilirsiniz [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] ayıkladığınız uygulama için. Uygulama zaten çalışıyor ve kullanıyorsanız **ekleme**, hata ayıklayıcı her zaman daha eski bir sürümü belirlemek mümkün olmayabilir [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Bu durumda, bildiren bir hata iletisi alırsınız,  
  
 Hata ayıklayıcı hakkında yanlış varsayılır yaptı [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sürümü kullanmak için uygulamanızı geçiyor.  
  
 Bu nadir durumlarda, hata ayıklayıcı için hangi sürümün kullanılacağını belirtmek için bir kayıt defteri anahtarı ayarlayabilirsiniz.  
  
### <a name="to-specify-a-net-framework-version-for-debugging"></a>Hata ayıklama için .NET Framework sürüm belirtmek için  
  
1.  Dizin makinenize yüklü .NET Framework sürümlerini bulmak için Windows\Microsoft.NET\Framework bakın. Sürüm numaraları aşağıdaki gibi görünmelidir:  
  
     `V1.1.4322`  
  
     Doğru sürüm numarasını belirleyin ve bunu not edin.  
  
2.  Başlat **Kayıt Defteri Düzenleyicisi'ni** (regedit).  
  
3.  İçinde **Kayıt Defteri Düzenleyicisi'ni**, HKEY_LOCAL_MACHINE klasörünü açın.  
  
4.  Gidin: HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine\\{449EC4CC-30D2-4032-9256-EE18EB41B62B}  
  
     Anahtar mevcut değilse HKEY_LOCAL_MACHINE\Software\Microsoft\VisualStudio\10.0\AD7Metrics\Engine sağ tıklayın ve **yeni anahtarı**. Yeni anahtar adı `{449EC4CC-30D2-4032-9256-EE18EB41B62B}`.  
  
5.  {449EC4CC-30D2-4032-9256-EE18EB41B62B} gezinme sonra konum **adı** sütun ve Bul CLRVersionForDebugging anahtarı.  
  
    1.  Anahtar mevcut değilse, {449EC4CC-30D2-4032-9256-EE18EB41B62B} sağ tıklayın ve **yeni bir dize değeri**. Yeni bir dize değeri sağ tıklayın, **yeniden adlandırma**ve türü `CLRVersionForDebugging`.  
  
6.  Çift **CLRVersionForDebugging**.  
  
7.  İçinde **dize Düzenle** .NET Framework sürüm numarası yazın **değeri** kutusu. Örneğin: V1.1.4322  
  
8.  **Tamam**'ı tıklatın.  
  
9. Kapat **Kayıt Defteri Düzenleyicisi'ni**.  
  
     Hata ayıklama başlattığınızda doğrulayın, hala bir hata iletisi alırsanız kayıt defterinde sürüm numarası doğru girdiniz. Ayrıca bir sürümünü kullandığınızdan emin olun [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] Visual Studio tarafından desteklenir. Hata ayıklayıcı geçerli .NET Framework sürümünü ve önceki sürümleri ile uyumludur, ancak gelecekteki sürümleriyle ileri doğru uyumlu olmayabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)