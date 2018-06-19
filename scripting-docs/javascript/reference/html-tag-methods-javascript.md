---
title: HTML etiketi metotları (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- link method [JavaScript]
- blink method [JavaScript]
- fontsize method [JavaScript]
- italics method [JavaScript]
- sup method [JavaScript]
- anchor method [JavaScript]
- fixed method [JavaScript]
- fontcolor method [JavaScript]
- bold method [JavaScript]
- small method [JavaScript]
- HTML Tag methods [JavaScript]
- sub method [JavaScript]
- big method [JavaScript]
ms.assetid: 50376223-be95-4aa4-9147-9e738a5d3cfa
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7639bc609d8e9b7e4b212fe67ae40f81487d708e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791105"
---
# <a name="html-tag-methods-javascript"></a>HTML Etiketi Metotları (JavaScript)
HTML etiketi metotları metinde geçici HTML öğeleri yerleştirmek için kullanabileceğiniz bir `String` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
 Aşağıdaki tabloda, sözdizimi ve her HTML etiketi yönteminin bir açıklaması listelenmektedir.  
  
 Sözdizimi sütununda `string1` olan bir `String` nesne veya sabit değer.  
  
 Standart sütun gösterir [World Wide Web Konsorsiyumu (W3C)](http://go.microsoft.com/fwlink/?LinkId=199553) HTML 4'e yönelik öneriler. "Önermez" HTML öğesi stil sayfaları lehinde önerilmez gösterir.  
  
|Sözdizimi|Yöntemi açıklaması|Parametre açıklaması|Standart|  
|------------|------------------------|---------------------------|--------------|  
|`string1`.Anchor (`name`)|Metin geçici bir ad özniteliğine sahip bir HTML Bağlayıcısı yerleştirir.|`name` Parametredir HTML bağlantı adı özniteliği yerleştirilecek metin.||  
|`string1`.Big()|Yerleştirir HTML \<büyük > metninin çevresindeki etiketler.||Önerilmez|  
|`string1`.blink()|Yerleştirir HTML \<BLINK > metninin çevresindeki etiketler. \<BLINK > etiketi, Internet Explorer'da desteklenmiyor.||Standart değil|  
|`string1`.Bold()|Yerleştirir HTML \<B > metninin çevresindeki etiketler.||Önerilmez|  
|`string1`.fixed()|Yerleştirir HTML \<TT > metninin çevresindeki etiketler.||Önerilmez|  
|`string1`.fontcolor (`color`)|Yerleştirir HTML \<yazı tipi > etiketleri metninin çevresindeki renk özniteliğine sahip.|`color` Parametredir on altılık değeri veya bir renk için önceden tanımlanmış adını içeren bir dize değeri. Geçerli önceden tanımlanmış renk adları bağlıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] konak tarayıcı ve sürümü.|Kullanım dışı|  
|`string1`.FontSize (`size`)|Yerleştirir HTML \<yazı tipi > metninin çevresindeki BOYUTU özniteliğiyle etiketler.|`size` Parametredir metnin boyutunu belirten bir tamsayı değeri. Geçerli bir tamsayı değerleri bağlıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] konak tarayıcı ve sürümü.|Kullanım dışı|  
|`string1`.italics()|Yerleştirir HTML \<t > metninin çevresindeki etiketler.||Önerilmez|  
|`string1`.Link (`href`)|Bir HREF özniteliği etrafında bir HTML Bağlayıcısı yerleştirir.|`href` Parametredir HTML bağlantı HREF özniteliği yerleştirilecek metin.||  
|`string1`.Small()|Yerleştirir HTML \<küçük > metninin çevresindeki etiketler.||Önerilmez|  
|`string1`.Strike()|Yerleştirir HTML \<ÜSTÜNÜ > metninin çevresindeki etiketler.||Kullanım dışı|  
|`string1`.Sub()|Yerleştirir HTML \<SUB > metninin çevresindeki etiketler.|||  
|`string1`.sup()|Yerleştirir HTML \<SUP > metninin çevresindeki etiketler.|||  
  
## <a name="remarks"></a>Açıklamalar  
 HTML etiketlerini dizeye zaten uygulanıp uygulanmadığını belirlemek için hiçbir denetimi gerçekleştirilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekler, HTML etiket yöntemleri kullanmayı gösterir.  
  
```JavaScript  
// anchor method.  
var strVariable = "This is an anchor.";  
document.write(strVariable.anchor("Anchor1"));  
// Output: <A NAME="Anchor1">This is an anchor.</A>  
  
// big method.  
var strVariable = "This is a string.";  
document.write(strVariable.big());  
// Output: <BIG>This is a string.</BIG>  
  
//  blink method.  
var strVariable = "This is a string.";  
document.write(strVariable.blink());  
// Output: <BLINK>This is a string.</BLINK>  
  
//  bold method.  
var strVariable = "This is a string.";  
document.write(strVariable.bold());  
// Output: <B>This is a string.</B>  
  
//  fixed method.  
var strVariable = "This is a string.";  
document.write(strVariable.fixed());  
// Output: <TT>This is a string.</TT>  
  
//  fontcolor method.  
var strVariable = "This is a string.";  
document.write(strVariable.fontcolor("red"));  
// Output: <FONT COLOR="red">This is a string.</FONT>  
  
//  fontsize method.  
var strVariable = "This is a string.";  
document.write(strVariable.fontsize(-1));  
// Output: <FONT SIZE="-1">This is a string.</FONT>  
  
//  italics method  
var strVariable = "This is a string.";  
document.write(strVariable.italics());  
// Output: <I>This is a string.</I>  
  
//  link method.  
var strVariable = "This is a hyperlink.";  
document.write(strVariable.link("http://www.microsoft.com"));  
// Output: <A HREF="http://www.microsoft.com">This is a hyperlink.</A>  
  
//  small method.  
var strVariable = "This is a string.";  
document.write(strVariable.small());  
// Output: <SMALL>This is a string.</SMALL>  
  
//  strike method.  
var strVariable = "This is a string.";  
document.write(strVariable.strike());  
// Output: <STRIKE>This is a string.</STRIKE>  
  
//  sub method.  
var strVariable = "This is a string.";  
document.write(strVariable.sub());  
// Output: <SUB>This is a string.</SUB>  
  
//  sup method.  
var strVariable = "This is a string.";  
document.write(strVariable.sup());  
// Output: <SUP>This is a string.</SUP>  
```  
  
## <a name="requirements"></a>Gereksinimler  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Uygulandığı öğe**: [dize nesnesi](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize nesnesi](../../javascript/reference/string-object-javascript.md)