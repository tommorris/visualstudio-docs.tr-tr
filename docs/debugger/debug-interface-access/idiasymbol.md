---
title: Idiasymbol | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol interface
ms.assetid: 01ad328a-736c-4933-a9f8-c2ded19ddd8c
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e4954c691795f71704aab7493ef8df3dbb3f958
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbol"></a>IDiaSymbol
Sembol örneğini özelliklerini açıklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaSymbol : IUnknown  
```  
  
## <a name="methods-in-alphabetical-order"></a>Alfabetik sırada yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaSymbol`.  
  
> [!NOTE]
>  Simgeler simge türüne bağlı olarak bu yöntemlerden yalnızca bazıları için anlamlı veri döndürür. Bir yöntem döndürüyorsa `S_OK`, sonra da bu yöntem anlamlı veri döndürdü.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiasymbol::findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)|Simgenin tüm alt öğeleri alır.|  
|[IDiaSymbol::findChildrenEx](../../debugger/debug-interface-access/idiasymbol-findchildrenex.md)|Alt simge alır. Bu yöntem, genişletilmiş sürümüdür [Idiasymbol::findchildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md).|  
|[IDiaSymbol::findChildrenExByAddr](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyaddr.md)|Belirtilen bir adres geçerli öğenin alt öğelerine simgenin alır.|  
|[IDiaSymbol::findChildrenExByRVA](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyrva.md)|Belirtilen sanal adreste (RVA) geçerli öğenin alt öğelerine simgenin alır.|  
|[IDiaSymbol::findChildrenExByVA](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyva.md)|Belirtilen sanal adresinde geçerli öğenin alt öğelerine simgenin alır.|  
|[IDiaSymbol::findInlineFramesByAddr](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyaddr.md)|Tüm satır içi çerçeveler belirli bir adresi üzerinde yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findInlineFramesByRVA](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyrva.md)|Tüm satır içi çerçeveler bir adresinde belirtilen göreli sanal (RVA) yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findInlineFramesByVA](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyva.md)|Tüm satır içi çerçeveler belirtilen sanal adresine (VA) yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findInlineeLines](../../debugger/debug-interface-access/idiasymbol-findinlineelines.md)|Satır numarası bilgilerini doğrudan içermesinden, tüm işlevleri veya dolaylı olarak, bu simgeyi yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findInlineeLinesByAddr](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyaddr.md)|Satır numarası bilgilerini doğrudan veya dolaylı olarak, bu simge belirtilen adres aralığındaki içermesinden, bulunan tüm işlevlerin yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findInlineeLinesByRVA](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyrva.md)|Satır numarası bilgilerini doğrudan veya dolaylı olarak, belirtilen göreli sanal adres (RVA) içinde bu simgeyi içermesinden, bulunan tüm işlevlerin yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findInlineeLinesByVA](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyva.md)|Satır numarası bilgilerini doğrudan veya dolaylı olarak, belirtilen sanal adres (VA) içinde bu simgeyi içermesinden, bulunan tüm işlevlerin yinelemek bir istemci izin veren bir numaralandırmasını alır.|  
|[IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasymbol-findsymbolsbyrvaforacceleratorpointertag.md)|Bu yöntem karşılık gelen bir etiket değeri verildiğinde, bu saplama işlevinde, belirtilen bir göreli sanal adreste bulunan sembolleri numaralandırması döndürür.|  
|[IDiaSymbol::findSymbolsForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasymbol-findsymbolsforacceleratorpointertag.md)|Hızlandırıcı işaretçi etiket sayısı C++ AMP saplama işlevinde döndürür.|  
|[IDiaSymbol::get_acceleratorPointerTags](../../debugger/debug-interface-access/idiasymbol-get-acceleratorpointertags.md)|Karşılık gelen tüm Hızlandırıcı işaretçi etiket değerleri bir C++ AMP Hızlandırıcı saplama işlevi döndürür.|  
|[Idiasymbol::get_access](../../debugger/debug-interface-access/idiasymbol-get-access.md)|Sınıf üyesine erişim değiştiricisi alır.|  
|[Idiasymbol::get_addressoffset](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|Bir adresi konumu uzaklık parçası alır.|  
|[Idiasymbol::get_addresssection](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|Bir adresi konumu bölüm parçası alır.|  
|[Idiasymbol::get_addresstaken](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|Başka bir simge bu adresi başvuruda bulunup bulunmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_age](../../debugger/debug-interface-access/idiasymbol-get-age.md)|Program veritabanı geçerlilik süresi değerini alır.|  
|[Idiasymbol::get_arrayındextype](../../debugger/debug-interface-access/idiasymbol-get-arrayindextype.md)|Dizi dizini türü simge tanımlayıcısını alır.|  
|[Idiasymbol::get_arrayındextypeıd](../../debugger/debug-interface-access/idiasymbol-get-arrayindextypeid.md)|Simgenin dizi dizini türü tanımlayıcısını alır.|  
|[Idiasymbol::get_backendmajor](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|Arka uç ana sürüm numarasını alır.|  
|[Idiasymbol::get_backendminor](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|Arka uç alt sürüm numarasını alır.|  
|[Idiasymbol::get_backendbuild](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|Arka uç yapı numarası alır.|  
|[IDiaSymbol::get_baseDataOffset](../../debugger/debug-interface-access/idiasymbol-get-basedataoffset.md)|Temel veri uzaklığı alır.|  
|[IDiaSymbol::get_baseDataSlot](../../debugger/debug-interface-access/idiasymbol-get-basedataslot.md)|Temel veri yuvası alır.|  
|[IDiaSymbol::get_baseSymbol](../../debugger/debug-interface-access/idiasymbol-get-basesymbol.md)|İşaretçinin temel aldığı simge alır.|  
|[IDiaSymbol::get_baseSymbolId](../../debugger/debug-interface-access/idiasymbol-get-basesymbolid.md)|İşaretçinin temel aldığı simgesi kimliği alır.|  
|[Idiasymbol::get_basetype](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|Basit bir tür türü etiket alır.|  
|[Idiasymbol::get_bitposition](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|Bir konum bit konumunu alır.|  
|[IDiaSymbol::get_builtInKind](../../debugger/debug-interface-access/idiasymbol-get-builtinkind.md)|HLSL türünü yerleşik alır.|  
|[Idiasymbol::get_callingconvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)|Bir yöntemin çağırma bir göstergesi döndürür.|  
|[Idiasymbol::get_classparent](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|Simgenin sınıfı üst bir başvuru alır.|  
|[Idiasymbol::get_classparentıd](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|Simgenin sınıfı üst tanımlayıcısını alır.|  
|[Idiasymbol::get_code](../../debugger/debug-interface-access/idiasymbol-get-code.md)|Simgenin bir kod adresine başvuran olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_compilergenerated](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|Simgenin derleyicinin ürettiği olduğunu gösteren bir bayrak alır.|  
|[Idiasymbol::get_compilername](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|Derleyicinin oluşturmak için kullanılan adını alır [derlenecek](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_constructor](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|Kullanıcı tanımlı veri türü bir oluşturucuya sahip olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_container](../../debugger/debug-interface-access/idiasymbol-get-container.md)|Bu simgenin içeren simge alır.|  
|[Idiasymbol::get_consttype](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|Kullanıcı tanımlı veri türü sabit olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_Count](../../debugger/debug-interface-access/idiasymbol-get-count.md)|Bir liste veya dizideki öğe sayısını alır.|  
|[IDiaSymbol::get_countLiveRanges](../../debugger/debug-interface-access/idiasymbol-get-countliveranges.md)|Geçerli adres aralıklarını yerel simgesiyle ilişkili sayısını alır.|  
|[Idiasymbol::get_customcallingconvention](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|İşlev özel çağırma kullanıp kullanmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_databytes](../../debugger/debug-interface-access/idiasymbol-get-databytes.md)|OEM simgesi veri baytını alır.|  
|[Idiasymbol::get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|Veri simgesi değişken sınıflandırmasını alır.|  
|[Idiasymbol::get_editandcontinueenabled](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|Derlenmiş program veya birim Düzenle ve devam et özelliklerini açıklayan bayrağı alır.|  
|[Idiasymbol::get_farreturn](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|İşlev kadar dönüş kullanıp kullanmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_frontendmajor](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|Ön uç ana sürüm numarasını alır.|  
|[Idiasymbol::get_frontendminor](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|Ön uç alt sürüm numarasını alır.|  
|[Idiasymbol::get_frontendbuild](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|Ön uç yapı numarası alır.|  
|[Idiasymbol::get_function](../../debugger/debug-interface-access/idiasymbol-get-function.md)|Ortak simgenin bir işleve başvuruyor olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_guid](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|Simgenin GUID alır.|  
|[Idiasymbol::get_hasalloca](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|İşlev çağrısı içerip içermediğini gösteren bir bayrak alır `alloca`.|  
|[Idiasymbol::get_hasassignmentoperator](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|Kullanıcı tanımlı veri türü için tanımlı hiçbir atama işleçleri olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_hascastoperator](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|Kullanıcı tanımlı veri türü için tanımlı hiçbir atama işleçleri olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_hasdebugınfo](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|Derlenecek tüm hata ayıklama bilgileri içerip içermediğini gösteren bir bayrak alır.|  
|[Idiasymbol::get_haseh](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|İşlev stili C++ özel durum işleyici olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_haseha](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|İşlev zaman uyumsuz özel durum işleyicisi olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_hasınlasm](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|İşlev satır içi derleme olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_haslongjump](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|İşlev longjmp komutu (C-style özel durum işleme parçası) içerip içermediğini gösteren bir bayrak alır.|  
|[Idiasymbol::get_hasmanagedcode](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|Yönetilen kod modülü içerip içermediğini gösteren bir bayrak alır.|  
|[Idiasymbol::get_hasnestedtypes](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|Kullanıcı tanımlı veri türü tür tanımları iç içe olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_hassecuritychecks](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|İşlev veya derlenecek derlenmiş güvenlik denetimlerini olup olmadığını gösteren bir bayrak alır (aracılığıyla [/GS (arabellek güvenlik denetimi)](/cpp/build/reference/gs-buffer-security-check) derleyici anahtar).|  
|[Idiasymbol::get_hasseh](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|İşlev Win32 stili yapılandırılmış özel durum işleme olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_hassetjump](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|İşlev setjmp komutu içerip içermediğini gösteren bir bayrak alır.|  
|[Idiasymbol::get_indirectvirtualbaseclass](../../debugger/debug-interface-access/idiasymbol-get-indirectvirtualbaseclass.md)|Kullanıcı tanımlı veri türü dolaylı bir sanal temel sınıf olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_ınlspec](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|İşlev satır içi özniteliğiyle işaretlenmiş olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_interruptreturn](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|İşlevi bir dönüş kesme yönergesi olup olmadığını gösteren bir bayrak alır.|  
|[Idiasymbol::get_intro](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|İşlev temel sınıf sanal işlev olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_isAcceleratorGroupSharedLocal](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorgroupsharedlocal.md)|Simgenin bir grup paylaşılan yerel değişkende için C++ AMP Hızlandırıcı derlenmiş kod karşılık gelen olup olmadığını gösteren bir bayrak alır.|  
|[IDiaSymbol::get_isAcceleratorPointerTagLiveRange](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorpointertagliverange.md)|Simgenin karşılık gelen olup olmadığını belirten bir bayrak alır *tanımı aralığı simgesi* için C++ AMP Hızlandırıcı derlenmiş kodda bir işaretçi değişkeninin etiketi bileşeni. Tanım aralığı simgenin adreslerinin bir aralık için bir değişken konumudur.|  
|[IDiaSymbol::get_isAcceleratorStubFunction](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorstubfunction.md)|Simgenin bir üst düzey işlevi simge karşılık gelen bir Hızlandırıcı için derlenmiş bir gölgelendirici için karşılık gelen olup olmadığını gösterir bir `parallel_for_each` çağırın.|  
|[Idiasymbol::get_isaggregated](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|Veri toplama birçok simgelerin bir parçası olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|Sembol dosyası C türleri içerip içermediğini gösteren bir bayrak alır.|  
|[Idiasymbol::get_iscvtcıl](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|Modülü yerel koda ortak Ara dili (CIL gelen) dönüştürüldü olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_isdataaligned](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|Belirli bir sınırı hizalanmış öğeler kullanıcı tanımlı veri türü olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_isHLSLData](../../debugger/debug-interface-access/idiasymbol-get-ishlsldata.md)|Bu simgenin yüksek düzey gölgelendirici dili (HLSL) veri temsil edip etmediğini belirler.|  
|[Idiasymbol::get_ishotpatchable](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|Modülü ile derlenen olup olmadığını belirten bir bayrak alır [/hotpatch (düzeltme eki eklenebilen görüntü oluşturma)](/cpp/build/reference/hotpatch-create-hotpatchable-image) derleyici anahtar.|  
|[Idiasymbol::get_isltcg](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|Yönetilen derlenecek bağlayıcı'nın LTCG ile bağlı olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_isMatrixRowMajor](../../debugger/debug-interface-access/idiasymbol-get-ismatrixrowmajor.md)|Matrisin satır büyük olup olmadığını belirtir.|  
|[Idiasymbol::get_ismsılnetmodule](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|Yönetilen derlenecek (yalnızca meta veriler içeren) bir .netmodule olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_isMultipleInheritance](../../debugger/debug-interface-access/idiasymbol-get-ismultipleinheritance.md)|Belirtir olup olmadığını `this` veri üyesi birden çok devralma ile işaretçi işaret eder.|  
|[Idiasymbol::get_isnaked](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|İşlev olup olmadığını gösteren bir bayrak alır [naked](/cpp/cpp/naked-cpp) özniteliği.|  
|[IDiaSymbol::get_isOptimizedAway](../../debugger/debug-interface-access/idiasymbol-get-isoptimizedaway.md)|Değişkeni yerine getirilip getirilmeyeceğini belirtir.|  
|[IDiaSymbol::get_isPointerBasedOnSymbolValue](../../debugger/debug-interface-access/idiasymbol-get-ispointerbasedonsymbolvalue.md)|Belirtir olup olmadığını `this` işaretçi bir sembol değeri temel alır.|  
|[IDiaSymbol::get_isPointerToDataMember](../../debugger/debug-interface-access/idiasymbol-get-ispointertodatamember.md)|Bu simgenin veri üyesi için bir işaretçi olup olmadığını belirtir.|  
|[IDiaSymbol::get_isPointerToMemberFunction](../../debugger/debug-interface-access/idiasymbol-get-ispointertomemberfunction.md)|Bu simgenin üye işlevi için bir işaretçi olup olmadığını belirtir.|  
|[IDiaSymbol::get_isReturnValue](../../debugger/debug-interface-access/idiasymbol-get-isreturnvalue.md)|Değişkeni dönüş değeri taşır olup olmadığını belirtir.|  
|[IDiaSymbol::get_isSdl](../../debugger/debug-interface-access/idiasymbol-get-issdl.md)|Modül/SDL seçeneğiyle derlendiği olup olmadığını belirtir.|  
|[IDiaSymbol::get_isSingleInheritance](../../debugger/debug-interface-access/idiasymbol-get-issingleinheritance.md)|Belirtir olup olmadığını `this` tek devralma veri üyesiyle işaretçi işaret eder.|  
|[Idiasymbol::get_issplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|Veri toplama ayrı simgelerin bölme olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_isstatic](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|Bir işlev veya dönüştürücü katman statik olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_isstripped](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|Özel sembolleri simge dosyasından atılmış olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_isVirtualInheritance](../../debugger/debug-interface-access/idiasymbol-get-isvirtualinheritance.md)|Belirtir olup olmadığını `this` sanal devralma veri üyesiyle işaretçi işaret eder.|  
|[Idiasymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)|Kaynak dili alır.|  
|[Idiasymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)|Bu simge ile temsil edilen nesne tarafından kullanılan belleğin bayt sayısını alır.|  
|[Idiasymbol::get_lexicalparent](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|Simgenin sözcük üst bir başvuru alır.|  
|[Idiasymbol::get_lexicalparentıd](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|Simgenin sözcük üst tanımlayıcısını alır.|  
|[Idiasymbol::get_libraryname](../../debugger/debug-interface-access/idiasymbol-get-libraryname.md)|Nesne yüklendiği kitaplığı veya nesne dosyasının dosya adını alır.|  
|[IDiaSymbol::get_liveRangeLength](../../debugger/debug-interface-access/idiasymbol-get-liverangelength.md)|Yerel simgenin geçerli adres aralığını uzunluğunu döndürür.|  
|[IDiaSymbol::get_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md)|Yerel simgenin geçerli olduğu başlangıç adresi aralığı bölüm bölümünü döndürür.|  
|[IDiaSymbol::get_liveRangeStartAddressOffset](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddressoffset.md)|Yerel simgenin geçerli olduğu başlangıç adresi aralığı uzaklık bölümünü döndürür.|  
|[IDiaSymbol::get_liveRangeStartRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-liverangestartrelativevirtualaddress.md)|Yerel simgenin geçerli adres aralığının başlangıcını döndürür.|  
|[Idiasymbol::get_locationtype](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|Bir veri simgenin konumu türünü alır.|  
|[Idiasymbol::get_lowerbound](../../debugger/debug-interface-access/idiasymbol-get-lowerbound.md)|FORTRAN dizi boyutu alt sınırı alır.|  
|[Idiasymbol::get_lowerboundıd](../../debugger/debug-interface-access/idiasymbol-get-lowerboundid.md)|FORTRAN dizi boyutu alt sınırı simge tanımlayıcısını alır.|  
|[Idiasymbol::get_machinetype](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|Hedef CPU türünü alır.|  
|[Idiasymbol::get_managed](../../debugger/debug-interface-access/idiasymbol-get-managed.md)|Simgenin başvurduğu olup olmadığını gösteren kod yönetilen bir bayrak alır.|  
|[IDiaSymbol::get_memorySpaceKind](../../debugger/debug-interface-access/idiasymbol-get-memoryspacekind.md)|Bellek alanı türü alır.|  
|[Idiasymbol::get_msil](../../debugger/debug-interface-access/idiasymbol-get-msil.md)|Simgenin Microsoft Ara dili (MSIL) koda başvuran olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_name](../../debugger/debug-interface-access/idiasymbol-get-name.md)|Simgenin adını alır.|  
|[Idiasymbol::get_nested](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|Kullanıcı tanımlı veri türü iç içe yerleştirilmiş olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_noınline](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|İşlevi ile işaretlenmiş olup olmadığını belirten bir bayrak alır [noinline](/cpp/cpp/noinline) özniteliği.|  
|[Idiasymbol::get_noreturn](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|İşlevi ile bildirilmiş olup olmadığını belirten bir bayrak alır [noreturn](/cpp/cpp/noreturn) özniteliği.|  
|[Idiasymbol::get_nostackordering](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|Yığın sıralamaya arabellek yığını denetleme bir parçası olarak yapılabilir olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_notreached](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|İşlev veya etiketi hiçbir zaman ulaşıldığında olup olmadığını belirten bir bayrak alır.|  
|[IDiaSymbol::get_numberOfAcceleratorPointerTags](../../debugger/debug-interface-access/idiasymbol-get-numberofacceleratorpointertags.md)|Hızlandırıcı işaretçi etiket sayısı C++ AMP saplama işlevinde döndürür.|  
|[IDiaSymbol::get_numberOfModifiers](../../debugger/debug-interface-access/idiasymbol-get-numberofmodifiers.md)|Özgün türüne uygulanacağını değiştiricileri sayısını alır.|  
|[IDiaSymbol::get_numberOfRegisterIndices](../../debugger/debug-interface-access/idiasymbol-get-numberofregisterindices.md)|YAZMAÇ dizinlerini sayısını alır.|  
|[IDiaSymbol::get_numberOfRows](../../debugger/debug-interface-access/idiasymbol-get-numberofrows.md)|Matrisin satır sayısını alır.|  
|[IDiaSymbol::get_numberOfColumns](../../debugger/debug-interface-access/idiasymbol-get-numberofcolumns.md)|Matristeki sütun sayısını alır.|  
|[IDiaSymbol::get_objectFileName](../../debugger/debug-interface-access/idiasymbol-get-objectfilename.md)|Nesne dosya adı alır.|  
|[Idiasymbol::get_objectpointertype](../../debugger/debug-interface-access/idiasymbol-get-objectpointertype.md)|Bir sınıf yöntemi için nesne işaretçisi türünü alır.|  
|[Idiasymbol::get_oemıd](../../debugger/debug-interface-access/idiasymbol-get-oemid.md)|Simgenin alır `oemId` değeri.|  
|[Idiasymbol::get_oemsymbolıd](../../debugger/debug-interface-access/idiasymbol-get-oemsymbolid.md)|Simgenin alır `oemSymbolId` değeri.|  
|[Idiasymbol::get_offset](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|Simgenin konumu uzaklığı alır.|  
|[Idiasymbol::get_optimizedcodedebugınfo](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|İşlev veya etiketi en iyi duruma getirilmiş kod içerip içermediğini gösteren bir bayrak alır debug bilgi.|  
|[Idiasymbol::get_overloadedoperator](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|Kullanıcı tanımlı veri türü işleçleri aşırı yüklü olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_packed](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|Kullanıcı tanımlı veri türü dolu olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_platform](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|Derlenecek dosya ve program derlenmiş platform türünü alır.|  
|[Idiasymbol::get_pure](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|Bu işlev saf olup olmadığını belirten bir bayrak alır sanal.|  
|[Idiasymbol::get_rank](../../debugger/debug-interface-access/idiasymbol-get-rank.md)|FORTRAN boyutlu bir diziye sırasını alır.|  
|[Idiasymbol::get_reference](../../debugger/debug-interface-access/idiasymbol-get-reference.md)|Bir işaretçi türü bir başvuru olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_registerıd](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|Konumun kayıt Belirleyicisi alır.|  
|[IDiaSymbol::get_registerType](../../debugger/debug-interface-access/idiasymbol-get-registertype.md)|Kayıt türünü alır.|  
|[Idiasymbol::get_relativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|Konumun göreli sanal adres (RAV) alır.|  
|[IDiaSymbol::get_restrictedType](../../debugger/debug-interface-access/idiasymbol-get-restrictedtype.md)|Belirtir olup olmadığını `this` işaretçi bayrak olarak kısıtlı.|  
|[IDiaSymbol::get_samplerSlot](../../debugger/debug-interface-access/idiasymbol-get-samplerslot.md)|Sampler yuvası alır.|  
|[Idiasymbol::get_scoped](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|Kullanıcı tanımlı veri türü Global olmayan bir sözcük kapsamında görünür olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_signature](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|Simgenin imza değeri alır.|  
|[IDiaSymbol::get_sizeInUdt](../../debugger/debug-interface-access/idiasymbol-get-sizeinudt.md)|Kullanıcı tanımlı bir tür üyesi boyutunu alır.|  
|[Idiasymbol::get_slot](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|Konumun Yuva sayısını alır.|  
|[Idiasymbol::get_sourcefilename](../../debugger/debug-interface-access/idiasymbol-get-sourcefilename.md)|Kaynak dosyasının dosya adını alır.|  
|[IDiaSymbol::getSrcLineOnTypeDefn](../../debugger/debug-interface-access/idiasymbol-getsrclineontypedefn.md)|Belirtilen bir kullanıcı tanımlı tür tanımlandığı belirtmek kaynak dosya ve satır numarasını alır.|  
|[IDiaSymbol::get_stride](../../debugger/debug-interface-access/idiasymbol-get-stride.md)|Matris veya strided dizi STRIDE alır.|  
|[IDiaSymbol::get_subType](../../debugger/debug-interface-access/idiasymbol-get-subtype.md)|Sub türünü alır.|  
|[IDiaSymbol::get_subTypeId](../../debugger/debug-interface-access/idiasymbol-get-subtypeid.md)|Alt türü kimliğini alır.|  
|[Idiasymbol::get_symbolsfilename](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|Simgeler yüklü dosyanın adını alır.|  
|[Idiasymbol::get_symındexıd](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|Benzersiz bir simge tanımlayıcısını alır.|  
|[Idiasymbol::get_symtag](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|Simge türü sınıflandırıcı alır.|  
|[Idiasymbol::get_targetoffset](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|Dönüştürücü hedef uzaklık bölümünü alır.|  
|[Idiasymbol::get_targetrelativevirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|Dönüştürücü hedefinin göreli sanal adres (RAV) alır.|  
|[Idiasymbol::get_targetsection](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|Dönüştürücü hedef adres bölümünü alır.|  
|[Idiasymbol::get_targetvirtualaddress](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|Dönüştürücü hedef sanal adres (VA) alır.|  
|[IDiaSymbol::get_textureSlot](../../debugger/debug-interface-access/idiasymbol-get-textureslot.md)|Doku yuvası alır.|  
|[Idiasymbol::get_thisadjust](../../debugger/debug-interface-access/idiasymbol-get-thisadjust.md)|Mantıksal alır `this` adjustor yöntemi.|  
|[Idiasymbol::get_thunkordinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|Bir işlevin dönüştürücü türü alır.|  
|[Idiasymbol::get_timestamp](../../debugger/debug-interface-access/idiasymbol-get-timestamp.md)|Temel alınan yürütülebilir dosyanın zaman damgası alır.|  
|[Idiasymbol::get_token](../../debugger/debug-interface-access/idiasymbol-get-token.md)|Yönetilen işlev veya değişken meta verileri belirtecini alır.|  
|[Idiasymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)|İşlev imzası başvuru alır.|  
|[Idiasymbol::get_typeıd](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|Simgenin türü tanımlayıcısını alır.|  
|[Idiasymbol::get_types](../../debugger/debug-interface-access/idiasymbol-get-types.md)|Bu simgenin derleyici özgü tür değerleri alır.|  
|[Idiasymbol::get_typeıds](../../debugger/debug-interface-access/idiasymbol-get-typeids.md)|Bu simgenin derleyici özel tür tanımlayıcı değerleri alır.|  
|[IDiaSymbol::get_uavSlot](../../debugger/debug-interface-access/idiasymbol-get-uavslot.md)|Uav yuvası alır.|  
|[Idiasymbol::get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|Kullanıcı tanımlı bir tür (UDT) çeşitli alır.|  
|[Idiasymbol::get_unalignedtype](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|Kullanıcı tanımlı veri türü hizalanmamış olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_undecoratedname](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|Donatılmış, C++ veya bağlantı, adı ve adını alır.|  
|[Idiasymbol::get_undecoratednameex](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|Uzantısı `get_undecoratedName` yöntemi bir uzantı alanı değerini temel ve adını alır.|  
|[IDiaSymbol::get_unmodifiedTypeId](../../debugger/debug-interface-access/idiasymbol-get-unmodifiedtypeid.md)|Özgün (değiştirilmemiş) türü Kimliğini alır.|  
|[Idiasymbol::get_upperbound](../../debugger/debug-interface-access/idiasymbol-get-upperbound.md)|FORTRAN dizi boyut üst sınırını alır.|  
|[Idiasymbol::get_upperboundıd](../../debugger/debug-interface-access/idiasymbol-get-upperboundid.md)|FORTRAN dizi boyutu üst sınırının simge tanımlayıcısını alır.|  
|[Idiasymbol::get_value](../../debugger/debug-interface-access/idiasymbol-get-value.md)|Bir sabit değerini alır.|  
|[Idiasymbol::get_virtual](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|İşlev sanal olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_virtualaddress](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|Konumun sanal adres (VA) alır.|  
|[Idiasymbol::get_virtualbaseclass](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseclass.md)|Kullanıcı tanımlı veri türü sanal bir temel sınıf olup olmadığını belirten bir bayrak alır.|  
|[Idiasymbol::get_virtualbasedispındex](../../debugger/debug-interface-access/idiasymbol-get-virtualbasedispindex.md)|Sanal Taban öteleme tablo dizine alır.|  
|[Idiasymbol::get_virtualbaseoffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|Sanal işlevinin sanal işlev tablosundaki uzaklık alır.|  
|[Idiasymbol::get_virtualbasepointeroffset](../../debugger/debug-interface-access/idiasymbol-get-virtualbasepointeroffset.md)|Sanal Taban işaretçisinin uzaklığını alır.|  
|[Idiasymbol::get_virtualbasetabletype](../../debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype.md)|Bir sanal temel tablo işaretçi türünü alır.|  
|[Idiasymbol::get_virtualtableshape](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|Kullanıcı tanımlı bir tür için sanal tablo türü simgesi arabiriminin alır.|  
|[Idiasymbol::get_virtualtableshapeıd](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|Simgenin sanal tablo şekli tanımlayıcısını alır.|  
|[Idiasymbol::get_volatiletype](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|Kullanıcı tanımlı veri türü volatile olup olmadığını belirten bir bayrak alır.|  
  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim, aşağıdaki yöntemlerden birini çağırarak alın:  
  
-   [Idiaenumsymbols::Item](../../debugger/debug-interface-access/idiaenumsymbols-item.md)  
  
-   [Idiaenumsymbols::Next](../../debugger/debug-interface-access/idiaenumsymbols-next.md)  
  
-   [Idiaenumsymbolsbyaddr::Next](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-next.md)  
  
-   [Idiaenumsymbolsbyaddr::prev](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-prev.md)  
  
-   [Idiaenumsymbolsbyaddr::symbolbyaddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyaddr.md)  
  
-   [Idiaenumsymbolsbyaddr::symbolbyrva](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyrva.md)  
  
-   [Idiaenumsymbolsbyaddr::symbolbyva](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)  
  
-   [Idiasession::findsymbolbyaddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [Idiasession::findsymbolbyrva](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [Idiasession::findsymbolbyrvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [Idiasession::findsymbolbyva](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [Idiasession::findsymbolbyvaex](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [Idiasession::findsymbolbytoken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [Idiasession::symbolbyıd](../../debugger/debug-interface-access/idiasession-symbolbyid.md)  
  
-   [Idiastackwalkhelper::symbolforva](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)  
  
-   [Idiasymbol::get_types](../../debugger/debug-interface-access/idiasymbol-get-types.md)  
  
## <a name="example"></a>Örnek  
 Bu örnek, belirli bir göreli sanal adresinde bir işlev için yerel değişkenler görüntülemek nasıl gösterir. Ayrıca, farklı türlerde simgeleri birbirleriyle nasıl ilişkili olduğunu gösterir.  
  
> [!NOTE]
>  `CDiaBSTR`kaydırılan bir sınıf bir `BSTR` ve örnek oluşturma kapsam dışına çıktığında dize boşaltma otomatik olarak yönetir.  
  
```C++  
void DumpLocalVars( DWORD rva, IDiaSession *pSession )  
{  
    CComPtr< IDiaSymbol > pBlock;  
    if ( FAILED( psession->findSymbolByRVA( rva, SymTagBlock, &pBlock ) ) )  
    {  
        Fatal( "Failed to find symbols by RVA" );  
    }  
    CComPtr< IDiaSymbol > pscope;  
    for ( ; pBlock != NULL; )  
    {  
        CComPtr< IDiaEnumSymbols > pEnum;  
        // local data search  
        if ( FAILED( pBlock->findChildren( SymTagNull, NULL, nsNone, &pEnum ) ) )  
        {  
            Fatal( "Local scope findChildren failed" );  
        }  
        CComPtr< IDiaSymbol > pSymbol;  
        DWORD tag;  
        DWORD celt;  
        while ( pEnum != NULL &&  
                SUCCEEDED( pEnum->Next( 1, &pSymbol, &celt ) ) &&  
                celt == 1)  
        {  
            pSymbol->get_symTag( &tag );  
            if ( tag == SymTagData )  
            {  
                CDiaBSTR name;  
                DWORD    kind;  
                pSymbol->get_name( &name );  
                pSymbol->get_dataKind( &kind );  
                if ( name != NULL )  
                    wprintf_s( L"\t%s (%s)\n", name, szDataKinds[ kind ] );  
            }  
            else if ( tag == SymTagAnnotation )  
            {  
                CComPtr< IDiaEnumSymbols > pValues;  
                // local data search  
                wprintf_s( L"\tAnnotation:\n" );  
                if ( FAILED( pSymbol->findChildren( SymTagNull, NULL, nsNone, &pValues ) ) )  
                    Fatal( "Annotation findChildren failed" );  
                pSymbol = NULL;  
                while ( pValues != NULL &&  
                        SUCCEEDED( pValues->Next( 1, &pSymbol, &celt ) ) &&  
                        celt == 1 )  
                {  
                    CComVariant value;  
                    if ( pSymbol->get_value( &value ) != S_OK )  
                        Fatal( "No value for annotation data." );  
                    wprintf_s( L"\t\t%ws\n", value.bstrVal );  
                    pSymbol = NULL;  
                }  
            }  
            pSymbol = NULL;  
        }  
        pBlock->get_symTag( &tag );   
        if ( tag == SymTagFunction )    // stop when at function scope  
            break;  
        // move to lexical parent  
        CComPtr< IDiaSymbol > pParent;  
        if ( SUCCEEDED( pBlock->get_lexicalParent( &pParent ) )  
            && pParent != NULL ) {  
            pBlock = pParent;  
        }  
        else  
        {  
            Fatal( "Finding lexical parent failed." );  
        }  
    };  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 `Header:`Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsymbolsbyaddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [Idiaenumsymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Simge türlerinin sınıf hiyerarşisi](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Simgeler ve simge etiketleri](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [Derlenecek dosya](../../debugger/debug-interface-access/compiland.md)