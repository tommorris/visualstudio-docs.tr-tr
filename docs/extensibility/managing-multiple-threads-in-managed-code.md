---
title: "Nasıl yapılır: yönetilen kod birden çok iş parçacığı yönetme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59730063-cc29-4dae-baff-2234ad8d0c8f
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c246c8be1d10893b018d5d0c5727d4af42efdc6b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-managing-multiple-threads-in-managed-code"></a>Nasıl yapılır: yönetilen kod birden çok iş parçacığı yönetme
Visual Studio kullanıcı Arabirimi iş parçacığı dışında iş parçacığı yürütmek işlemlerini zaman uyumsuz yöntemleri çağırır veya yönetilen bir VSPackage uzantısı varsa, aşağıda verilen yönergeleri izlemelidir. Tamamlamak için başka bir iş parçacığında iş için beklenecek gerekmez çünkü kullanıcı Arabirimi iş parçacığı yanıt verebilir durumda kalmasını sağlayabilir. Yığın yer kaplar ek iş parçacığı olmadığından, kodunuzu daha verimli hale getirebilir ve daha güvenilir ve kilitlenmeler ve askıda önlemek için hata ayıklama kolay yapabilirsiniz.  
  
 Genel olarak, farklı bir iş parçacığı kullanıcı Arabirimi iş parçacığından geçebilir veya tam tersi. Yöntem döndüğünde, geçerli iş parçacığının içinden başlangıçta çağrıldı parçacığıdır.  
  
> [!IMPORTANT]
>  API'leri aşağıdaki kılavuzları kullanın <xref:Microsoft.VisualStudio.Threading> ad alanı, özellikle, <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> sınıfı. Bu ad alanındaki API'leri yeni [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)]. Bir örneği elde edebilirsiniz bir <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory> gelen <xref:Microsoft.VisualStudio.Shell.ThreadHelper> özelliği `ThreadHelper.JoinableTaskFactory`.  
  
## <a name="switching-from-the-ui-thread-to-a-background-thread"></a>Arka plan iş parçacığı için kullanıcı Arabirimi iş parçacığından değiştirme  
  
1.  Kullanıcı Arabirimi iş parçacığı üzerinde olan ve arka plan iş parçacığında zaman uyumsuz iş yapmak istiyorsanız Task.Run() kullanın:  
  
    ```csharp  
    await Task.Run(async delegate{  
        // Now you're on a separate thread.  
    });  
    // Now you're back on the UI thread.  
  
    ```  
  
2.  Kullanıcı Arabirimi iş parçacığı üzerinde olan ve arka plan iş parçacığında, kullanım iş gerçekleştirirken zaman uyumlu olarak engellemek istiyorsanız <xref:System.Threading.Tasks.TaskScheduler> özelliği `TaskScheduler.Default` içinde <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>:  
  
    ```csharp  
    // using Microsoft.VisualStudio.Threading;  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        await TaskScheduler.Default;  
        // You're now on a separate thread.  
        DoSomethingSynchronous();  
        await OrSomethingAsynchronous();  
    });  
    ```  
  
## <a name="switching-from-a-background-thread-to-the-ui-thread"></a>Arka plan iş parçacığından kullanıcı Arabirimi iş parçacığına değiştirme  
  
1.  Arka plan iş parçacığında yapıyorsanız ve kullanıcı Arabirimi iş parçacığı kullanımı üzerinde bir şeyler istiyorsanız <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>:  
  
    ```csharp  
    // Switch to main thread  
    await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
    ```  
  
     Kullanabileceğiniz <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A> için kullanıcı Arabirimi iş parçacığı geçiş yapmak için yöntem. Bu yöntem, geçerli zaman uyumsuz yöntem devamlılık ile kullanıcı Arabirimi iş parçacığı için bir ileti gönderir ve ayrıca doğru önceliğini ayarlamak ve kilitlenmeleri önlemek için iş parçacığı framework geri kalanı ile iletişim kurar.  
  
     Arka plan iş parçacığı yöntemi zaman uyumsuz değildir ve zaman uyumsuz yapamazsınız, kullanmaya devam edebilirsiniz `await` için kullanıcı Arabirimi iş parçacığı ile çalışmanızı kaydırma tarafından geçiş yapmak için sözdizimi <xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.Run%2A>, bu örnekteki gibi:  
  
    ```csharp  
    ThreadHelper.JoinableTaskFactory.Run(async delegate {  
        // Switch to main thread  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        // Do your work on the main thread here.  
    });  
    ```