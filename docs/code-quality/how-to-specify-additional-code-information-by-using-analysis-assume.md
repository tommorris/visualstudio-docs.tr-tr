---
title: 'Nasıl yapılır: __analysis_assume kullanarak ek kod bilgileri belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- __analysis_assume
helpviewer_keywords:
- __analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
author: mikeblome
ms.author: mblome
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f039298e56e33bc80ae1a9f7384a40914c532ff8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>Nasıl yapılır: __analysis_assume Kullanarak Ek Kod Bilgileri Belirtme
Çözümleme işleminin yardımcı olmak ve Uyarıları azaltmak C/C++ kodu için kod analizi aracı için ipuçları sağlayabilir. Ek bilgi sağlamak için aşağıdaki işlev kullanın:  
  
 `__analysis_assume(`  `expr`  `)`  
  
 `expr` -true değerlendirileceği varsayılır herhangi bir ifade.  
  
 Kod çözümleme aracı ifade tarafından temsil edilen koşul işlevi burada görünür ve ifade, örneğin, bir değişkene atama tarafından değiştirilinceye kadar doğrudur noktasında doğru olduğunu varsayar.  
  
> [!NOTE]
>  `__analysis_assume` kodu iyileştirme etkilemez. Kod çözümleme aracı dışında `__analysis_assume` no-op tanımlanır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod `__analysis_assume` kod çözümleme uyarısı düzeltmek için [C6388](../code-quality/c6388.md):  
  
```  
#include<windows.h>  
#include<codeanalysis\sourceannotations.h>  
  
using namespace vc_attributes;  
  
// calls free and sets ch to null  
void FreeAndNull(char* ch);  
  
//requires pc to be null  
void f([Pre(Null=Yes)] char* pc);  
  
void test( )  
{  
  char *pc = (char*)malloc(5);  
  FreeAndNull(pc);  
  __analysis_assume(pc == NULL);   
  f(pc);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__assume](/cpp/intrinsics/assume)