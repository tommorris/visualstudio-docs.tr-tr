---
title: 'CA1600: boş işlem önceliğini kullanmayın | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- DoNotUseIdleProcessPriority
- CA1600
helpviewer_keywords:
- CA1600
- DoNotUseIdleProcessPriority
ms.assetid: 9b0d073b-78b6-41be-8ef3-14692a735283
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93255488efa84f553d61aaedb0474c69a4bbb8d0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1600-do-not-use-idle-process-priority"></a>CA1600: Boş işlem önceliğini kullanmayın
|||  
|-|-|  
|TypeName|DoNotUseIdleProcessPriority|  
|CheckId|CA1600|  
|Kategori|Microsoft.Mobility|  
|Yeni Değişiklik|Yeni|  
  
## <a name="cause"></a>Sebep  
 İşlemler ayarlamak bu kural oluşur `ProcessPriorityClass.Idle`.  
  
## <a name="rule-description"></a>Kural Tanımı  
 İşlem önceliğini Boşta olarak ayarlamayın. Bulunan işlemlerin `System.Diagnostics.ProcessPriorityClass.Idle` Aksi takdirde boş olacaktır ve bu nedenle bekleme engeller CPU kaplar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Ayarlama işlemleri `ProcessPriorityClass.BelowNormal`.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kural, yalnızca boş işlem önceliğini gereklidir ve mobility konuları güvenle yoksayılabilir gizlenen.