---
title: CommentMarkProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- CommentMarkProfile
- CommentMarkProfileA
ms.assetid: 33ccff45-c33a-4672-b41f-5b317b848cd1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aaae7a6ce1185426f23a8182ddcdf0c969f39a4b
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691049"
---
# <a name="commentmarkprofile"></a>CommentMarkProfile
`CommentMarkProfile` İşlevi ekler sayısal işaret ve bir metin dizesi içinde. *Vsp* dosya. Açıklama ve işareti için içeren iş parçacığı için profil oluşturma `CommentMarkProfile` işlevi açık olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
PROFILE_COMMAND_STATUS PROFILERAPI CommentMarkProfile(  
                                   long lMarker,   
                                   LPCTSTR szComment);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lMarker`  
  
 Eklenecek sayısal işaretçisi. İşaretin 0 (sıfır) değerine eşit veya daha büyük olmalıdır.  
  
 `szComment`  
  
 İşaretçi eklemek için metin dizesi. Dize NULL Sonlandırıcı dahil olmak üzere 256 karakterden kısa olmalıdır.  
  
## <a name="property-valuereturn-value"></a>Özellik değeri/dönüş değeri  
 Kullanarak işlevi başarısını veya başarısızlığını gösterir **PROFILE_COMMAND_STATUS** numaralandırması. Dönüş değeri aşağıdakilerden biri olabilir:  
  
|Numaralandırıcı|Açıklama|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametre, küçük veya 0 değerine eşit değil. Bu değerler ayrılmıştır. Açıklama ve işareti kaydedilmedi.|  
|MARK_ERROR_MODE_NEVER|Hiçbir zaman işlevi çağrıldığında profil oluşturma modu ayarlandı. Açıklama ve işareti kaydedilmedi.|  
|MARK_ERROR_MODE_OFF|İşlevi çağrıldığında profil oluşturma modu OFF olarak ayarlandı. Açıklama ve işareti kaydedilmedi.|  
|MARK_ERROR_NO_SUPPORT|Bu bağlamda işareti desteği yok. Açıklama ve işareti kaydedilmedi.|  
|MARK_ERROR_OUTOFMEMORY|Olay kaydetmek bellek yoktu. Açıklama ve işareti kaydedilmedi.|  
|MARK_TEXTTOOLONG|Dize en fazla 256 karakter aşıyor. Açıklama dizesi kesilir ve yorum ve işareti kaydedilir.|  
|MARK_OK|MARK_OK başarılı olduğunu belirtmek için döndürülür.|  
  
## <a name="remarks"></a>Açıklamalar  
 İşaretleri ve yorumları Vsınstr işareti komutuyla veya işlevler (CommentMarkAtProfile, CommentMarkProfile veya MarkProfile) ile eklendiğinde işareti profili işlevi içeren iş parçacığı için profil oluşturma durumu olmalıdır.  
  
 Profil işaretleri kapsamda geneldir. Örneğin, bir iş parçacığında eklenen bir profili işareti başlangıç ya da herhangi bir iş parçacığı veri segmentinin sonunu işaretlemek için kullanılabilir. *vsp* dosya.  
  
> [!IMPORTANT]
>  CommentMarkProfile yöntemi yalnızca araçları ile kullanılabilir.  
  
## <a name="net-framework-equivalent"></a>.NET framework eşdeğeri  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>İşlev bilgisi  
  
|||  
|-|-|  
|**Üstbilgi**|VSPerf.h içerir|  
|**Kitaplığı**|VSPerf.lib kullanın|  
|**Unicode**|Olarak uygulanan `CommentMarkProfileW` (Unicode) ve `CommentMarkProfileA` (ANSI).|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod CommentMarkProfile işlev çağrısı gösterir. Win32 dize makroları ve kod çağırır olup olmadığını belirlemek için Unicode derleyici ayarları kullanımını örnek varsayar [!INCLUDE[vcpransi](../profiling/includes/vcpransi_md.md)] işlev çağrısı.  
  
```cpp  
void ExerciseCommentMarkProfile()  
{  
    // Declare and initalize variables to pass to   
    // CommentMarkProfile.  The values of these   
    // parameters are assigned based on the needs   
    // of the code; and for the sake of simplicity  
    // in this example, the variables are assigned  
    // arbitrary values.  
    long markId = 01;  
    TCHAR * markText = TEXT("Exercising CommentMarkProfile...");  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    // Declare MarkOperationResult Enumerator.    
    // Holds return value from call to CommentMarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    markResult = CommentMarkProfile(  
        markId,  
        markText);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("CommentMarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)