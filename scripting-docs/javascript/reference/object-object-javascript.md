---
title: Nesne nesnesi (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: object
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Object object
ms.assetid: d24ef8fc-217b-4828-94e1-19f72780bae0
caps.latest.revision: "25"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17e82b9c66c286c7f847e7b67b1b5928aadd613e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="object-object-javascript"></a>Nesne Nesnesi (JavaScript)
Tüm ortak işlevsellik sağlar [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
obj  
 = new Object([value])   
```  
  
## <a name="parameters"></a>Parametreler  
 `obj`  
 Gerekli. Değişken adına `Object` nesne atanır.  
  
 *değer*  
 İsteğe bağlı. Herhangi biri [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] temel veri türleri (sayı, Boole veya dize). Değer bir nesne, nesne değiştirilmemiş döndürülür. Varsa *değeri* olan `null`, **tanımsız**, veya sağlanmayan, içerik sahip bir nesne oluşturulur.  
  
## <a name="remarks"></a>Açıklamalar  
 `Object` Nesne barındırılan diğer tüm [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneleri; tüm yöntemleri ve özellikleri diğer tüm nesneleri kullanılabilir. Yöntem kullanıcı tanımlı nesneler tanımlanabilir ve tarafından çağrılır [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] uygun zamanlarda. **ToString** yöntemi örneğidir bir sık sık yeniden tanımlanan `Object` yöntemi.  
  
 Bu dil başvurusu, her açıklaması `Object` yöntemi, hem varsayılan hem de iç nesneye özgü uygulama bilgisi içerir [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] nesneleri.  
  
## <a name="requirements"></a>Gereksinimler  
 `Object Object` Sunulmuştur [!INCLUDE[jsv3text](../../javascript/reference/includes/jsv3text-md.md)]. Aşağıdaki listelerin bazı üyeleri daha sonraki sürümlerde eklendi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda özelliklerini `Object Object`.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[__proto\_ \_ özelliği](../../javascript/reference/proto-property-object-javascript.md)|Bir nesne için prototip belirtir.|  
|[constructor özelliği](../../javascript/reference/constructor-property-object-javascript.md)|Bir nesneyi oluşturan işlevi belirtir.|  
|[prototype özelliği](../../javascript/reference/prototype-property-object-javascript.md)|Bir nesne sınıfı için prototipe bir başvuru döndürür.|  
  
## <a name="functions"></a>İşlevler  
 Aşağıdaki tabloda işlevlerini listeler `Object Object`.  
  
|İşlev|Açıklama|  
|--------------|-----------------|  
|[Object.Assign nesnesi](../../javascript/reference/object-assign-function-object-javascript.md)|Değerleri bir veya daha çok kaynak nesneden bir hedef nesnesine kopyalar.|  
|[Object.Create işlevi](../../javascript/reference/object-create-function-javascript.md)|Belirtilen bir prototip sahip ve isteğe bağlı olarak belirtilen özellikleri içeren bir nesne oluşturur.|  
|[Object.defineProperties işlevi](../../javascript/reference/object-defineproperties-function-javascript.md)|Bir veya daha fazla özellikleri bir nesne ekler ve/veya var olan özellikleri özniteliklerini değiştirir.|  
|[Object.defineProperty işlevi](../../javascript/reference/object-defineproperty-function-javascript.md)|Bir özellik için bir nesne ekler veya varolan bir özellik özniteliklerini değiştirir.|  
|[Object.Freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md)|Var olan özellik öznitelikleri ve değerleri değiştirilmesini ve yeni özellikleri eklenmesini engeller.|  
|[Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)|Veri özelliği ya da bir erişimci özellik tanımını döndürür.|  
|[Object.getOwnPropertyNames işlevi](../../javascript/reference/object-getownpropertynames-function-javascript.md)|Özellik adlarını ve bir yöntemlerinden birini döndürür.|  
|[Object.getOwnPropertySymbols işlevi](../../javascript/reference/object-getownpropertysymbols-function-javascript.md)|Sembol Özellikleri bir nesne döndürür.|  
|[Object.getPrototypeOf işlevi](../../javascript/reference/object-getprototypeof-function-javascript.md)|Bir nesne örneğini döndürür.|  
|[Object.is işlevi](../../javascript/reference/object-is-function-javascript.md)|İki değer aynı değer olup olmadığını belirten bir değer döndürür.|  
|[Object.isExtensible işlevi](../../javascript/reference/object-isextensible-function-javascript.md)|Bir nesne için yeni özellikler eklenebilir olup olmadığını belirten bir değer döndürür.|  
|[Object.isFrozen işlevi](../../javascript/reference/object-isfrozen-function-javascript.md)|Döndürür `true` var olan özellik öznitelikleri ve değerleri, bir nesne değiştirilemez ve yeni özellikleri nesneye eklenemez.|  
|[Object.isSealed işlevi](../../javascript/reference/object-issealed-function-javascript.md)|Döndürür `true` var olan özellik öznitelikleri bir nesne değiştirilemez ve yeni özellikleri nesneye eklenemez.|  
|[Object.Keys işlevi](../../javascript/reference/object-keys-function-javascript.md)|Numaralandırılabilir özellik adlarını ve bir yöntemlerinden birini döndürür.|  
|[Object.preventExtensions işlevi](../../javascript/reference/object-preventextensions-function-javascript.md)|Yeni özelliklerin eklenmesi nesneye engeller.|  
|[Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md)|Var olan özellikleri özniteliklerini değiştirme ve yeni özellikleri eklenmesini engeller.|  
|[Object.setPrototypeOf işlevi](../../javascript/reference/object-setprototypeof-function-javascript.md)|Bir nesnenin prototip ayarlar.|  
  
## <a name="methods"></a>Yöntemler  
 Aşağıdaki tabloda yöntemlerini listeler `Object Object`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[hasOwnProperty yöntemi](../../javascript/reference/hasownproperty-method-object-javascript.md)|Bir nesnenin belirtilen adda bir özelliği olup olmadığını belirten bir Boolean değer döndürür.|  
|[isPrototypeOf yöntemi](../../javascript/reference/isprototypeof-method-object-javascript.md)|Bir nesne başka bir nesnenin prototip hiyerarşisinde var olup olmadığını belirten bir Boole değeri döndürür.|  
|[Propertyısenumerable yöntemi](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Belirtilen bir özelliğin bir nesnenin parçası olup olmadığını ve numaralandırılabilir olup olmadığını belirten bir Boolean değer döndürür.|  
|[toLocaleString yöntemi](../../javascript/reference/tolocalestring-method-object-javascript.md)|Geçerli bölgesel ayarına göre bir dizeye dönüştürülen bir nesne döndürür.|  
|[toString yöntemi](../../javascript/reference/tostring-method-object-javascript.md)|Bir nesnenin dize gösterimini döndürür.|  
|[valueOf yöntemi](../../javascript/reference/valueof-method-object-javascript.md)|Belirtilen nesne ilkel değerini döndürür.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [JavaScript nesneleri](../../javascript/reference/javascript-objects.md)