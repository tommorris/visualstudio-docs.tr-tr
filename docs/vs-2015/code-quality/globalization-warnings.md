---
title: Genelleştirme uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.globalizationrules
helpviewer_keywords:
- warnings, globalization
- globalization warnings
- globalization [Visual Studio], warnings
- managed code analysis warnings, globalization warnings
ms.assetid: a8d12d41-14bf-4b43-af24-168312d7c390
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 2430b5cac7f3cbdf7d871f574438508fee0e625b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691290"
---
# <a name="globalization-warnings"></a>Genelleştirme Uyarıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Genelleştirme uyarıları](https://docs.microsoft.com/visualstudio/code-quality/globalization-warnings).  
  
Genelleştirme uyarıları, dünya çapında kullanılmaya hazır kitaplıkları ve uygulamaları destekler.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1300: MessageBoxOptions belirtin](../code-quality/ca1300-specify-messageboxoptions.md)|Doğru olarak sağdan sola okuma düzeni kullanan kültürler için bir ileti kutusu görüntülemek için Show yöntemi MessageBoxOptions numaralandırma RightAlign ve RtlReading üyeleri geçirilmelidir.|  
|[CA1301: Yinelenen hızlandırıcılardan kaçının](../code-quality/ca1301-avoid-duplicate-accelerators.md)|Giriş anahtarı, bir hızlandırıcı olarak da bilinir, ALT anahtarını kullanarak klavye giriş denetimini sağlar. Birden çok denetimin yinelenen erişim tuşları varsa, erişim tuşunun davranışı iyi tanımlı değildir.|  
|[CA1302: Yerel özel dizeleri doğrudan programın içine gömmeyin](../code-quality/ca1302-do-not-hardcode-locale-specific-strings.md)|System.Environment.SpecialFolder numaralandırma özel sistem klasörlerine başvuran üyeleri içerir. Bu klasörlerin konumları farklı işletim sistemleri üzerinde farklı değerlere sahip olabilir; kullanıcı konumları değiştirebilir ve konumlar yerelleştirilmiştir. Environment.GetFolderPath yöntemi yerelleştirilmiş ve o anda çalışan bilgisayara uygun Environment.SpecialFolder numaralandırma ile ilişkili olan konumları döndürür.|  
|[CA1303: Harfleri yerelleştirilmiş parametreler olarak göndermeyin](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)|Dışarıdan görünen bir yöntem bir dize değişmez değer parametre olarak yapıcıya veya yönteme geçirir [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] sınıf kitaplığı ve dize yerelleştirilebilir olmalıdır.|  
|[CA1304: CultureInfo belirtin](../code-quality/ca1304-specify-cultureinfo.md)|Yöntem veya Oluşturucu System.Globalization.CultureInfo parametre kabul eden aşırı yüklenmiş üye arar ve yöntem veya oluşturucu CultureInfo parametresi aşırı yükleme çağıramaz. Bir CultureInfo veya System.IFormatProvider nesnesi sağlanamadığında, aşırı yüklü üye tarafından sağlanan varsayılan değer, tüm yerel ayarlarda istediğiniz etkiyi vermeyebilir.|  
|[CA1305: IFormatProvider belirtin](../code-quality/ca1305-specify-iformatprovider.md)|Yöntem veya oluşturucu System.IFormatProvider parametresini kabul eden aşırı yüklü bir veya daha fazla üye arar ve yöntem veya oluşturucu IFormatProvider parametre yüklemesini çağırmaz. Bir System.Globalization.CultureInfo veya IFormatProvider nesnesi sağlanamadığında, aşırı yüklü üye tarafından sağlanan varsayılan değer, tüm yerel ayarlarda istediğiniz etkiyi vermeyebilir.|  
|[CA1306: Veri türleri için yerel ayarları ayarlayın](../code-quality/ca1306-set-locale-for-data-types.md)|Yerel ayarlar, veri için kültür-özel sunum öğelerini, örneğin para birimi sembolleri, sayısal değerler için biçimleri ve sıralama düzeni için kullanılan biçimlendirme gibi değerleri belirler. Bir DataTable veya DataSet oluşturduğunuzda, yerel ayarı açık olarak ayarlamanız gerekir.|  
|[CA1307: StringComparison belirtin](../code-quality/ca1307-specify-stringcomparison.md)|StringComparison parametresi ayarlanmamış bir yöntemi aşırı bir dize karşılaştırma işleminde kullanır.|  
|[CA1308: Dizeleri büyük harfe normalleştirin](../code-quality/ca1308-normalize-strings-to-uppercase.md)|Dizeler büyük harfe normalleştirilmeli. Küçük bir karakter grubu küçük harfe dönüştürüldüğünde gidiş dönüş yapamaz.|  
|[CA1309: Sıralı StringComparison kullanın](../code-quality/ca1309-use-ordinal-stringcomparison.md)|StringComparison parametresini Ordinal ya da OrdinalIgnoreCase'a ayarlayamayan dilbilimsel olmayan dize karşılaştırma işlemi. Açıkça StringComparison.Ordinal veya StringComparison.OrdinalIgnoreCase için parametre ayarıyla kodunuz genellikle hızlanır, daha doğru olur ve daha güvenilir hale gelir.|  
|[CA2101: P/Invoke dize bağımsız değişkenleri için hazırlama belirtin](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)|Bir platform çağırma üyesi kısmen güvenilmeyen çağrıcılara izin verir. bir dize parametresine sahiptir ve dize açıkça sıralanmaz. Bu, olası bir güvenlik açığına neden olabilir.|



