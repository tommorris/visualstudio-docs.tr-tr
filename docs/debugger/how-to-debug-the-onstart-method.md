---
title: 'Nasıl yapılır: OnStart yönteminde hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- OnStart method
- debugging [Visual Studio], Windows services
- debugging managed code, OnStart method
- debugging Windows Services applications, OnStart method
- Windows Service applications, debugging
ms.assetid: b06b5d65-424b-490f-bf58-97583cd7006a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 369cebf83f1d3dc54472b4c912b4196427684a38
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-the-onstart-method"></a>Nasıl Yapılır: OnStart Yönteminde Hata Ayıklama
Bir Windows hizmeti, hizmet başlatma ve hata ayıklayıcısı hizmet işlemine iliştirme ayıklayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Windows hizmet uygulamalarında hata ayıklama](/dotnet/framework/windows-services/how-to-debug-windows-service-applications). Ancak, hata ayıklamak için <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> yöntemi bir Windows hizmetinin, hata ayıklayıcı'dan yönteminin içine başlatma gerekir.  
  
1.  Bir çağrı ekleyin <xref:System.Diagnostics.Debugger.Launch%2A> başında `OnStart()`yöntemi.  
  
    ```csharp  
    protected override void OnStart(string[] args)  
    {  
        System.Diagnostics.Debugger.Launch();  
     }  
    ```  
  
2.  Hizmeti başlatmak (kullanabileceğiniz `net start`, veya başlatın **Hizmetleri** penceresi).  
  
     Bir iletişim kutusu aşağıdaki gibi görmeniz gerekir:  
  
     ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")  
  
3.  Seçin **Evet, hata ayıklama \<hizmet adı >.**  
  
4.  Just-In-Time hata ayıklayıcı penceresinde Visual Studio hata ayıklama için kullanmak istediğiniz sürümü seçin.  
  
     ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")  
  
5.  Visual Studio başlar ve yürütme yeni bir örneğini adresindeki durdurulursa `Debugger.Launch()` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklama güvenliği](../debugger/debugger-security.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)