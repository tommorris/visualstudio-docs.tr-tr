---
title: Idiaframedata | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData interface
ms.assetid: 2f1b4986-341b-4641-89a4-226e261e9d93
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19581f25a9f75bd1a791c9f2f7b23998218e5f27
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idiaframedata"></a>IDiaFrameData
Yığın çerçevesi ayrıntılarını gösterir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaFrameData : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaFrameData`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Idiaframedata::get_addresssection](../../debugger/debug-interface-access/idiaframedata-get-addresssection.md)|Çerçeve kod adresi bölüm parçası alır.|  
|[Idiaframedata::get_addressoffset](../../debugger/debug-interface-access/idiaframedata-get-addressoffset.md)|Çerçeve kod adresi uzaklık parçası alır.|  
|[Idiaframedata::get_relativevirtualaddress](../../debugger/debug-interface-access/idiaframedata-get-relativevirtualaddress.md)|Görüntü göreli sanal adres (RAV) çerçevesi için kod alır.|  
|[Idiaframedata::get_virtualaddress](../../debugger/debug-interface-access/idiaframedata-get-virtualaddress.md)|Çerçeve kodunu sanal adres (VA) alır.|  
|[Idiaframedata::get_lengthblock](../../debugger/debug-interface-access/idiaframedata-get-lengthblock.md)|Çerçeve tarafından açıklanan kod bloğunun bayt cinsinden uzunluğu alır.|  
|[Idiaframedata::get_lengthlocals](../../debugger/debug-interface-access/idiaframedata-get-lengthlocals.md)|Yerel değişkenler yığına bayt sayısını alır.|  
|[Idiaframedata::get_lengthparams](../../debugger/debug-interface-access/idiaframedata-get-lengthparams.md)|Yığına parametrelerinin bayt sayısını alır.|  
|[Idiaframedata::get_maxstack](../../debugger/debug-interface-access/idiaframedata-get-maxstack.md)|Yığın çerçevesi içinde gönderilen bayt sayısını alır.|  
|[Idiaframedata::get_lengthprolog](../../debugger/debug-interface-access/idiaframedata-get-lengthprolog.md)|Başlangıç kod bloğundaki bayt sayısını alır.|  
|[Idiaframedata::get_lengthsavedregisters](../../debugger/debug-interface-access/idiaframedata-get-lengthsavedregisters.md)|Kaydedilmiş Yazmaçlar yığına bayt sayısını alır.|  
|[Idiaframedata::get_program](../../debugger/debug-interface-access/idiaframedata-get-program.md)|Geçerli işlevi çağırmadan önce ayarlayın kayıt hesaplamak için kullanılan program dizesini alır.|  
|[Idiaframedata::get_systemexceptionhandling](../../debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling.md)|Alır, bu sistem özel durum işleme belirten bir bayrak etkili olur.|  
|[Idiaframedata::get_cplusplusexceptionhandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)|Alır, C++ özel durum işleme belirten bir bayrak etkili olur.|  
|[Idiaframedata::get_functionstart](../../debugger/debug-interface-access/idiaframedata-get-functionstart.md)|Blok işlevi giriş noktasını içerse belirten bir bayrak alır.|  
|[Idiaframedata::get_allocatesbasepointer](../../debugger/debug-interface-access/idiaframedata-get-allocatesbasepointer.md)|Bu adres aralığındaki kod için temel işaretçi ayrılır belirten bir bayrak alır. Bu yöntem kullanım dışıdır.|  
|[Idiaframedata::get_type](../../debugger/debug-interface-access/idiaframedata-get-type.md)|Derleyici özgü çerçeve türünü alır.|  
|[Idiaframedata::get_functionparent](../../debugger/debug-interface-access/idiaframedata-get-functionparent.md)|Alır işlevi kapsayan için veri arabirimi çerçevesi.|  
|[Idiaframedata::Execute](../../debugger/debug-interface-access/idiaframedata-execute.md)|Yığın geriye doğru izleme gerçekleştirir ve yığın ilerlemesi çerçeve arabiriminde yazmaçlar geçerli durumunu döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıntılar için bir çerçeve kullanılabilir adres ve blok uzunluğu ile belirtilen adres aralığı içinde yürütme noktaları içindir.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırarak elde [Idiaenumframedata::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md) veya [Idiaenumframedata::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md) yöntemleri. Bkz: [Idiaenumframedata](../../debugger/debug-interface-access/idiaenumframedata.md) Ayrıntılar için arabirim.  
  
## <a name="example"></a>Örnek  
 Bu örnek özelliklerini yazdırır bir `IDiaFrameData` nesnesi. Bkz: [Idiaenumframedata](../../debugger/debug-interface-access/idiaenumframedata.md) arabirimi bir örnek için nasıl `IDiaFrameData` arabirimi elde edilir.  
  
```C++  
void PrintFrameData(IDiaFrameData* pFrameData){  
    DWORD dwSect;  
    DWORD dwOffset;  
    DWORD cbBlock;  
    DWORD cbLocals; // Number of bytes reserved for the function locals  
    DWORD cbParams; // Number of bytes reserved for the function arguments  
    DWORD cbMaxStack;  
    DWORD cbProlog;  
    DWORD cbSavedRegs;  
    BOOL  bSEH;  
    BOOL  bEH;  
    BOOL  bStart;  
    BSTR  wszProgram;  
  
    if(pFrameData->get_addressSection(&dwSect) == S_OK &&   
       pFrameData->get_addressOffset(&dwOffset) == S_OK &&  
       pFrameData->get_lengthBlock(&cbBlock) == S_OK &&  
       pFrameData->get_lengthLocals(&cbLocals) == S_OK &&  
       pFrameData->get_lengthParams(&cbParams) == S_OK &&  
       pFrameData->get_maxStack(&cbMaxStack) == S_OK &&  
       pFrameData->get_lengthProlog(&cbProlog) == S_OK &&  
       pFrameData->get_lengthSavedRegisters(&cbSavedRegs) == S_OK &&  
       pFrameData->get_systemExceptionHandling(&bSEH) == S_OK &&  
       pFrameData->get_cplusplusExceptionHandling(&bEH) == S_OK &&  
       pFrameData->get_functionStart(&bStart) == S_OK )  
    {  
        wprintf(L"Frame address  : %04X:%08X\n", dwSect, dwOffset);  
        wprintf(L"Block size     : 0x%8X\n", cbBlock);  
        wprintf(L"Locals size    : 0x%8X\n", cbLocals);  
        wprintf(L"Parms size     : 0x%8X\n", cbParams);  
        wprintf(L"Max stack used : 0x%8X\n", cbMaxStack);  
        wprintf(L"Prolog size    : 0x%8X\n", cbProlog);  
        wprintf(L"Saved regs size: 0x%8X\n", cbSavedRegs);  
        wprintf(L"System Exception Handling: %c\n", bSEH ? L'Y' : L'N');  
        wprintf(L"C++ Exception Handling   : %c\n", bEH ? L'Y' : L'N');  
        wprintf(L"Function starts in block : %c\n", bStart ? L'Y' : L'N');  
  
        if (pFrameData->get_program(&wszProgram) == S_OK)  
        {  
            wprintf(L"Program used for register set: %s\n", wszProgram);  
            SysFreeString(wszProgram);  
        }  
        else  
        {  
            wprintf(L"\n");  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Dia2.h  
  
 Kitaplığı: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumframedata](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [Idiaenumframedata::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)   
 [Idiaenumframedata::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md)