---
title: 'CA2101: P-Invoke dize bağımsız değişkenleri için sıralama belirtin. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- SpecifyMarshalingForPInvokeStringArguments
- CA2101
helpviewer_keywords:
- CA2101
- SpecifyMarshalingForPInvokeStringArguments
ms.assetid: 9d1abfc3-d320-41e0-9f6e-60cefe6ffe1b
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 816158bbdfbbff22ab4941ef388330af7fe7fbb9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca2101-specify-marshaling-for-pinvoke-string-arguments"></a>CA2101: P/Invoke dize bağımsız değişkenleri için hazırlama belirtin
|||  
|-|-|  
|TypeName|SpecifyMarshalingForPInvokeStringArguments|  
|CheckId|CA2101|  
|Kategori|Microsoft.Globalization|  
|Yeni Değişiklik|Bölünemez|  
  
## <a name="cause"></a>Sebep  
 Bir platform çağırma üye kısmen güvenilen arayanlara için sağlayan bir dize parametresi varsa ve açıkça dize sıralama değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Unicode'dan ANSI için dönüştürme, belirli bir ANSI kod sayfası tüm Unicode karakterlerini gösterilebilir mümkündür. *En uygun eşlemeyi* bir karakteri temsil edilemeyen karakter getirilmesiyle bu sorunu çözmek çalışır. Bu özelliğin kullanımının, seçilen karakter denetleyemeyeceğiniz için olası bir güvenlik açığı neden olabilir. Örneğin, kötü amaçlı kod dosya sistemi özel karakterleri gibi dönüştürülür belirli kod sayfasında bulunmayan karakterler içeren bir UNICODE dizesi bilerek oluşturabilirsiniz '..' veya '/'. Ayrıca, dize için ANSI dönüştürülmeden önce güvenlik denetimlerini özel karakterler için sıklıkla oluşuyor olduğunu unutmayın.  
  
 En uygun eşlemeyi MB WChar yönetilmeyen dönüştürme için varsayılan değerdir. En uygun eşlemeyi açıkça devre dışı bırakmak sürece, kodunuzu bu sorun nedeniyle yararlanma güvenlik açığı içerebilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlal düzeltmek için açıkça dizesi veri türleriyle sıralama.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlal ediyor ve ihlalin düzeltmek nasıl gösterir bir yöntemi gösterir.  
  
 [!code-csharp[FxCop.Security.PinvokeAnsiUnicode#1](../code-quality/codesnippet/CSharp/ca2101-specify-marshaling-for-p-invoke-string-arguments_1.cs)]