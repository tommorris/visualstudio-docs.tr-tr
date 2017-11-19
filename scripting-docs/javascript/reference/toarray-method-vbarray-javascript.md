---
title: "toArray yöntemi (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toArray
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toArray method
ms.assetid: 664de44c-2039-4289-82f6-948e9d744d80
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeee8acad04125eb942089b4d8dacef6f0f5e6fb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="toarray-method-vbarray-javascript"></a>toArray Yöntemi (VBArray) (JavaScript)
Standart bir döndürür [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] array VBArray dönüştürülür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
safeArray.toArray( )   
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gerekli *safeArray* başvurudur VBArray nesnesi.  
  
 Tek boyutlu bir çok boyutlu VBArray dönüştürme çevirir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dizi. Art arda gelen her boyut öncekinin sonuna eklenir. Örneğin, üç boyut ve her boyut üç öğelerinde VBArray dönüştürülen bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] gibi dizisi:  
  
 VBArray içerdiğini varsayalım: (1, 2, 3), (4, 5, 6) (7, 8, 9). Çeviri sonra [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] dizi içeriyor: 1, 2, 3, 4, 5, 6, 7, 8, 9.  
  
 Şu anda dönüştürmenin hiçbir yolu olan bir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] bir VBArray diziye.  
  
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
      document.writeln("<BR>")  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vbarray)  
{  
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
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
 **Uygulandığı öğe**: [VBArray nesnesi](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dimensions yöntemi (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [GetItem yöntemi (VBArray)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [LBound yöntemi (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [UBound yöntemi (VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)