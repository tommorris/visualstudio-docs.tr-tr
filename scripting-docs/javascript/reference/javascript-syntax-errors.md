---
title: JavaScript sözdizimi hataları | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- errors [JavaScript]
- syntax errors, JavaScript
ms.assetid: 0343dc19-5f5e-4a4c-83da-630b4fbcb3b6
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3bc3398d6a90ef308fd2b4b367bc1006ad95f5b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791444"
---
# <a name="javascript-syntax-errors"></a>JavaScript Sözdizimi Hataları
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]sözdizimi hataları ortaya zaman birinin yapısı, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] deyimleri bir veya daha fazla söz dizimi kurallarını ihlal ediyor.  
  
## <a name="errors"></a>Hatalar  
  
|Hata sayısı|Açıklama|  
|------------------|-----------------|  
|1019|[Döngü dışında ' break' olamaz](../../javascript/misc/can-t-have-break-outside-of-loop.md)|  
|1020|[Döngü dışında 'continue' olamaz](../../javascript/misc/can-t-have-continue-outside-of-loop.md)|  
|1030|[Koşullu derleme kapalı](../../javascript/misc/conditional-compilation-is-turned-off.md)|  
|1027|['default' yalnızca bir kez 'switch' deyimi içinde bulunabilir](../../javascript/misc/default-can-only-appear-once-in-a-switch-statement.md)|  
|1005|[Beklenen ' ('](../../javascript/misc/expected-left-parenthesis-javascript.md)|  
|1006|[Beklenen ')'](../../javascript/misc/expected-right-parenthesis-javascript.md)|  
|1012|[Beklenen '/'](../../javascript/misc/expected-minus.md)|  
|1003|[Beklenen ':'](../../javascript/misc/expected-colon.md)|  
|1004|[Beklenen ';'](../../javascript/misc/expected-semicolon.md)|  
|1032|[Beklenen ' @'](../../javascript/misc/expected-at.md)|  
|1029|[Beklenen '@end'](../../javascript/misc/expected-at-end.md)|  
|1007|[Beklenen ' &#93;'](../../javascript/misc/expected-right-square-bracket.md)|  
|1008|[Beklenen ' {'](../../javascript/misc/expected-left-curly-brace.md)|  
|1009|[Beklenen '}'](../../javascript/misc/expected-right-curly-brace.md)|  
|1011|[Beklenen '='](../../javascript/misc/expected-equal-javascript.md)|  
|1033|['Catch' bekleniyor.](../../javascript/misc/expected-catch.md)|  
|1031|[Sabit bekleniyor](../../javascript/misc/expected-constant.md)|  
|1023|[Onaltılık basamak bekleniyordu](../../javascript/misc/expected-hexadecimal-digit.md)|  
|1010|[Tanımlayıcı bekleniyor](../../javascript/misc/expected-identifier-javascript.md)|  
|1028|[Tanımlayıcı bekleniyor, dize veya sayı](../../javascript/misc/expected-identifier-string-or-number.md)|  
|1024|[Beklenen 'while'](../../javascript/misc/expected-while.md)|  
|1014|[Geçersiz bir karakter](../../javascript/misc/invalid-character-javascript.md)|  
|1026|[Etiket bulunamadı](../../javascript/misc/label-not-found.md)|  
|1025|[Etiket yeniden tanımlandı](../../javascript/misc/label-redefined.md)|  
|1018|['return deyimi işlev dışı'](../../javascript/misc/return-statement-outside-of-function.md)|  
|1002|[Sözdizimi hatası](../../javascript/misc/syntax-error-javascript.md)|  
|1035|[Throw aynı kaynak satırdaki bir ifade gelmelidir](../../javascript/misc/throw-must-be-followed-by-an-expression-on-the-same-source-line.md)|  
|1016|[Sonlandırılmayan açıklama](../../javascript/misc/unterminated-comment.md)|  
|1015|[Sonlandırılmamış dize sabiti](../../javascript/misc/unterminated-string-constant-javascript.md)|  
  
### <a name="script-host-errors"></a>Komut dosyası ana bilgisayarı hataları  
 Aşağıdaki hatalar düzgün komut dosyası ana bilgisayarı için ilgili hatalar konuşarak ancak bazen görebilirsiniz.  
  
|Hata|HRESULT|Açıklama|  
|-----------|-------------|-----------------|  
|SCRIPT_E_RECORDED|0x86664004|Bir hata, komut dosyası altyapısı ve ana bilgisayar arasında iletilecek kaydedildi. Konak, hata kodu çağırana geçirmesini gerekiyor.|  
|SCRIPT_E_REPORTED|0x80020101|Betik altyapısı IActiveScriptSite::OnScriptError aracılığıyla konak işlenmeyen bir özel durum bildirdi. Konak bu hatayı yoksayabilirsiniz.|  
|SCRIPT_E_PROPAGATE|0x8002010|Bir komut dosyası hatası farklı bir iş parçacığında olabilecek çağırana yayılır. Ana bilgisayar hata kodu çağırana geçirmesini.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript çalışma zamanı hataları](../../javascript/reference/javascript-run-time-errors.md)