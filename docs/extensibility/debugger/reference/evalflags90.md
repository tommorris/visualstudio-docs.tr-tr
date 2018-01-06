---
title: EVALFLAGS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 80f281e65d4dd7b2df24233552bdc46d4b29bebe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="evalflags90"></a>EVALFLAGS90
İfade değerlendirme denetim bayrakları geçerli değerlerini sıralar. Bu numaralandırma genişletir [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) numaralandırması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 EVAL90_RETURNVALUE  
 Dönüş değeri varsa değerlendirilmesi belirtir.  
  
 EVAL90_NOSIDEEFFECTS  
 Yan etkileri değil verileceğini belirtir.  
  
 EVAL90_ALLOWBPS  
 Durdurma kesme noktaları üzerinde belirtir.  
  
 EVAL90_ALLOWERRORREPORT  
 Ana bilgisayara izin verilmesi için Raporlama hata belirtir. Internet Explorer'da komut ifade değerlendirmesi için kullanılır.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 İşlev çağırma yerine adresleri olarak değerlendirilecek işlevler zorlar.  
  
 EVAL90_NOFUNCEVAL  
 İşlev değerlendirilen gelen engeller. Örneğin, göz önünde bulundurun `int` ifadesinde belirteci `myExpression(int) + 10`. Bu işlev doğru adresi olarak ancak olmayan bir değer olarak değerlendirilebilir.  
  
 EVAL90_NOEVENTS  
 İfade değerlendirme sırasında meydana gelen olayları oturum hata ayıklama Yöneticisi'ni (SDM) ya da IDE gönderilmemelidir belirtmek için bayraklayın.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Tasarım zamanı ifade değerlendirmesi sağlar.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Açık değişken oluşturma sağlar.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Hemen gerçekleşmesi için değerlendirme zorlar. Bu, kullanıcı isteği gibi bir isteği hizmet verirken yararlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 Başlık: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit Listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)