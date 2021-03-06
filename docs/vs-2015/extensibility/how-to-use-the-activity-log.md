---
title: 'Nasıl yapılır: Etkinlik günlüğünü kullanma | Microsoft Docs'
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
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: 30
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 79a06bd3bcaa8b6361d0aaa19dffb8081d652a3b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689945"
---
# <a name="how-to-use-the-activity-log"></a>Nasıl yapılır: Etkinlik günlüğünü kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: etkinlik günlüğü'nün](https://docs.microsoft.com/visualstudio/extensibility/how-to-use-the-activity-log).  
  
VSPackage için etkinlik günlüğü iletileri yazabilirsiniz. Bu özellik, perakende ortamlarda VSPackages hata ayıklama için özellikle yararlıdır.  
  
> [!TIP]
>  Etkinlik günlüğü her zaman açıktır. Visual Studio çalışırken bir arabellek genel yapılandırma bilgilerine sahip olan ilk on girişi yanı sıra yüz en son girdileri tutar.  
  
### <a name="to-write-an-entry-to-the-activity-log"></a>Etkinlik günlüğünün bir giriş yazmak için  
  
1.  Bu kodda Ekle <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi veya başka bir yöntem VSPackage Oluşturucusu hariç:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Bu kod alır <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> hizmet ve kendisine bıraktığı bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> arabirimi. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> bilgilendirici bir giriş geçerli kültür bağlamını kullanarak etkinlik günlüğüne yazar.  
  
2.  VSPackage'ı (genellikle bir komut çağrılan veya bir pencere açılırsa olduğunda) yüklendiğinde, metin etkinlik günlüğüne yazılır.  
  
### <a name="to-examine-the-activity-log"></a>Etkinlik günlüğünü incelemek için  
  
1.  Etkinlik günlüğü için Visual Studio veri alt Bul: *% AppData %* \Microsoft\VisualStudio\14.0\ActivityLog.XML...  
  
2.  Etkinlik günlüğü herhangi bir metin düzenleyicisi ile açın. Tipik bir girişi şu şekildedir:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Etkinlik günlüğü bir hizmet olduğundan, etkinlik günlüğü VSPackage oluşturucuda kullanılamıyor.  
  
 Etkinlik günlüğü, yalnızca kendisine yazmadan önce almanız gerekir. Önbellek yok veya gelecekte kullanım için Etkinlik günlüğünü kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [VSPackage sorunlarını giderme](../extensibility/troubleshooting-vspackages.md)   
 [VSPackage’lar](../extensibility/internals/vspackages.md)

