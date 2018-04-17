---
title: SymTagEnum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- SymTagEnum enumeration
ms.assetid: 528a50cf-e13d-46ec-a98c-323d5d047de9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0268b6e46787e772f7343e5306713554687e869a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="symtagenum"></a>SymTagEnum
Simgenin türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
enum SymTagEnum {   
   SymTagNull,  
   SymTagExe,  
   SymTagCompiland,  
   SymTagCompilandDetails,  
   SymTagCompilandEnv,  
   SymTagFunction,  
   SymTagBlock,  
   SymTagData,  
   SymTagAnnotation,  
   SymTagLabel,  
   SymTagPublicSymbol,  
   SymTagUDT,  
   SymTagEnum,  
   SymTagFunctionType,  
   SymTagPointerType,  
   SymTagArrayType,   
   SymTagBaseType,   
   SymTagTypedef,   
   SymTagBaseClass,  
   SymTagFriend,  
   SymTagFunctionArgType,   
   SymTagFuncDebugStart,   
   SymTagFuncDebugEnd,  
   SymTagUsingNamespace,   
   SymTagVTableShape,  
   SymTagVTable,  
   SymTagCustom,  
   SymTagThunk,  
   SymTagCustomType,  
   SymTagManagedType,  
   SymTagDimension,  
   SymTagCallSite,  
   SymTagInlineSite,  
   SymTagBaseInterface,  
   SymTagVectorType,  
   SymTagMatrixType,  
   SymTagHLSLType  
};  
```  
  
## <a name="elements"></a>Öğeleri  
 `SymTagNull`  
 Simgenin türü yok sahip olduğunu gösterir.  
  
 `SymTagExe`  
 Simgenin bir .exe dosyası olduğunu gösterir. Yalnızca bir tane `SymTagExe` sembol deposu başına simgesi. Genel kapsamlı hizmet verir ve bir sözcük üst öğesi yok.  
  
 `SymTagCompiland`  
 Derlenecek dosya simgesi her derlenecek bileşeni sembol deposu gösterir. Yerel uygulamalar için `SymTagCompiland` simgeleri görüntüsüne bağlı nesne dosyaları karşılık gelir. Bazı Microsoft Ara dili (MSIL) görüntüleri türlerinde sınıfı başına bir derlenecek yoktur.  
  
 `SymTagCompilandDetails`  
 Simgenin derlenecek genişletilmiş öznitelikleri içerdiğini gösterir. Bu özellikleri alınırken derlenecek simgeleri yüklenirken gerektirebilir.  
  
 `SymTagCompilandEnv`  
 Simgenin derlenecek için tanımlanmış bir ortam dize olduğunu gösterir.  
  
 `SymTagFunction`  
 Simgenin bir işlevi olduğunu gösterir.  
  
 `SymTagBlock`  
 Simgenin iç içe geçmiş bir bloğu gösterir.  
  
 `SymTagData`  
 Simgenin veri olduğunu gösterir.  
  
 `SymTagAnnotation`  
 Simgenin bir kod ek açıklama için olduğunu belirtir. Bu simgenin alt öğeleri olan sabit veri dizeleri (`SymTagData`, `LocIsConstant`, `DataIsConstant`). Çoğu istemcileri bu simgeyi yoksay.  
  
 `SymTagLabel`  
 Simgenin bir etiket olduğunu gösterir.  
  
 `SymTagPublicSymbol`  
 Simgenin bir ortak simge olduğunu gösterir. Yerel uygulamalar için bu simgeyi görüntü bağlama sırasında karşılaşılan COFF dış simge kullanılır.  
  
 `SymTagUDT`  
 Simgenin bir kullanıcı tanımlı tür (yapısı, sınıf veya birleşimi) olduğunu gösterir.  
  
 `SymTagEnum`  
 Simgenin bir numaralandırma olduğunu gösterir.  
  
 `SymTagFunctionType`  
 Simgenin bir işlev imzası türü olduğunu gösterir.  
  
 `SymTagPointerType`  
 Simgenin bir işaretçi türü olduğunu gösterir.  
  
 `SymTagArrayType`  
 Simgenin bir dizi türü olduğunu gösterir.  
  
 `SymTagBaseType`  
 Simgenin bir taban türü olduğunu gösterir.  
  
 `SymTagTypedef`  
 Simgenin olduğunu gösteren bir `typedef`, diğer bir deyişle, başka bir tür için diğer ad.  
  
 `SymTagBaseClass`  
 Simgenin bir kullanıcı tanımlı türde bir taban sınıf olduğunu belirtir.  
  
 `SymTagFriend`  
 Simgenin bir kullanıcı tanımlı türde bir arkadaş olduğunu gösterir.  
  
 `SymTagFunctionArgType`  
 Simgenin bir işlev bağımsız değişkeni olduğunu gösterir.  
  
 `SymTagFuncDebugStart`  
 Simgenin işlevin başlangıç kodunu bitiş konumunu gösterir.  
  
 `SymTagFuncDebugEnd`  
 Simgenin işlevin epilog kodunu başlangıç konumunu gösterir.  
  
 `SymTagUsingNamespace`  
 Simgenin bir ad alanı adı, geçerli kapsamda etkin olduğunu gösterir.  
  
 `SymTagVTableShape`  
 Simgenin sanal tablo açıklamasını gösterir.  
  
 `SymTagVTable`  
 Simgenin bir sanal tablo işaretçi olduğunu gösterir.  
  
 `SymTagCustom`  
 Simgenin özel bir sembol olduğunu ve DIA. tarafından yorumlanmaz gösterir.  
  
 `SymTagThunk`  
 Simgenin 16 ve 32 bit kod arasında veri paylaşımı için kullanılan bir dönüştürücü olduğunu gösterir.  
  
 `SymTagCustomType`  
 Simgenin bir özel derleyici simge olduğunu gösterir.  
  
 `SymTagManagedType`  
 Simgenin meta verilerde olduğunu gösterir.  
  
 `SymTagDimension`  
 Simgenin FORTRAN çok boyutlu bir dizi olduğunu gösterir.  
  
 `SymTagCallSite`  
 Simgenin çağrısı site temsil ettiğini gösterir.  
  
 `SymTagInlineSite`  
 Simgenin satır içi sitenin temsil ettiğini gösterir.  
  
 `SymTagBaseInterface`  
 Simgenin bir temel arabirim olduğunu gösterir.  
  
 `SymTagVectorType`  
 Simgenin bir vektör türü olduğunu gösterir.  
  
 `SymTagMatrixType`  
 Simgenin bir matris türü olduğunu gösterir.  
  
 `SymTagHLSLType`  
 Simgenin yüksek düzey gölgelendirici dil türü olduğunu gösterir.  
  
## <a name="remarks"></a>Açıklamalar  
 Hata ayıklama dosya içindeki tüm sembolleri simgenin türünü belirten bir tanımlayıcı etiketine sahip.  
  
 Bu numaralandırma değerleri için yapılan bir çağrı tarafından döndürülen [Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) yöntemi.  
  
 Bu numaralandırma değerleri, belirli simge türü için arama kapsamını sınırlandırmak için aşağıdaki yöntemleri için geçirilir:  
  
-   [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: cvconst.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Numaralandırmalar ve yapılar](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Idiasession::findsymbolbyaddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)   
 [Idiasession::findsymbolbyrva](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)   
 [Idiasession::findsymbolbyrvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)   
 [Idiasession::findsymbolbytoken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)   
 [Idiasession::findsymbolbyva](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)   
 [Idiasession::findsymbolbyvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)   
 [Idiasession::findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)