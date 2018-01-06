---
title: "Kaynak Denetimi çalışma zamanı ayrıntıları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9b27aa56cdcf48ded56f9a43e40a1e65f3491536
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-runtime-details"></a>Kaynak Denetimi çalışma zamanı ayrıntıları
Kullanıcı bir dosyayı projede kaynak denetimine ya da bir sihirbaz gibi bir Otomasyon denetleyicisi aracılığıyla eklediğinde bir proje için kaynak denetimi eklenir. Bir proje kendisi için kaynak denetimi altında olduğunu belirtmez; Kaynak denetimi destekler, ancak el ile eklenmesi gerekir.  
  
## <a name="registering-with-a-source-control-package"></a>Bir kaynak denetimi paketiyle kaydetme  
 Projenizdeki dosya kaynak denetimine eklendiğinde, ortam çağırır <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> tanımlama bilgileri kaynak denetim sistemi tarafından kullanılan dört donuk dizeleri sağlamak için. Bu dizeler, proje dosyasında depolar. Bu dizeler kaynak denetimi saplama (kaynak denetim paketleri yöneten Visual Studio bileşeni) proje türü başlatmada çağırarak iletilmesi gereken <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>. Bu sırayla uygun kaynak denetimi paketini yükler ve onun uyarlamasını çağrısına iletilen `IVsSccManager2::RegisterSccProject`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [Kaynak Denetimini Destekleme](../../extensibility/internals/supporting-source-control.md)