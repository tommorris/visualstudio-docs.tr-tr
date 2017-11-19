---
title: IActiveScriptProperty::SetProperty | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProperty.SetProperty
apilocation: scrobj.dll
helpviewer_keywords: SetProperty method, IActiveScriptProperty interface
ms.assetid: 0ba429c5-04a3-4505-bc5f-69c505dfca91
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bc9b5f4c0d02789988bb41f46417651414beed7f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptpropertysetproperty"></a>IActiveScriptProperty::SetProperty
Parametresi tarafından belirtilen özelliği ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT SetProperty(  
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
 Ayarlanacak özellik değeri.  
  
 `pvarIndex`  
 Kullanılmadı.  
  
 `pvarValue`  
 Özelliğin değeri.  
  
 İçin izin verilen değerler `dwProperty` aşağıdaki tabloda açıklanmıştır.  
  
|Sabit|Değer|Açıklama|  
|--------------|-----------|-------------|  
|SCRIPTPROP_INTEGERMODE|0x00003000|Kayan nokta modu yerine tamsayı modunda bölmek için komut dosyası altyapısı zorlar. Varsayılan değer `False` şeklindedir.|  
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
 Etkinleştirmek veya tamsayı bölme devre dışı bırakmak için çağırma `SetProperty` ve dönüştürün bir `Boolean` için bir `Object`. Varsayılan olarak, özellik değeri olduğundan `False`. Ayarlarsanız `True`, bölme işlemleri yalnızca tamsayı döndürür.  
  
 Etkinleştirmek veya özel bir dize karşılaştırma devre dışı bırakmak için çağırma `SetProperty` ve geçirin bir `Object` değeri. Geçirdiğiniz nesne arabirimi uygulamalıdır [Iactivescriptstringcompare arabirimi](../../winscript/reference/iactivescriptstringcompare-interface.md). [StrComp](../../winscript/reference/iactivescriptstringcompare-strcomp.md) yöntemi [Iactivescriptstringcompare arabirimi](../../winscript/reference/iactivescriptstringcompare-interface.md) arabirimi, bir dize karşılaştırma işlevi yürütülen her zaman çağrılır.  
  
 Ne zaman desteklenecek dil özellikleri kümesi seçmek için [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı başlatılır, çağırma `SetProperty` ve SCRIPTPROP_INVOKEVERSIONING için etkin için ayarlama dil özelliğine karşılık gelen bir değer geçirin. Bu özellik (SCRIPTLANGUAGEVERSION_5_7) 1 olarak ayarlanırsa, kullanılabilir dil özellikleri sürümünü 5.7 görünen aynıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı. 2 (SCRIPTLANGUAGEVERSION_5_8) olarak ayarlanırsa, kullanılabilir dil özellikleri sürüm 5.7 5.8 sürümde eklenen yeni özellikler ek olarak görünen olanlardır. Varsayılan olarak, bu özellik konak farklı varsayılan davranışı desteklemedikçe sürüm 5.7, görünen dil özellik kümesi eşit olduğu (SCRIPTLANGUAGEVERSION_DEFAULT) 0 olarak ayarlanır. Örneğin, Internet Explorer 8 içine çevrilir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 5.8 sürümü tarafından desteklenen dil özellikleri [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Internet Explorer 8 için varsayılan belge modunda "Internet Explorer 8 standartları" modu olduğunda varsayılan komut dosyası altyapısı. Internet Explorer 7 standartları için Internet Explorer 8 belge modu veya Quirks modunu değiştirme sıfırlar [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 5.7 sürümünde var olan dil özellik kümesini desteklemek için komut dosyası altyapısı [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı.  
  
> [!NOTE]
>  SCRIPTPROP_INVOKEVERSIONING yalnızca ayarlanmalıdır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] komut dosyası altyapısı başlatıldığı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek karşılaştırma işlev aşırı yüklemesi izin verme ve Tamsayı bölme kullanmak için komut dosyası altyapısı zorlamak nasıl gösterir.  
  
```c#  
BMLScriptEngine bmlScriptEngine = new BMLScriptEngine();  
IActiveScriptProperty scriptProperties = bmlScriptEngine as   
    IActiveScriptProperty;  
  
// Force the scripting engine to use integer division.  
Boolean enableIntegerDivision = true;  
Object vtIntegerDivInstance = (Object)enableIntegerDivision;  
                scriptProperties.SetProperty(SCRIPTPROP_INTEGERDIVISION,   
    System.IntPtr.Zero, ref vtIntegerDivInstance);  
  
// Allow overloading of the compare function.  
BMLScriptStringCompare bmlScriptStringCompareInstance = new   
    BMLScriptStringCompare();  
Object vtStrCmpInstance = (Object)bmlScriptStringCompareInstance;  
scriptProperties.SetProperty(SCRIPTPROP_STRCOMPINST,   
    System.IntPtr.Zero, ref vtStrCmpInstance);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge Uyumluluk tanımlama](http://msdn.microsoft.com/library/cc288325)   
 [Iactivescriptproperty](../../winscript/reference/iactivescriptproperty.md)   
 [Sürüm bilgileri](../../javascript/reference/javascript-version-information.md)