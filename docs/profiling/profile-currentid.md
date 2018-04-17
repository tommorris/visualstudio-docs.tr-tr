---
title: PROFILE_CURRENTID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- PROFILE_CURRENTID
ms.assetid: 55ccf665-a05e-48c3-adf7-7714c0a9aaef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e11076168dbcdbdd8cc617ab305f3f25550fcb1e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="profilecurrentid"></a>PROFILE_CURRENTID
PROFILE_CURRENTID NameProfile, StartProfile, StopProfile, SuspendProfile ve ResumeProfile işlevleri için bir çağrı iş parçacığı kimliği veya işlem kimliği için sahte belirteci döndürür. Geçerli iş parçacığının veya işlem yerine özellikle belirtilen bir çalışmaya işlevi neden kullanın.  
  
## <a name="example"></a>Örnek  
 PROFILE_CURRENTID VSPerf.h tanımlanır:  
  
```  
static const unsigned int PROFILE_CURRENTID = (unsigned int)-1;  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek PROFILE_CURRENTID gösterilmektedir. Bu örnek, geçerli iş parçacığının çağrıda tanımlayan bir parametre olarak PROFILE_CURRENTID kullanır. [StartProfile](../profiling/startprofile.md) işlevi.  
  
```  
void ExerciseProfileCurrentID()  
{  
    // Declare ProfileOperationResult enumeration   
    // to hold return value of a call to StartProfile.  
    PROFILE_COMMAND_STATUS profileResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    profileResult = StartProfile(  
        PROFILE_GLOBALLEVEL,  
        PROFILE_CURRENTID);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("StartProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, profileResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)   
 [NameProfile](../profiling/nameprofile.md)   
 [ResumeProfile](../profiling/resumeprofile.md)   
 [StartProfile](../profiling/startprofile.md)   
 [StopProfile](../profiling/stopprofile.md)   
 [SuspendProfile](../profiling/suspendprofile.md)