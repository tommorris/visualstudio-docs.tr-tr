---
title: NameProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- NameProfile
- NameProfileA
ms.assetid: 1bb05441-c4ff-4323-9fef-f3924fba4430
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f0b717882e943a37857bbdadf3d318f94b4900dc
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="nameprofile"></a>NameProfile
`NameProfile` İşlevi belirtilen işlem veya iş parçacığı bir dize atar.  
  
 NameProfile API yalnızca profil oluşturma araçları kullanılabilir. NameProfile API örnekleme profili oluşturma için desteklenmiyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI NameProfile(  
                                   LPCTSTR pszName,   
                                   PROFILE_CONTROL_LEVEL Level,  
                                   unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszName`  
  
 Profil oluşturma öğesinin adı. Bir ad (NameProfileA dönüş NAME_ERROR_INVALID_NAME içinde kaynaklanan) geçersiz ise:  
  
-   NameProfileA geçirilen işaretçi NULL bir değerdir  
  
-   Bir sayı ile pszName dize verilerini başlatır  
  
-   Bir alanı pszName dize verilerini içerir  
  
-   PszName dize verilerini şu karakterlerden birini içeriyor:,. ' ~! @# $% ^ & * () = [] {}&#124;\\? / <>  
  
 `Level`  
  
 Hangi performans veri toplama uygulanabilir profili düzeyini gösterir. Aşağıdaki **PROFILE_CONTROL_LEVEL** değerleri, hangi performans veri toplama uygulanabilir üç düzeylerinden birini belirtmek için kullanılabilir:  
  
|Numaralandırıcı|Açıklama|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Genel düzeyi ayarı, tüm işlemler ve Çalıştır profil oluşturma iş parçacıkları etkiler.|  
|PROFILE_PROCESSLEVEL|İşlem düzeyi ayarı belirtilen işleminin bir parçası olan tüm iş parçacıklarının etkiler.|  
|PROFILE_THREADLEVEL|İş parçacığı düzeyi ayarı profil belirtilen iş parçacığı etkiler.|  
  
 `dwId`  
  
 Profil oluşturma düzeyi tanımlayıcısı. Sistem tarafından oluşturulan tanımlayıcısı iş parçacığı veya işlemi kullanın.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Kullanarak işlevi başarısını veya başarısızlığını gösterir **PROFILE_COMMAND_STATUS** numaralandırması. Dönüş değeri aşağıdakilerden biri olabilir:  
  
|Numaralandırıcı|Açıklama|  
|----------------|-----------------|  
|NAME_ERROR_ID_NOEXIST|Belirtilen profil öğesi yok.|  
|NAME_ERROR_INVALID_NAME|Adı geçersiz.|  
|NAME_ERROR_LEVEL_NOEXIST|Düzey belirtilen profili yok.|  
|NAME_ERROR_NO_SUPPORT|Belirtilen işlem desteklenmiyor.|  
|NAME_ERROR_OUTOFMEMORY|Olay kaydetmek bellek yoktu.|  
|NAME_ERROR_REDEFINITION|Bir ad zaten profili öğesine atandı. Bu işlevde ad yok sayılır.|  
|NAME_ERROR_TEXTTRUNCATED|Adı metin null karakteri de dahil olmak üzere 32 karakter sayısını aştı ve bu nedenle kesildi.|  
|NAME_OK|Ad başarıyla kaydedildi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca bir ad, her işlem veya iş parçacığı atanabilir. Profil oluşturma öğesi adlı sonra NameProfile yapılan sonraki çağrılar o öğeye ilişkin göz ardı edilir.  
  
 Farklı iş parçacıkları veya işlemler için aynı adı belirtilmezse, rapora tüm öğeleri aynı ada sahip düzeyde verilerden dahil edilir.  
  
 Bir işlem veya iş parçacığı geçerli dışında belirtirseniz, bu başlatıldı ve buna adını önce çalışmaya başladığı emin emin olmanız gerekir. Aksi takdirde NameProfile yöntemi başarısız olur.  
  
> [!IMPORTANT]
>  İş parçacığı önce CreateProcess() ve CreateThread() API işlevleri döndürebilir veya işlemi başlatıldı.  
  
## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>İşlev bilgisi  
  
|||  
|-|-|  
|**Üstbilgi**|VSPerf.h içerir|  
|**Kitaplığı**|VSPerf.lib kullanın|  
|**Unicode**|Olarak uygulanan `NameProfileW` (Unicode) ve `NameProfileA` (ANSI).|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod NameProfile işlev çağrısı gösterir. Örnek Win32 dize makroların kullanılması ve kod çağrıları ANSI işlevi etkin olup olmadığını belirlemek ANSI derleyici ayarları varsayar.  
  
```  
void ExerciseNameProfile()  
{  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Create and initialize variables to pass to   
    // ExerciseNameProfile.  The value of this   
    // parameter is based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variable is assigned an arbitrary value.  
    TCHAR * profileName = TEXT("ExerciseNameProfile");  
  
    // Declare enumeration to hold result of call to   
    // ExerciseNameProfle.  
    PROFILE_COMMAND_STATUS nameResult;  
  
    nameResult =  NameProfile(  
        profileName,  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("NameProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, nameResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)