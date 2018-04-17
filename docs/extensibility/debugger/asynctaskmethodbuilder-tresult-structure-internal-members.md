---
title: AsyncTaskMethodBuilder&lt;TResult&gt; yapısı - iç üyeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- AsyncTaskMethodBuilder<TResult> structure [.NET Framework debug engines]
- debug engines, AsyncTaskMethodBuilder<TResult> structure [.NET Framework]
ms.assetid: 17ebc340-8170-4aff-bf54-dc4548c83632
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4b5c9c3b0ff653384ff7a14487899d8205975cd5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="asynctaskmethodbuilderlttresultgt-structure---internal-members"></a>AsyncTaskMethodBuilder&lt;TResult&gt; yapısı - iç üyeleri
Bu konuda iç üyeleri açıklanmaktadır <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> sınıfı. Bu sınıf hakkında genel bilgi için bkz: <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> başvuru konusu.  
  
 **Namespace:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
 **Derleme:** mscorlib (içinde mscorlib.dll)  
  
 İç bu üye .NET Framework'teki erişemediği için aşağıdaki söz dizimini ortak Ara dile (CIL) sağlanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<TResult>  
       extends System.ValueType  
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder  
```  
  
## <a name="internal-members"></a>İç üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ObjectIdForDebugger özelliği](../../extensibility/debugger/asynctaskmethodbuilder-tresult-objectidfordebugger-property.md)|Bu oluşturucu hata ayıklayıcı için benzersiz şekilde tanımlamak için kullanılabilir bir nesneyi alır.|  
|[m_task alan](../../extensibility/debugger/asynctaskmethodbuilder-tresult-m-task-field.md)|Gevşek başlatılmış görev yerleşik temsil eder.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601>   
 [.NET Framework için Paralel Uzantı Dahili Bileşenleri](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)