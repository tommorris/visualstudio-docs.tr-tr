---
title: Idispatchex arabirimi | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDispatchEx interface, about IDispatchEx
- IDispatchEx interface
ms.assetid: 37a3303f-f78e-4b5b-aac8-b836c92819de
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a100a193f5e3abcb076fb8aaf3d64a0d0c38833
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchex-interface"></a>IDispatchEx Arabirimi
`IDispatchEx`, bir uzantısı olarak `IDispatch` özellikleri arabirimi, uygun komut dosyası dili gibi dinamik diller için. Bu bölümde açıklanmıştır `IDispatchEx` kendisini arasındaki farklar arabirim `IDispatch` ve `IDispatchEx`ve uzantıları için stratejinin. Okuyucular aşina olduğunuzu beklenir `IDispatch` ve erişimi `IDispatch` belgeleri.  
  
## <a name="remarks"></a>Açıklamalar  
 `IDispatch`Microsoft Visual Basic for temelde geliştirilmiştir. Birincil sınırlandırılmasıdır `IDispatch` olan bu nesneler statik olduğunu varsayar. Nesneleri çalışma zamanı sırasında değiştirmeyin olduğundan, diğer bir deyişle, tür bilgileri tam olarak bunları derleme zamanında tanımlayabilirsiniz. Visual Basic Scripting Edition (VBScript) gibi komut dosyası dilleri bulunan dinamik çalışma zamanı modelleri ve [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ve nesne modelleri dinamik HTML gerektiren daha esnek bir arabirim olarak.  
  
 `IDispatchEx`tüm hizmetlerini sağlamak için geliştirilmiştir `IDispatch` komut dosyası dili gibi daha dinamik geç bağlama dilleri için uygun olan bazı uzantılar yanı sıra. Ek özelliklerinin `IDispatchEx` tarafından sağlanan ötesinde `IDispatch` şunlardır:  
  
-   Yeni üyeler nesneye ("expando") ekleme — kullanmak `GetDispID` ile `fdexNameEnsure` bayrağı.  
  
-   Bir nesnenin üyelerine silmek — kullanmak `DeleteMemberByName` veya `DeleteMemberByDispID`.  
  
-   Büyük küçük harfe duyarlı gönderme işlemleri — kullanmak `fdexNameCaseSensitive` veya `fdexNameCaseInsensitive`.  
  
-   Örtük ada sahip üye için arama — kullanmak `fdexNameImplicit`.  
  
-   Bir nesnenin DISPID değerleri listeleme — kullanmak `GetNextDispID`.  
  
-   DISPID eşlemesinden öğe adı için — kullanmak `GetMemberName`.  
  
-   Nesne üyeleri özelliklerini alın — kullanmak `GetMemberProperties`.  
  
-   Yöntem çağırma ile `this` işaretçi — kullanmak `InvokeEx` DISPATCH_METHOD ile.  
  
-   Ad alanı üst nesnenin almak için ad alanları kavramı destekleyen tarayıcılarda izin — kullanmak `GetNameSpaceParent`.  
  
 Nesneleri destekleyen `IDispatchEx` de destekleyebilir `IDispatch` geriye dönük uyumluluk için. Destek nesnelerin dinamik doğasını `IDispatchEx` için birkaç şifrelemelerini `IDispatch` bu nesnelerin arabirimi. Örneğin, `IDispatch` aşağıdaki varsayım yapmaz:  
  
-   Üye ve parametre DISPID değerleri nesne ömrü boyunca sabit kalmalıdır. Bu, bir istemcinin DISPID değerleri bir kez elde ve daha sonra kullanmak üzere önbelleğe almasını sağlar.  
  
 Bu yana `IDispatchEx` ekleme ve silme üyelerinin geçerli DISPID değerleri kümesi durumda sabit sağlar. Ancak, `IDispatchEx` DISPID ve üye adı arasında eşleme sabit kalmasını gerektirir. Üye silinirse anlamına gelir:  
  
-   Aynı ada sahip bir üye oluşturulana kadar DISPID yeniden kullanılamaz.  
  
-   DISPID için geçerli kalır `GetNextDispID`.  
  
-   DISPID düzgün biçimde herhangi biri tarafından kabul edilmesi gereken `IDispatch` veya `IDispatchEx` yöntemleri — üye silindi olarak algılar ve bir uygun hata kodunu (genellikle DISP_E_MEMBERNOTFOUND veya S_FALSE) döndürür.  
  
## <a name="examples"></a>Örnekler  
 Bu [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] işlevi test() kod şunları gerçekleştirir:  
  
-   Çağırarak yeni bir nesne oluşturur `Object` oluşturucusu ve değişken Obj. yeni nesneye bir işaretçi atar  
  
-   Nesne Elem adlı yeni bir öğesi oluşturur ve bu öğeye işlevi kat gösteren bir işaretçi atar.  
  
-   Bu işlevi çağırır. Bir yöntem olarak çağrılan bu yana `this` işaretçi Obj. nesnesine başvuruyor Yeni bir öğe işlevi ekler çubuğuna nesne.  
  
 Tam HTML kodu verilmiştir:  
  
```  
<html>  
<body>  
<script type="text/javascript">  
function cat()  
{  
   // Create new element and assign the value 10  
   this.Bar = 10;  
}  
  
function test()  
{  
   // Construct new object  
   Obj = new Object();  
  
   // Create new element and assign function pointer  
   Obj.Elem = cat;  
  
   // Call Elem method ("this" == Obj)  
   Obj.Elem();  
  
   // Obj.Bar now exists  
}  
test();  
</script>  
</body>  
</html>  
```  
  
 Bu aynı Web sayfasında yerleştirilmiş bir denetimin bir gönderme işaretçi tarayıcıdan komut dosyası motorları elde edilemedi. Denetimin ardından işlevi test() uygulamak:  
  
```  
<html>  
<body>  
<script type="text/javascript">  
function cat()  
{  
   // Create new element and assign the value 10  
   this.Bar = 10;  
}  
</script>  
<object id="test" <CLASSID="CLSID:9417DB5D-FA2A-11D0-8CB3-00C04FC2B085">>  
</object>  
</body>  
</html>  
```  
  
 Kod denetimden, test, aynı şeyi yapar [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] işlevi `test()`. Bu dağıtım çağrılar içine çalışan yapılır Not [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] altyapısı ve altyapı durumunu değiştirin:  
  
-   Cat işlevini kullanarak gönderme işaretçisini alır `GetDispID()`.  
  
-   Nesne işlevini kullanarak gönderme işaretçisini alır `GetDispID()`.  
  
-   Nesne işlev çağrısı yaparak bir nesne oluşturur `InvokeEx()` ve yeni oluşturulan nesnesine gönderme işaretçi alır.  
  
-   Elem, yeni bir öğe nesnesi kullanılarak oluşturur `GetDispID()` ile `fdexNameEnsure` bayrağı.  
  
-   Gönderme işaretçi öğesi kullanarak kat koyar `InvokeEx()`.  
  
-   Cat gönderme işaretçisine çağırarak bir yöntem olarak çağırır `InvokeEx()` ve gönderme işaretçiyi yapılandırılmış nesne olarak geçirme `this` işaretçi.  
  
-   Yeni bir öğe kat yöntemi oluşturur çubuğunda geçerli `this` nesnesi.  
  
-   Doğrular yeni öğe çubuğu, oluşturulan nesneyi kullanarak öğelerini numaralandırma tarafından oluşturulan `GetNextDispID()`.  
  
 Kodu test denetimi için:  
  
```  
   BOOL test(IDispatchEx *pdexScript)  
   {  
      HRESULT hr;  
      VARIANT var;  
      DISPID dispid, putid;  
      BOOL retval = FALSE;  
      BSTR bstrName = NULL;  
      IDispatch   *pdispObj = NULL, *pdispCat = NULL;  
      IDispatchEx *pdexObj = NULL;  
      DISPPARAMS dispparams, dispparamsNoArgs = {NULL, NULL, 0, 0};  
  
      // Get dispatch pointer for "cat"  
      bstrName = SysAllocString(OLESTR("cat"));  
         if (bstrName == NULL) goto LDone;  
      hr = pdexScript->GetDispID(bstrName, 0, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
      hr = pdexScript->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_PROPERTYGET, &dispparamsNoArgs,   
         &var, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
      pdispCat = var.pdispVal;  
  
      // Create object by calling "Object" constructor  
      bstrName = SysAllocString(OLESTR("Object"));  
         if (NULL == bstrName) goto LDone;  
      hr = pdexScript->GetDispID(bstrName, 0, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
      hr = pdexScript->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_CONSTRUCT, &dispparamsNoArgs,   
         &var, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
      pdispObj = var.pdispVal;  
      hr = pdispObj->QueryInterface(IID_IDispatchEx, (void **)&pdexObj);  
         if (FAILED(hr)) goto LDone;  
  
      // Create new element in object  
      bstrName = SysAllocString(OLESTR("Elem"));  
         if (NULL == bstrName) goto LDone;  
      hr = pdexObj->GetDispID(bstrName, fdexNameEnsure, &dispid);  
         if (FAILED(hr)) goto LDone;  
      SysFreeString(bstrName);  
         bstrName = NULL;  
  
      // Assign "cat" dispatch pointer to element  
      putid = DISPID_PROPERTYPUT;  
      var.vt = VT_DISPATCH;  
      var.pdispVal = pdispCat;  
      dispparams.rgvarg = &var;  
      dispparams.rgdispidNamedArgs = &putid;  
      dispparams.cArgs = 1;  
      dispparams.cNamedArgs = 1;  
      hr = pdexObj->InvokeEx(dispid, LOCALE_USER_DEFAULT,   
         DISPATCH_PROPERTYPUTREF, &dispparams,  
         NULL, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
  
      // Invoke method with "this" pointer  
      putid = DISPID_THIS;  
      var.vt = VT_DISPATCH;  
      var.pdispVal = pdispObj;  
      dispparams.rgvarg = &var;  
      dispparams.rgdispidNamedArgs = &putid;  
      dispparams.cArgs = 1;  
      dispparams.cNamedArgs = 1;  
      hr = pdexObj->InvokeEx(dispid, LOCALE_USER_DEFAULT,  
         DISPATCH_METHOD, &dispparams,  
            NULL, NULL, NULL);  
         if (FAILED(hr)) goto LDone;  
  
      // Confirm that new element "Bar" is in object  
      hr = pdexObj->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);  
      while (hr == NOERROR)  
      {  
            hr = pdexObj->GetMemberName(dispid, &bstrName);  
            if (FAILED(hr)) goto LDone;  
            retval = !wcscmp(bstrName, OLESTR("Bar"));  
            SysFreeString(bstrName);  
            bstrName = NULL;  
            if (retval) goto LDone;  
         hr = pdexObj->GetNextDispID(fdexEnumAll, dispid, &dispid);  
      }  
LDone:  
   SysFreeString(bstrName);  
   if (pdispCat != NULL)  
      pdispCat->Release();  
   if (pdispObj != NULL)  
      pdispObj->Release();  
   if (pdexObj != NULL)  
      pdexObj->Release();  
  
   return retval;  
   }  
```  
  
## <a name="methods"></a>Yöntemler  
 [Idispatchex yöntemleri](../../winscript/reference/idispatchex-methods.md)