---
title: Idiasession::findlinesbylinenum | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByLinenum method
ms.assetid: 76d5622d-9a91-4c2a-a98f-263af5d1daef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5d0cfcda8a48278abd8420e2c23954f5f7a22203
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2018
ms.locfileid: "31464631"
---
# <a name="idiasessionfindlinesbylinenum"></a>IDiaSession::findLinesByLinenum
İçinde ya da yakın bir kaynak dosyasında belirtilen satır numarası arasındadır derlenecek satır numaralarını belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```C++  
HRESULT findLinesByLinenum (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `compiland`  
 [in] Bir [Idiasymbol](../../debugger/debug-interface-access/idiasymbol.md) için satır numaralarını aranacağı derlenecek temsil eden nesne. Bu parametre olamaz `NULL`.  
  
 `file`  
 [in] Bir [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md) içinde arama yapmak istediğiniz kaynak dosyasını temsil eden nesne. Bu parametre olamaz `NULL`.  
  
 `linenum`  
 [in] Tabanlı satır numarasını belirtir.  
  
> [!NOTE]
>  Tüm satırları belirtmek için sıfır kullanamazsınız (kullanmak [Idiasession::findlines](../../debugger/debug-interface-access/idiasession-findlines.md) tüm satırları bulmak için yöntem).  
  
 `column`  
 [in] Sütun sayısını belirtir. Tüm sütunları belirtmek için sıfır kullanın. Bir satır halinde bayt uzaklığı bir sütundur.  
  
 `ppResult`  
 [out] Döndürür bir [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) satır numaralarını listesini içeren objta alınır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, kaynak dosyasını açın, bu dosyanın katkıda derlenecek dosyalar numaralandırır ve her derlenecek başladığı kaynak dosyasında satır numaralarını bulun gösterilmektedir.  
  
```C++  
void ShowLinesInCompilands(IDiaSession *pSession, LPCOLESTR filename)  
{  
    IDiaEnumSourceFiles* pEnum;  
    IDiaSourceFile*      pFile;  
    DWORD                celt;  
  
    pSession->findFile ( NULL, filename, nsFNameExt, &pEnum );  
    while ( pEnum->Next ( 1, &pFile, &celt ) == S_OK ) // for each file  
    {  
        IDiaEnumSymbols* pEnumCompilands;  
        IDiaSymbol* pCompiland;  
  
        pFile->get_compilands ( &pEnumCompilands );  
        // for each compiland  
        while ( pEnumCompilands->Next ( 1, &pCompiland, &celt ) == S_OK )  
        {  
            IDiaEnumLineNumbers* pEnum;  
            // Find first compiland closest to line 1 of the file.  
            if (pSession->findLinesByLinenum( pCompiland, pFile, 1, 0, &pEnum ) == S_OK)  
            {  
                IDiaLineNumber *pLineNumber;  
                DWORD lineCount;  
                while ( pEnum->Next(1,&pLineNumber,&lineCount) == S_OK)  
                {  
                     DWORD lineNum;  
                     if (pLineNumber->get_line(&lineNum) == S_OK)  
                     {  
                          printf("compiland starts in source at line number = %lu\n",lineNum);  
                     }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idiaenumlinenumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiasession](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::findlinesbyaddr](../../debugger/debug-interface-access/idiasession-findlinesbyaddr.md)   
 [Idiasourcefile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)