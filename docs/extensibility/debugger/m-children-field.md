---
title: m_children alan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e71bc592e77daac877b571b14acd2d62a8657b9f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109983"
---
# <a name="mchildren-field"></a>m_children alan
Bu görev ile kayıtlı alt görevler listesi.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
 İç bu üye .NET Framework'teki erişemediği için aşağıdaki söz dizimini ortak Ara dile (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Görev yürütülürken görevi yürüten iş parçacığı bu diziye erişim.  
  
 Görev tamamlandı, bunlar herhangi bir şey için eklemeyin veya kaldırmadan bir şey sürece başka bir iş parçacığı bu alan erişebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ContingentProperties sınıfı](../../extensibility/debugger/contingentproperties-class-internal-members.md)