---
title: ResumeProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- ResumeProfile
ms.assetid: 876f145b-ec07-4240-ade6-4f6e44baadce
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4f1db214a40411b8c03e46463fda9ed8b235ab03
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="resumeprofile"></a>ResumeProfile
`ResumeProfile` Yöntemi azaltır askıya alma/sürdürmeden sayaç için belirtilen profil düzeyi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI ResumeProfile(  
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
 Aşağıdaki örnek ResumeProfile işlevi gösterilmektedir. Örnek SuspendProfile yöntemine bir çağrı aynı iş parçacığı veya tarafından tanımlanan işlemi için yapılan varsayar [PROFILE_CURRENTID](../profiling/profile-currentid.md).  
  
```  
void ExerciseResumeProfile()  
{  
    // The initial value of the Suspend/Resume counter is 0.   
    // Each call to SuspendProfile adds 1 to the Suspend/Resume   
    // count; each call to ResumeProfile subtracts 1.   
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare enumeration to hold result of call to ResumeProfile  
    PROFILE_COMMAND_STATUS profileResult;  
  
    profileResult = ResumeProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("ResumeProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)