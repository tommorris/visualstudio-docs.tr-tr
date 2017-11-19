---
title: "Veri özellikleri ve erişimci özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 7e132831-375d-4728-9a57-5c6f91075b1c
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b800131ba76aa432492c0caefdbb9e8d5291924
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="data-properties-and-accessor-properties"></a>Veri Özellikleri ve Erişimci Özellikleri
Bu bölüm veri özellikleri ve erişimci özellikleri hakkında gerek olasılığı olan tüm bilgileri içerir.  
  
### <a name="data-properties"></a>Veri özellikleri  
 A *veri özelliği* almak ve bir değer ayarlamak bir özelliktir. Veri özellikleri içeren `value` ve `writable` kendi tanımlayıcılarında özellikleri.  
  
 Aşağıdaki tabloda veri özellik tanımlayıcısı öznitelikleri listeler.  
  
|Veri tanımlayıcısı özniteliği|Açıklama|Varsayılan|  
|-------------------------------|-----------------|-------------|  
|`value`|Özelliğin geçerli değeri.|`undefined`|  
|`writable`|`true`veya `false`. Varsa `writable` ayarlanır `true`, özellik değeri değiştirilemiyor.|`false`|  
|`enumerable`|`true`veya `false`. Varsa `enumerable` ayarlanır `true`, özellik tarafından numaralandırılmış bir `for...in` deyimi.|`false`|  
|`configurable`|`true`veya `false`. Varsa `configurable` ayarlanır `true`özellik öznitelikleri değiştirilebilir ve özellik silinebilir.|`false`|  
  
 Tanımlayıcı yoksa bir `value`, `writable`, `get`, veya `set` özniteliği ve belirtilen özellik adı yok, veri özellik eklenir.  
  
 Zaman `configurable` özniteliği `false` ve `writable` olan `true`, `value` ve `writable` öznitelikleri değiştirilebilir.  
  
#### <a name="data-properties-added-without-using-defineproperty"></a>Veri defineProperty olmadan eklenen özelliklerini kullanma  
 Veri özelliği kullanmadan eklerseniz, `Object.defineProperty`, `Object.defineProperties`, veya `Object.create` İşlevler, `writable`, `enumerable`, ve `configurable` öznitelikleridir tüm kümesine `true`. Özellik eklendikten sonra bunu kullanarak değiştirebilirsiniz `Object.defineProperty` işlevi.  
  
 Veri özelliği eklemek için aşağıdaki yöntemleri kullanabilirsiniz:  
  
-   Giriş olarak atama işleci (=)`obj.color = "white";`  
  
-   Bir nesne olarak değişmez değer`obj = { color: "white", height: 5 };`  
  
-   Bölümünde açıklandığı gibi bir yapım işlevi [türlerini tanımlamak için oluşturucular kullanma](../../javascript/advanced/using-constructors-to-define-types.md)  
  
### <a name="accessor-properties"></a>Erişimci özellikleri  
 Bir *erişimci özelliği* özellik değerini ayarlayın ya da alınan her zaman bir kullanıcı tarafından sağlanan işlevi çağırır. Tanımlayıcı için bir erişimci özelliği içeren bir `get` öznitelik, bir `set` özniteliği ya da her ikisini de.  
  
 Aşağıdaki tabloda bir erişimci özellik tanımlayıcısı öznitelikleri listeler.  
  
|Erişimci tanımlayıcısı özniteliği|Açıklama|Varsayılan|  
|-----------------------------------|-----------------|-------------|  
|`get`|Özellik değeri döndüren bir işlev. İşlev hiç parametre yok.|`undefined`|  
|`set`|Özellik değeri ayarlar bir işlev. Atanacak değeri içeren bir parametre içeriyor.|`undefined`|  
|`enumerable`|`true`veya `false`. Varsa `enumerable` ayarlanır `true`, özellik tarafından numaralandırılmış bir `for...in` deyimi.|`false`|  
|`configurable`|`true`veya `false`. Varsa `configurable` ayarlanır `true`özellik öznitelikleri değiştirilebilir ve özellik silinebilir.|`false`|  
  
 Zaman bir `get` erişimci tanımlanmadı ve özellik değeri, erişmek için bir girişimde `undefined` döndürülür. Zaman bir `set` erişimci tanımlanmadı ve hiçbir şey olmaz erişimcisi özelliğine bir değer atamak için bir girişimde.  
  
### <a name="property-modifications"></a>Özellik değişiklikleri  
 Nesne zaten belirtilen adda bir özellik varsa, özellik öznitelikleri değiştirilmiştir. Özellik değiştirdiğinizde tanımlayıcısı belirtilmemiş öznitelikleri aynı kalır.  
  
 Varsa `configurable` özniteliği mevcut bir özellik olan `false`, yalnızca değişikliği değiştiriyor izin verilen `writable` özniteliğini `true` için `false`.  
  
 Veri özelliği bir erişimci özelliği ve tam tersini için değiştirebilirsiniz. Bunu yaptığınızda, `configurable` ve `enumerable` tanımlayıcısı belirtilmemiş öznitelikleri özelliğinde korunur. Tanımlayıcısı belirtilmemiş diğer öznitelikleri varsayılan değerlerine ayarlanır.  
  
 Birden fazla çağrı kullanarak yapılandırılabilir erişimci özellikleri artımlı olarak tanımlayabilirsiniz `Object.defineProperty` işlevi. Örneğin, bir `Object.defineProperty` çağrısı tanımlamak yalnızca bir `get` erişimcisi. Aynı özellik adına bir sonraki çağrı tanımlayabilir bir `set` erişimcisi. Özelliği daha sonra hem olurdu bir `get` erişimcisi ve `set` erişimcisi.  
  
 Mevcut bir özellik için geçerli bir tanımlayıcı nesnesi elde etmek için kullanabileceğiniz [Object.getOwnPropertyDescriptor işlevi](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
 Kullanabileceğiniz [Object.seal işlevi](../../javascript/reference/object-seal-function-javascript.md) ve [Object.freeze işlevi](../../javascript/reference/object-freeze-function-javascript.md) özellik öznitelikleri değiştirilmesini engellemek için.