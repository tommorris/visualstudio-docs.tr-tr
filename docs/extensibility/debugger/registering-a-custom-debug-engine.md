---
title: "Hata ayıklama altyapısı özel bir kaydetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, registering
ms.assetid: 9984cd3d-d34f-4662-9ace-31766499abf5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 50903d9b45828725da03c0fcb0db0f08d7f884eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="registering-a-custom-debug-engine"></a>Bir özel hata ayıklama altyapısı kaydetme
Hata ayıklama altyapısı gerekir kendisini COM kurallarına uygun bir sınıf fabrikası kaydetmek yanı sıra Visual Studio kayıt defteri alt anahtarı Visual Studio ile kaydedin.  
  
> [!NOTE]
>  Hata ayıklama altyapısı kaydetmek nasıl bir örnek bir parçası olarak yerleşik TextInterpreter örnek bulunabilir [öğretici: bir hata ayıklama altyapısını kullanarak ATL COM derleme](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24).  
  
## <a name="dll-server-process"></a>DLL sunucu işlemi  
 Genellikle, bir hata ayıklama altyapısı kendi DLL'de COM sunucusu olarak uygulanır. Bu hata ayıklama altyapısı Visual Studio erişebilmesi için önce COM ile kendi üreteci CLSID kaydettirmelisiniz anlamına gelir. Hata ayıklama altyapısı kendisi ile Visual Studio kendisini herhangi bir özellik (Aksi ölçümleri olarak bilinir) oluşturmak için hata ayıklama kaydetmeniz gerekir sonra altyapısını destekler. Hata ayıklama altyapısı için Visual Studio kayıt defteri alt anahtarına yazılan ölçümleri seçiminde hata ayıklama motoru destekler özelliklerine bağlıdır.  
  
 [Hata ayıklama için SDK Yardımcıları](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md) yalnızca hata ayıklama altyapısı; kaydetmek gerekli kayıt defteri konumları açıklar ayrıca çok sayıda kullanışlı işlevler ve olun C++ geliştiricileri için bildirimleri içeren dbgmetric.lib kitaplık açıklanır daha kolay kayıt defterini düzenleme.  
  
### <a name="example"></a>Örnek  
 Nasıl kullanılacağını gösteren bir örnek (TextInterpreter örnekten) aşağıdadır `SetMetric` (dbgmetric.lib) ile Visual Studio hata ayıklama altyapısı kaydetmek için işlev. Geçirilen ölçümleri de dbgmetric.lib içinde tanımlanmıştır.  
  
> [!NOTE]
>  TextInterpreter temel hata ayıklama altyapısıdır; uygulamaz — ve bu nedenle kaydettirilemedi — diğer özellikleri. Daha eksiksiz bir hata ayıklama altyapısı tam listesini olurdu `SetMetric` çağrıları veya kendi eşdeğer, her bir özelliğin hata ayıklama altyapısı için bir tane destekler.  
  
```  
// Define base registry subkey to Visual Studio.  
static const WCHAR strRegistrationRoot[] = L"Software\\Microsoft\\VisualStudio\\8.0";  
  
HRESULT CTextInterpreterModule::RegisterServer(BOOL bRegTypeLib, const CLSID * pCLSID)  
{  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricName, L"Text File", false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricCLSID, CLSID_Engine, false, strRegistrationRoot);  
    SetMetric(metrictypeEngine, __uuidof(Engine), metricProgramProvider, CLSID_MsProgramProvider, false, strRegistrationRoot);  
  
    return base::RegisterServer(bRegTypeLib, pCLSID);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir özel hata ayıklama altyapısı oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)   
 [Hata ayıklama için SDK Yardımcıları](../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)   
 [Öğretici: ATL COM kullanarak hata ayıklama altyapısı oluşturma](http://msdn.microsoft.com/en-us/9097b71e-1fe7-48f7-bc00-009e25940c24)