---
title: VBArray nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VBArray
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- VBArray object constant
ms.assetid: f0b767f1-ea8a-4726-962b-2708d4742518
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b86e261a0cef445f1e0e0ecd651d5eb283cffce1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="vbarray-object-javascript"></a>VBArray Nesnesi (JavaScript)
Visual Basic güvenli diziler erişim sağlar.  
  
> [!WARNING]
>  Bu nesne Internet Explorer'da yalnızca içinde değil desteklenmiyor [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
varName = new VBArray(safeArray)   
```  
  
## <a name="parameters"></a>Parametreler  
 `varName`  
 Gerekli. VBArray atandığı değişken adı.  
  
 *safeArray*  
 Gerekli. VBArray değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 VBArrays salt okunurdur ve doğrudan oluşturulamıyor. *SafeArray* bağımsız değişkeni gerekir elde VBArray değeri VBArray oluşturucuya geçirilen önce. Bu, varolan bir ActiveX veya başka bir nesne değeri alarak yalnızca yapılabilir.  
  
 VBArrays birden çok boyut olabilir. Her boyut dizinlerini farklı olabilir. **Boyutları** yöntemi alır; dizinin boyut sayısını `lbound` ve `ubound` yöntemleri almak dizinlerini her boyut için kullanılan aralık.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç bölümden oluşur. Visual Basic güvenli diziye oluşturmak için VBScript kodu ilk bölümüdür. İkinci bölümü [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Visual Basic güvenli diziye dönüştürür kod bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dizi. Bu bölümlerin her ikisi de yerleştirilmesini \<HEAD > bölümünde HTML sayfası. Üçüncü bir parçasıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] gider, kod \<gövde > diğer iki bölümden alınmalıdır.  
  
```JavaScript  
<head>  
<script type="text/vbscript">  
<!--  
Function CreateVBArray()  
   Dim i, j, k  
   Dim a(2, 2)  
   k = 1  
   For i = 0 To 2  
      For j = 0 To 2  
         a(j, i) = k  
         document.writeln(k)  
         k = k + 1  
      Next  
      document.writeln("<br />")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vbarray){  
   var a = new VBArray(vbarray);  
   var b = a.toArray();  
   var i;  
   for (i = 0; i < 9; i++)   
   {  
      document.writeln(b[i]);  
   }  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
<!--  
   VBArrayTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## <a name="properties"></a>Özellikler  
 `VBArray` Nesnenin özellik vardır.  
  
## <a name="methods"></a>Yöntemler  
 [dimensions yöntemi](../../javascript/reference/dimensions-method-vbarray-javascript.md) &#124; [GetItem yöntemi](../../javascript/reference/getitem-method-vbarray-javascript.md) &#124; [lbound yöntemi](../../javascript/reference/lbound-method-vbarray-javascript.md) &#124; [toArray yöntemi](../../javascript/reference/toarray-method-vbarray-javascript.md) &#124; [ubound yöntemi](../../javascript/reference/ubound-method-vbarray-javascript.md)  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizi nesnesi](../../javascript/reference/array-object-javascript.md)