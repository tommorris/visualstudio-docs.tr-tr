---
title: .NET Framework için uzantı iç paralel | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, internals [.NET Framework]
ms.assetid: 93e07cfa-91fa-464c-b866-8bf5570411df
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4936efe50023ed1e193d0c2ec0d9c3423ac5cc64
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31100617"
---
# <a name="parallel-extension-internals-for-the-net-framework"></a>.NET Framework için paralel uzantısı dahili bileşenleri
İç türleri, yöntemleri, bu bölümde açıklanmıştır ve yardımcı sınıfları alanlarının paralel uzantıları .NET Framework için özel bir hata ayıklayıcısı uygulayın.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Task sınıfı](../../extensibility/debugger/task-class-internal-members.md)  
 İç veri üyeleri açıklar <xref:System.Threading.Tasks.Task?displayProperty=fullName> sınıfı.  
  
 [TaskScheduler sınıfı](../../extensibility/debugger/taskscheduler-class-internal-members.md)  
 İç veri üyeleri açıklar <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName> sınıfı.  
  
 [ContingentProperties sınıfı](../../extensibility/debugger/contingentproperties-class-internal-members.md)  
 İç veri üyeleri açıklar `System.Threading.Tasks.ContingentProperties` sınıfı.  
  
 [AsyncTaskMethodBuilder yapısı](../../extensibility/debugger/asynctaskmethodbuilder-structure-internal-members.md)  
 İç üyeleri açıklar <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> yapısı.  
  
 [AsyncTaskMethodBuilder\<TResult > yapısı](../../extensibility/debugger/asynctaskmethodbuilder-tresult-structure-internal-members.md)  
 İç üyeleri açıklar <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder%601> yapısı.  
  
 [AsyncVoidMethodBuilder yapısı](../../extensibility/debugger/asyncvoidmethodbuilder-structure-internal-members.md)  
 İç üyeleri açıklar <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> yapısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Threading.Tasks.Task?displayProperty=fullName>   
 <xref:System.Threading.Tasks.TaskScheduler?displayProperty=fullName>   
 [Visual Studio hata ayıklayıcısı genişletilebilirliği](../../extensibility/debugger/visual-studio-debugger-extensibility.md)   
 [Paralel Programlama](/dotnet/standard/parallel-programming/index)