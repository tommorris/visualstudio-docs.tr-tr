---
title: "LBound yöntemi (VBArray) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: lbound
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: lbound method
ms.assetid: 30ff5e8a-8165-494b-bce8-0a562ec2eec3
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b01adf424d42e9d24512d15b03ede6079a3da186
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="lbound-method-vbarray-javascript"></a>lbound Yöntemi (VBArray) (JavaScript)
Bir VBArray belirtilen boyuttaki kullanılan en düşük dizin değeri döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
safeArray.lbound(dimension)   
```  
  
## <a name="parameters"></a>Parametreler  
 *safeArray*  
 Gerekli. VBArray nesnesi.  
  
 `dimension`  
 İsteğe bağlı. Alt sınır dizin istediği VBArray boyut. Atlanırsa, `lbound` 1 geçildi gibi davranır.  
  
## <a name="remarks"></a>Açıklamalar  
 VBArray boşsa, `lbound` yöntemi tanımsız döndürür. Varsa `dimension` VBArray boyutlarında sayısından daha büyük ya da negatif yöntemi "Alt simge aralık dışında" bir hata oluşturur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, üç bölümden oluşur. Visual Basic güvenli diziye oluşturmak için VBScript kodu ilk bölümüdür. İkinci bölümü [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] güvenli dizinin boyut sayısını ve her boyutun alt sınırını belirler kodu. Visual Basic yerine VBScript güvenli diziye oluşturulduğundan, alt sınır her zaman sıfır olacak. Bu bölümlerin her ikisi de yerleştirilmesini \<HEAD > bölümünde HTML sayfası. Üçüncü bir parçasıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] gider, kod \<gövde > diğer iki bölümden alınmalıdır.  
  
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
         k = k + 1  
      Next  
   Next  
   CreateVBArray = a  
End Function  
-->  
</script>  
  
<script type="text/javascript">  
<!--  
function VBArrayTest(vba){  
   var i;  
   var a = new VBArray(vba);  
   var s = "";  
   for (i = 1; i <= a.dimensions(); i++)  
   {  
      s += "The lower bound of dimension ";  
      s += i + " is ";  
      s += a.lbound(i);  
      s += ".<br />";  
   }  
   return (s);  
}  
-->  
</script>  
</head>  
  
<body>  
<script type="text/javascript">  
   document.write(VBArrayTest(CreateVBArray()));  
</script>  
</body>  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Şu belge modlarında desteklenir: Quirks, Internet Explorer 6 standartları, Internet Explorer 7 standartları, Internet Explorer 8 standartları, Internet Explorer 9 standartları ve Internet Explorer 10 standartları. İçinde desteklenmez [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] uygulamalar. Bkz. [Sürüm Bilgisi](../../javascript/reference/javascript-version-information.md).  
  
 **Uygulandığı öğe**: [VBArray nesnesi](../../javascript/reference/vbarray-object-javascript.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [dimensions yöntemi (VBArray)](../../javascript/reference/dimensions-method-vbarray-javascript.md)   
 [GetItem yöntemi (VBArray)](../../javascript/reference/getitem-method-vbarray-javascript.md)   
 [toArray yöntemi (VBArray)](../../javascript/reference/toarray-method-vbarray-javascript.md)   
 [UBound yöntemi (VBArray)](../../javascript/reference/ubound-method-vbarray-javascript.md)