---
title: IActiveScriptProperty::GetProperty | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptProperty.GetProperty
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetProperty method, IActiveScriptProperty interface
ms.assetid: a43383db-b148-4d76-83bd-4f0e899b7cb1
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d55fb2d816931a74827d318e13860b3f97f0fd23
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793970"
---
# <a name="iactivescriptpropertygetproperty"></a>IActiveScriptProperty::GetProperty
Parametresi tarafından belirtilen özelliği alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetProperty(  
// The property value:  
    uint dwProperty,    
// Not used:  
    IntPtr pvarIndex,    
// The value of the property:   
    out object pvarValue,    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwProperty`  
 Almak için özellik değeri.  
  
 `pvarIndex`  
 Kullanılmadı.  
  
 `pvarValue`  
 Özelliğin değeri.  
  
 İçin izin verilen değerler `dwProperty` aşağıdaki tabloda açıklanmıştır.  
  
|Sabit|Değer|Açıklama|  
|--------------|-----------|-------------|  
|SCRIPTPROP_INTEGERMODE|0x00003000|Kayan nokta modu yerine tamsayı modunda bölmek için komut dosyası altyapısı zorlar.|  
|SCRIPTPROP_STRINGCOMPAREINSTANCE|0x00003001|Değiştirilmesi gereken komut dosyası motoru dize karşılaştırma işlevi sağlar.|  
|SCRIPTPROP_ABBREVIATE_GLOBALNAME_RESOLUTION|0x70000002|Genel nesne katkıda bulunmak için herhangi bir komut dosyası motorları mevcut komut dosyası altyapısı bildirir.|  
|SCRIPTPROP_INVOKEVERSIONING|0x00004000|Zorlar [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı tarafından desteklenebilmesi için dil özellikleri kümesi seçin. Tarafından desteklenen dil özellikleri varsayılan kümesini [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] sürümünü 5.7 görünen dil özellik kümesi için komut dosyası altyapısı eşdeğerdir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı.|  
  
## <a name="return-value"></a>Dönüş Değeri  
 Aşağıdaki değerlerden birini döndürür:  
  
|Dönüş Değeri|Açıklama|  
|------------------|-------------|  
|`S_OK`|Başarılı.|  
|`E_INVALIDARG`|Bağımsız değişken geçerli değil.|  
|`E_UNEXPECTED`|Çağrı beklendiği (örneğin, komut dosyası altyapısı henüz yüklenen başlatılmadı veya).|  
  
## <a name="remarks"></a>Açıklamalar  
 Konak, herhangi bir komut dosyası motorları genel nesne katkıda bulunmak için mevcut bir komut dosyası motoru bildirmek için SCRIPTPROP_ABBREVIATE_GLOBALNAME_RESOLUTION özelliğini kullanabilirsiniz. Örneğin, Internet Explorer bilgilendirebilir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] oluşturulmakta olan sayfaya yalnızca içeren altyapısı [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyaları. Bu nedenle, yalnızca [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] altyapısı, yeni özellikleri genel nesne penceresine ekleyebilir ve aynı yapmak için hiçbir Visual Basic Scripting Edition (VBScript) altyapısı yoktur. Altyapısı bu bayrak yoksayabilirsiniz veya genel nesnesine eklenen yeni üyeler yönetimini iyileştirmek için kullanabilir.  
  
 Ana bilgisayar olacak şekilde dil özellikleri kümesi seçmek için SCRIPTPROP_INVOKEVERSIONING özelliğini kullanabilirsiniz ne zaman desteklenen [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı başlatılır. Bu özellik (SCRIPTLANGUAGEVERSION_5_7) 1 olarak ayarlanırsa, kullanılabilir dil özellikleri sürümünü 5.7 görünen aynıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı. 2 (SCRIPTLANGUAGEVERSION_5_8) olarak ayarlanırsa, kullanılabilir dil özellikleri sürüm 5.7 5.8 sürümünde eklenen özellikler ek olarak görünen olanlardır. Varsayılan olarak, bu özellik konak farklı varsayılan davranışı desteklemedikçe sürüm 5.7, görünen dil özellik kümesi eşit olduğu (SCRIPTLANGUAGEVERSION_DEFAULT) 0 olarak ayarlanır. Örneğin, Internet Explorer 8 içine çevrilir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 5.8 sürümü tarafından desteklenen dil özellikleri [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Internet Explorer 8 için belge modunda "Internet Explorer 8 standartları" modu olduğunda varsayılan komut dosyası altyapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge Uyumluluk tanımlama](http://msdn.microsoft.com/library/cc288325)   
 [Iactivescriptproperty](../../winscript/reference/iactivescriptproperty.md)   
 [Sürüm bilgileri](../../javascript/reference/javascript-version-information.md)