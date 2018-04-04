---
title: XAML hataları ve Uyarıları | Microsoft Docs
ms.date: 03/06/2018
ms.technology: vs-ide-designers
ms.topic: article
ms.assetid: 34eac8a0-7ec5-4c40-b97a-0126ed367931
author: karann-msft
ms.author: karann
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 60e29417e1a993adfb2c4bb7c78a6f1ed0209cef
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="xaml-errors-and-warnings"></a>XAML hataları ve Uyarıları

XAML yazarken, Visual Studio yazarken kodu analiz eder. Bir hata algılandığında bir dalgalı kod satırında görünür. Dalgalı getirildiğinde hata veya uyarı hakkında daha fazla bilgi sağlar. Bazı hatalar ve Uyarılar için görüntülenen tıklattıktan kullanarak hızlı eylem ampul **Ctrl**+**.** klavye kısayolu sorunu düzeltmek için olan seçenekleri görüntüler.

## <a name="error-types"></a>Hata türleri

Arka planda, birden çok araç paralel XAML analiz edin. XAML hatalarını tek bir hata algıladı aracına bağlı aşağıdaki üç tür ayrılır:

|**Tarafından algılanan hata**|**Hata kodu biçimi**|  
|--------------------------------|-----------------|  
|XAML dil hizmeti (XAML Düzenleyicisi)|XLSxxxx|  
|XAML Tasarımcısı|XDGxxxx|  
|XAML Düzenle ve devam et|XECxxxx|  

> [!Note]
> Tüm hatalar/uyarılar karşılık gelen bir koda sahip. Bu hatalar genellikle XAML Tasarımcısı hatalardır.


## <a name="suppress-xaml-designer-errors"></a>XAML Tasarımcısı hataları gözardı

Açık **seçenekleri** seçerek iletişim **Araçlar > Seçenekler**ve ardından **metin düzenleyicisi > XAML > çeşitli**.

İşaretini **Göster XAML tasarımcısı tarafından algılanan hatalar** onay kutusu.

![XAML Tasarımcısı hataları gözardı](../designers/media/suppress_xaml_designer_errors.PNG "SuppressXAMLDesignerErrors")


