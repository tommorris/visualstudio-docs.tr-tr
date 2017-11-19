---
title: "Nasıl yapılır: etkinlik günlüğü kullanın | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d08cd747c762d7820e4744251fb00abff22b3fdc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-the-activity-log"></a>Nasıl yapılır: etkinlik günlüğü kullanın
VSPackages etkinlik günlüğü iletileri yazabilirsiniz. Bu özellik, perakende ortamlarda VSPackages hata ayıklama için özellikle yararlıdır.  
  
> [!TIP]
>  Etkinlik günlüğü her zaman açıktır. Visual Studio, son yüz girişleri ve bunun yanı sıra genel yapılandırma bilgilerini ilk on girişleri çalışırken bir arabellek tutar.  
  
### <a name="to-write-an-entry-to-the-activity-log"></a>Etkinlik günlüğü için bir giriş yazmak için  
  
1.  Bu kod ekleme <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> yöntemi veya başka bir yöntem VSPackage Oluşturucusu dışında:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Bu kod alır <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> hizmet ve kendisine bıraktığı bir <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> arabirimi. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A>bir bilgilendirme girişi geçerli kültür bağlamı kullanarak etkinlik günlüğüne yazar.  
  
2.  VSPackage (genellikle bir komut çağrılır veya bir pencere açıldığında olduğunda) yüklendiğinde, metin etkinlik günlüğüne yazılır.  
  
### <a name="to-examine-the-activity-log"></a>Etkinlik günlüğü incelemek için  
  
1.  Etkinlik günlüğü alt klasöründe için Visual Studio verileri bulur: *% AppData %*\Microsoft\VisualStudio\15.0\ActivityLog.XML...  
  
2.  Etkinlik günlüğü ile herhangi bir metin düzenleyicisinde açın. Tipik bir girişi şöyledir:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Etkinlik günlüğü bir hizmet olduğundan, etkinlik günlüğü VSPackage oluşturucuda kullanılamaz.  
  
 Yalnızca kendisine yazmadan önce etkinlik günlüğü edinmeniz gerekir. Önbellek değil veya etkinlik günlüğü gelecekte kullanmak için kaydedin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Sorun giderme VSPackages](../extensibility/troubleshooting-vspackages.md)   
 [VSPackages](../extensibility/internals/vspackages.md)
