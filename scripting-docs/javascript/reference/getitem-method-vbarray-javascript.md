---
title: "GetItem yöntemi (VBArray) (JavaScript) | Microsoft Docs"
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
- getItem
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getItem method
- Item property
ms.assetid: f62964ad-8b2f-4596-95d0-b20e587ecea5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e6457435d047f2780a19fa8ce26fc2bb86f7ae0e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="getitem-method-vbarray-javascript"></a>getItem Metodu (VBArray) (JavaScript)
Belirtilen konumda öğeyi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
safeArray.getItem(dimension1[, dimension2, ...], dimensionN)   
```  
  
## <a name="parameters"></a>Parametreler  
 *safeArray*  
 Gerekli. VBArray nesnesi.  
  
 *dimension1,..., dimensionN*  
 VBArray istenen öğesinin tam konumunu belirtir. *n*VBArray boyutlarında sayısına eşittir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç bölümden oluşur. Visual Basic güvenli diziye oluşturmak için VBScript kodu ilk bölümüdür. İkinci bölümü [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Visual Basic güvenli diziye tekrarlanan ve her öğenin içeriğini yazdırır kodu. Bu bölümlerin her ikisi de yerleştirilmesini \<HEAD > bölümünde HTML sayfası. Üçüncü bir parçasıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] gider, kod \<gövde > diğer iki bölümden alınmalıdır.  
  
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
         a(i, j) = k  
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
function GetItemTest(vbarray)  
{  
   var i, j;  
   var a = new VBArray(vbarray);  
   for (i = 0; i <= 2; i++)  
   {  
      for (j =0; j <= 2; j++)  
      {  
         document.writeln(a.getItem(i, j));  
      }  
   }  
}  
-->  
</script>  
</head>  
<body>  
<script type="text/javascript">  
<!--  
   GetItemTest(CreateVBArray());  
-->  
</script>  
</body>  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
 **Uygulandığı öğe**: [VBArray nesnesi](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dimensions yöntemi (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [LBound yöntemi (VBArray)](../../javascript/reference/lbound-method-vbarray-javascript.md)   
 [toArray yöntemi (VBArray)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [UBound yöntemi (VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)