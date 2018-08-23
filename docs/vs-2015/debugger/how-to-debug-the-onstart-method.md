---
title: 'Nasıl yapılır: OnStart metodunda hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- OnStart method
- debugging [Visual Studio], Windows services
- debugging managed code, OnStart method
- debugging Windows Services applications, OnStart method
- Windows Service applications, debugging
ms.assetid: b06b5d65-424b-490f-bf58-97583cd7006a
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c2528c99c0f607c3fc98cb8d10e15bfa0c2316f4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673779"
---
# <a name="how-to-debug-the-onstart-method"></a>Nasıl Yapılır: OnStart Yönteminde Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: OnStart metodunda hata ayıklama](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-the-onstart-method).  
  
Bir Windows hizmeti, hizmete ve hata ayıklayıcı hizmet işlemine iliştirme ayıklayabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Windows hizmet uygulamaları hata ayıklama](http://msdn.microsoft.com/library/63ab0800-0f05-4f1e-88e6-94c73fd920a2). Ancak, hata ayıklamak için <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> yöntemi bir Windows hizmetinin ayıklayıcısından yöntemi içinde başlatmak gerekir.  
  
1.  Bir çağrı ekleyin <xref:System.Diagnostics.Debugger.Launch%2A> başındaki `OnStart()`yöntemi.  
  
    ```csharp  
    protected override void OnStart(string[] args)  
    {  
        System.Diagnostics.Debugger.Launch();  
     }  
    ```  
  
2.  Hizmeti Başlat (kullanabilirsiniz `net start`, ya da başlatın **Hizmetleri** pencere).  
  
     Bir iletişim kutusu aşağıdaki gibi görmeniz gerekir:  
  
     ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")  
  
3.  Seçin **Evet, hata ayıklama \<hizmet adı >.**  
  
4.  Tam zamanında hata ayıklayıcı penceresinde, hata ayıklama için kullanmak istediğiniz Visual Studio sürümünü seçin.  
  
     ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")  
  
5.  Yeni bir örneğini Visual Studio başlatılır ve yürütme sırasında durduruldu `Debugger.Launch()` yöntemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)



