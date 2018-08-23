---
title: m_children alanı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 0b72bd9563817c67e819485528e339410b9f87ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688050"
---
# <a name="mchildren-field"></a>m_children Alanı
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [m_children alanı](https://docs.microsoft.com/visualstudio/extensibility/debugger/m-children-field).  
  
Bu göreve kaydedilmiş alt görevlerin listesi.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
 .NET Framework'den bu iç üye erişemediği için aşağıdaki söz dizimini ortak Ara dil (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Görev yürütülürken, görevi yürüten iş parçacığı bu dizinin erişmelidir.  
  
 Görev tamamlandıysa, bunlar olmayan herhangi bir şey eklemek veya herhangi bir şey kaldırın sürece diğer iş parçacıkları Bu alan erişebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ContingentProperties sınıfı](../../extensibility/debugger/contingentproperties-class-internal-members.md)

