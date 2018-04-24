---
title: MarkProfile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- MarkProfile
ms.assetid: 54dac8c8-c8ee-4023-af27-b25466e3a6ec
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a5e4f93446c49120afb43202f457af39439ca1bc
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="markprofile"></a>MarkProfile
`MarkProfile` Yöntemi .vsp dosyasında bir profil işareti ekler. İş parçacığı içeren için profil oluşturma `MarkProfile` işlevi eklenecek işareti açık olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI MarkProfile( long lMarker );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lMarker`  
  
 Eklenecek işaretçisi. İşaretin 0 (sıfır) değerine eşit veya daha büyük olmalıdır.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
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
 İşareti değer MarkProfile işlevi içeren iş parçacığı profili, kodu her çalıştığında .vsp dosyasına eklenir. Birden çok kez MarkProfile çağırabilirsiniz.  
  
 Profil işaretleri kapsamda geneldir. Örneğin, bir iş parçacığında eklenen bir profili işareti başlangıç ya da herhangi bir iş parçacığı .vsp dosyasındaki veri segmentinin sonunu işaretlemek için kullanılabilir.  
  
 İşaretleri ve yorumları API işlevleri (CommentMarkAtProfile, CommentMarkProfile veya MarkProfile) veya işareti komutu ile yerleştirildiğinde işareti profili işlevi içeren iş parçacığı için profil oluşturma durumu olmalıdır.  
  
> [!IMPORTANT]
>  MarkProfile yöntemi araçları yalnızca profil oluşturma ile kullanılması gerekir.  
  
## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>İşlev bilgisi  
 Başlık: VSPerf.h içinde bildirilen  
  
 İçeri aktarma kitaplığı: VSPerf.lib  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod MarkProfile işlev gösterir.  
  
```  
void ExerciseMarkProfile()  
{  
    // Declare and initialize variables to pass to   
    // MarkProfile.  The values of these parameters   
    // are assigned based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variables are assigned arbitrary values.  
    int markId = 03;  
  
    // Declare enumeration to hold return value of   
    // call to MarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    markResult = MarkProfile(markId);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("MarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio profil oluşturucu API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)