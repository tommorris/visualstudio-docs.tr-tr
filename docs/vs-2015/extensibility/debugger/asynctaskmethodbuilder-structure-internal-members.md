---
title: AsyncTaskMethodBuilder yapısı - dahili üyeler | Microsoft Docs
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
- debug engines, AsyncTaskMethodBuilder structure [.NET Framework]
- AsyncTaskMethodBuilder structure [.NET Framework debug engines]
ms.assetid: f32f5857-7ef8-45fd-8b5a-7f644eb98b11
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 14b17ebde347d2558c8d18277d5c49d066243034
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694430"
---
# <a name="asynctaskmethodbuilder-structure---internal-members"></a>AsyncTaskMethodBuilder Yapısı - Dahili Üyeler
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [AsyncTaskMethodBuilder yapısı - dahili üyeler](https://docs.microsoft.com/visualstudio/extensibility/debugger/asynctaskmethodbuilder-structure-internal-members).  
  
Bu konu, iç üyelerini açıklar <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> sınıfı. Bu sınıf hakkında genel bilgi için bkz: <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> başvuru konusu.  
  
 **Namespace:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **Bütünleştirilmiş kod:** mscorlib (mscorlib.dll içinde)  
  
 Bu iç üyeleri .NET Framework'ten erişemediği için aşağıdaki söz dizimini ortak Ara dil (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>Dahili üyeler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ObjectIdForDebugger özelliği](../../extensibility/debugger/asynctaskmethodbuilder-objectidfordebugger-property.md)|Hata ayıklayıcı bu oluşturucuya benzersiz olarak tanımlanabilmesi için kullanılabilecek bir nesneyi alır.|  
|[m_builder alan](../../extensibility/debugger/asynctaskmethodbuilder-m-builder-field.md)|Bu genel olmayan örnek için temsilciler Genel oluşturucu nesnesini temsil eder.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>   
 [.NET Framework için Paralel Uzantı Dahili Bileşenleri](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)

