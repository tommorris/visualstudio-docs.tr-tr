---
title: "Nasıl yapılır: OnStart yönteminde hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e84d16d8f860586b69812c3080979ca5ea99ce8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-the-onstart-method"></a>Nasıl Yapılır: OnStart Yönteminde Hata Ayıklama
Bir Windows hizmeti, hizmet başlatma ve hata ayıklayıcısı hizmet işlemine iliştirme ayıklayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: Windows hizmet uygulamalarında hata ayıklama](/dotnet/framework/windows-services/how-to-debug-windows-service-applications). Ancak, hata ayıklamak için <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> yöntemi bir Windows hizmetinin, hata ayıklayıcı'dan yönteminin içine başlatma gerekir.  
  
1.  Bir çağrı ekleyin <xref:System.Diagnostics.Debugger.Launch%2A> başında `OnStart()`yöntemi.  
  
    ```CSharp  
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