---
title: SuspendProfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: SuspendProfile
ms.assetid: 7c8de6e6-bb88-4353-92c3-ce7290310d61
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6b91542039544e085b6599923e9cc8dcb08d6c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="suspendprofile"></a>SuspendProfile
`SuspendProfile` Yöntemi belirtilen profil düzeyi için askıya alma/sürdürmeden sayacı artırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI SuspendProfile(  
                       PROFILE_CONTROL_LEVEL Level,   
                       unsigned int dwId);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `Level`  
  
 Hangi performans veri toplama uygulanabilir profili düzeyini gösterir. Aşağıdaki **PROFILE_CONTROL_LEVEL** numaralandırmalar, hangi performans veri toplama uygulanabilir üç düzeylerinden birini belirtmek için kullanılabilir:  
  
|Numaralandırıcı|Açıklama|  
|----------------|-----------------|  
|PROFILE_GLOBALLEVEL|Genel düzeyi ayarı, tüm işlemler ve Çalıştır profil oluşturma iş parçacıkları etkiler.|  
|PROFILE_PROCESSLEVEL|İşlem düzeyi ayarı belirtilen işleminin bir parçası olan tüm iş parçacıklarının etkiler.|  
|PROFILE_THREADLEVEL|İş parçacığı düzeyi ayarı profil belirtilen iş parçacığı etkiler.|  
  
 `dwId`  
  
 Sistem tarafından oluşturulan işlem veya iş parçacığı tanımlayıcısı.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 Kullanarak işlevi başarısını veya başarısızlığını gösterir **PROFILE_COMMAND_STATUS** numaralandırması. Dönüş değeri aşağıdakilerden biri olabilir:  
  
|Numaralandırıcı|Açıklama|  
|----------------|-----------------|  
|PROFILE_ERROR_ID_NOEXIST|Profil oluşturma öğesi kimliği yok.|  
|PROFILE_ERROR_LEVEL_NOEXIST|Düzey belirtilen profil yok.|  
|PROFILE_ERROR_MODE_NEVER|Hiçbir zaman işlevi çağrıldığında profil oluşturma modu ayarlandı.|  
|PROFILE_ERROR_NOT_YET_IMPLEMENTED|Profil oluşturma işlev çağrısı, profil düzeyinde veya arama ve düzeyi birleşimi henüz uygulanmadı.|  
|PROFILE_OK|Çağrı başarılı oldu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Askıya alma/sürdürmeden sayacın başlangıç değeri 0'dır. SuspendProfile her çağrı için askıya alma/sürdürmeden sayısı 1 ekler; her çağrı ResumeProfile 1 çıkarır.  
  
 Askıya alma/sürdürmeden sayısı 0'dan büyük olduğunda düzeyi için askıya alma/sürdürme durumu Kapalı'dır. Sayısı 0 değerine eşit veya daha küçük olduğunda, askıya alma/sürdürmeden açık durumda.  
  
 Başlat/Durdur durumu ve askıya alma/sürdürme durumu hem de açık olduğunda, profil düzeyi için açık bir durumda. İş parçacığı olması için genel işlem profili ve iş parçacığı düzeyi durumları için iş parçacığı tüm olmalıdır açık.  
  
## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>İşlev bilgisi  
 Başlık: VSPerf.h içinde bildirilen  
  
 İçeri aktarma kitaplığı: VSPerf.lib  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek SuspendProfile yöntemi gösterilmektedir. Bu örnekte StartProfile önceki bir çağrı tarafından tanımlanan iş parçacığı ve işlem için yaptığınız varsayılmaktadır. [PROFILE_CURRENTID](../profiling/profile-currentid.md).  
  
```  
void ExerciseSuspendProfile()  
{  
    // The initial value of the Suspend/Resume counter is 0.  
    // Each call to SuspendProfile adds 1 to the  
    // Suspend/Resume count; each call  
    // to ResumeProfile subtracts 1.  
  
    // Variables used to print output  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold result of call  
    // to SuspendProfile  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = SuspendProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("SuspendProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)