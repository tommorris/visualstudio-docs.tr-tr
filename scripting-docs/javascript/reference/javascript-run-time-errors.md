---
title: "JavaScript çalışma zamanı hataları | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT-32725
- VS.WebClient.Help.SCRIPT7002
- VS.WebClient.Help.SCRIPT1001
- VS.WebClient.Help.SCRIPT16389
- VS.WebClient.HelpSCRIPT50
- VS.WebClient.HelpSCRIPT70
- VS.WebClient.HelpSCRIPT87
- VS.WebClient.HelpSCRIPT65535
- VS.WebClient.HelpSCRIPT445
- VS.WebClient.HelpSCRIPT600
- VS.WebClient.HelpSCRIPT2343
- VS.WebClient.HelpSCRIPT122
- VS.WebClient.HelpSCRIPT28
- VS.WebClient.HelpSCRIPT16386
- VS.WebClient.HelpSCRIPT7015
- VS.WebClient.HelpSCRIPT3
- VS.WebClient.HelpSCRIPT16388
- VS.WebClient.HelpSCRIPT14
- VS.WebClient.HelpSCRIPT12030
- VS.WebClient.HelpSCRIPT12029
- VS.WebClient.HelpSCRIPT1001
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- errors [JavaScript]
- run-time errors, JavaScript
ms.assetid: c111469d-8f31-4bde-9d46-16d58775db7d
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb75c59fae32911c3dd3a7468439a198d7191755
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="javascript-run-time-errors"></a>JavaScript Çalışma zamanı Hataları
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]çalışma zamanı hataları sistem yürütülemiyor bir eylemi gerçekleştirmek komut dosyanızı çalıştığında oluşan hatalardır. Çalışma zamanı hataları değişkeni ifadelerinin değerlendirileceği veya bellek tahsis görebilirsiniz.  
  
## <a name="windows-runtime-errors"></a>Windows Çalışma Zamanı Hataları  
 Windows çalışma zamanı API'leri kullanıyorsanız, [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulama, Windows çalışma zamanı HRESULTs dönüştürülen JavaScript hataları görmek. Windows çalışma zamanı HRESULTs 0x80070000 üzerinden aralığında düşük bit onaltılık değerini almak ve bir ondalık sayıya dönüştürme için JavaScript hataları dönüştürülür. Örneğin, 0x80070032 HRESULT ondalık değeri 50 dönüştürülür ve SCRIPT50 JavaScript hatasıdır. Ondalık değer 16389 0x80074005 HRESULT dönüştürülür ve SCRIPT16389 JavaScript hatasıdır.  
  
## <a name="errors"></a>Hatalar  
  
|Hata sayısı|Açıklama|  
|------------------|-----------------|  
|5|[Erişim reddedildi](../../javascript/misc/access-is-denied.md)|  
|438|[Nesne bu özelliği veya yöntemi desteklemiyor](../../javascript/misc/object-doesn-t-support-this-property-or-method.md)|  
|1001|Bellek yetersiz|  
|5029|[Dizi uzunluğu sonlu pozitif bir tamsayı olmalıdır](../../javascript/misc/array-length-must-be-a-finite-positive-integer.md)|  
|5030|[Dizi uzunluğu sonlu pozitif bir sayı atanmalıdır](../../javascript/misc/array-length-must-be-assigned-a-finite-positive-number.md)|  
|5028|[Dizi ya da bağımsız değişkenler nesnesi bekleniyor](../../javascript/misc/array-or-arguments-object-expected.md)|  
|5010|[Boolean bekleniyor](../../javascript/misc/boolean-expected.md)|  
|5003|[İşlev sonucuna atanamaz](../../javascript/misc/cannot-assign-to-a-function-result.md)|  
|5000|['This' nesnesine atanamaz](../../javascript/misc/cannot-assign-to-this.md)|  
|5034|[Desteklenmeyen değer bağımsız değişkeninde döngüsel başvuru](../../javascript/misc/circular-reference-in-value-argument-not-supported.md)|  
|5006|[Tarih nesnesi bekleniyor](../../javascript/misc/date-object-expected.md)|  
|5015|[Numaralandırıcı nesne bekleniyor](../../javascript/misc/enumerator-object-expected.md)|  
|5022|[Oluşturulan özel durum yakalanmadı](../../javascript/misc/exception-thrown-and-not-caught.md)|  
|5020|[Beklenen ')' normal ifadede](../../javascript/misc/expected-right-parenthesis-in-regular-expression-javascript.md)|  
|5019|[Beklenen ' &#93;' normal ifadede](../../javascript/misc/expected-right-square-bracket-in-regular-expression-javascript.md)|  
|5023|[İşlev geçerli bir prototip nesnesi yok](../../javascript/misc/function-does-not-have-a-valid-prototype-object.md)|  
|5002|[İşlev bekleniyor](../../javascript/misc/function-expected.md)|  
|5008|[Geçersiz atama](../../javascript/misc/illegal-assignment-javascript.md)|  
|5021|[Geçersiz karakter kümesi aralığı](../../javascript/misc/invalid-range-in-character-set-javascript.md)|  
|5035|[Geçersiz değiştirici bağımsız değişken](../../javascript/misc/invalid-replacer-argument.md)|  
|5014|[JavaScript nesne bekleniyor](../../javascript/misc/javascript-object-expected.md)|  
|5001|[Sayı bekleniyor](../../javascript/misc/number-expected.md)|  
|5007|[Nesne bekleniyor](../../javascript/misc/object-expected.md)|  
|5012|[Nesne üyesi bekleniyor](../../javascript/misc/object-member-expected.md)|  
|5016|[Normal ifade nesnesi bekleniyor](../../javascript/misc/regular-expression-object-expected.md)|  
|5005|[Dize bekleniyor](../../javascript/misc/string-expected.md)|  
|5017|[Normal ifadede sözdizimi hatası](../../javascript/misc/syntax-error-in-regular-expression-javascript.md)|  
|5026|[Kesir basamakları sayısı aralık dışında olduğundan](../../javascript/misc/the-number-of-fractional-digits-is-out-of-range.md)|  
|5027|[Duyarlılık aralık dışında kalıyor](../../javascript/misc/the-precision-is-out-of-range.md)|  
|5025|[Kodu çözülecek URI geçerli bir kodlamada değil](../../javascript/misc/the-uri-to-be-decoded-is-not-a-valid-encoding.md)|  
|5024|[Kodlanacak URI geçersiz karakter içeriyor](../../javascript/misc/the-uri-to-be-encoded-contains-an-invalid-character.md)|  
|5009|[Tanımlanmamış tanımlayıcı](../../javascript/misc/undefined-identifier.md)|  
|5018|[Beklenmeyen niceleyici](../../javascript/misc/unexpected-quantifier-javascript.md)|  
|5013|[VBArray bekleniyor](../../javascript/misc/vbarray-expected.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript sözdizimi hataları](../../javascript/reference/javascript-syntax-errors.md)