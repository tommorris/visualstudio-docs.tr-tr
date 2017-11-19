---
title: CompilandDetails | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CompilandDetails symbol
ms.assetid: ddc7d794-c622-4c63-b2a6-72f8b2d0022a
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9bfbb1e05dadb18e9357e38d6ed660c248dccec4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="compilanddetails"></a>CompilandDetails
Derlenecek dosya bilgileri sembolleriyle arasında bölünür bir `SymTagCompiland` etiketi (düşük ayrıntı) ve bir `SymTagCompilandDetails` etiketi (yüksek ayrıntı). `SymTagCompilandDetails`Ek simgeleri yüklenmesini gerektirir. Ancak, çok sayıda ile kullanılamıyor derlenecek hakkında bilgi sağlayan bir `SymTagCompiland` simgesi.  
  
## <a name="properties"></a>Özellikler  
 Aşağıdaki tabloda bu simge türü için geçerli olan özellikleri gösterir.  
  
|Özellik|Veri türü|Açıklama|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_backendbuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|`DWORD`|Arka uç yapı derleyici sayısı.|  
|[Idiasymbol::get_backendmajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|`DWORD`|Derleyici arka uç ana sürüm numarası.|  
|[Idiasymbol::get_backendminor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|`DWORD`|Derleyici arka uç ikincil sürüm numarası.|  
|[Idiasymbol::get_compilername](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|`BSTR`|(Yalnızca DIA SDK V8.0 veya sonrası) bu derlenecek üretilen derleyici adı.|  
|[Idiasymbol::get_editandcontinueenabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|`TRUE`Düzenle ve devam et derleme etkinleştirilmişse.|  
|[Idiasymbol::get_frontendbuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|`DWORD`|Ön uç yapılandırma derleyici sayısı.|  
|[Idiasymbol::get_frontendmajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|`DWORD`|Derleyici ön uç ana sürüm numarası.|  
|[Idiasymbol::get_frontendminor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|`DWORD`|Derleyici ön uç alt sürüm numarasını.|  
|[Idiasymbol::get_hasdebugınfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|`BOOL`|`TRUE`Bu derlenecek hata ayıklama bilgileri (yalnızca DIA SDK V8.0 veya sonrası) varsa.|  
|[Idiasymbol::get_hasmanagedcode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|`BOOL`|`TRUE`Bu derlenecek (yalnızca DIA SDK v8.0 veya sonrası) yönetilen kodu içeriyorsa.|  
|[Idiasymbol::get_hassecuritychecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE`derlenecek dosya ile derlenen varsa [/GS (arabellek güvenlik denetimi)](/cpp/build/reference/gs-buffer-security-check) derleyici anahtarı (yalnızca DIA SDK V8.0 veya üzeri).|  
|[Idiasymbol::get_iscvtcıl](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|`BOOL`|`TRUE`derlenecek dosya ortak Ara dili (CIL) koddan yerel koda dönüştürüldü durumunda.|  
|[Idiasymbol::get_isdataaligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|`BOOL`|`TRUE`Kullanıcı tanımlı türler (UDT) için hizalı durumunda bazı bellek sınırı (yalnızca DIA SDK V8.0 veya sonrası) belirttiniz.|  
|[Idiasymbol::get_ishotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|`BOOL`|`TRUE`derlenecek dosya ile derlenen varsa [/hotpatch (düzeltme eki eklenebilen görüntü oluşturma)](/cpp/build/reference/hotpatch-create-hotpatchable-image) derleyici anahtarı (yalnızca DIA SDK v8.0 veya üzeri).|  
|[Idiasymbol::get_isltcg](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|`BOOL`|`TRUE`derlenecek dosya ile derlenen varsa [/LTCG (bağlama zamanı kodu oluşturma)](/cpp/build/reference/ltcg-link-time-code-generation) derleyici anahtarı (yalnızca DIA SDK V8.0 veya üzeri).|  
|[Idiasymbol::get_ismsılnetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|`BOOL`|Derlenecek dosya Microsoft Ara dili (MSIL) Modülü (yalnızca DIA SDK v8.0 veya sonrası) ise TRUE.|  
|[Idiasymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|`DWORD`|Kaynak kodu dili.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Derlenecek dosya simgesi.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|Sözcük üst simge kimliği.|  
|[Idiasymbol::get_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|`DWORD`|Derlenecek derlenmiş üzerinde platform (birini [CV_CPU_TYPE_e numaralandırması](../../debugger/debug-interface-access/cv-cpu-type-e.md) değerleri).|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|Dizin kimliği simgesi.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Döndürür `SymTagCompilandDetails` (birini [SymTagEnum numaralandırması](../../debugger/debug-interface-access/symtagenum.md) değerleri).|  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyicileri genellikle iki geçişi derleyici bilinen bir form gelir; bazı derleyici sürümler her geçişte ayrı bir program tarafından ele alınır. Bu ön uç ve arka uç derleyicileri sırasıyla, bu nedenle arka uç ve ön uç sürüm numaraları için Sembol Özellikleri denir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derlenecek dosya](../../debugger/debug-interface-access/compiland.md)   
 [Simge türlerinin sözcük hiyerarşisi](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)