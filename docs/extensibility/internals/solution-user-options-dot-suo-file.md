---
title: "Çözüm kullanıcı seçenekleri (. Suo) dosya | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .suo files, VSPackages
- suo files, VSPackages
- solutions, .suo files
- solutions, user options
- solution user options (.suo) file
ms.assetid: 75258e0d-600d-4a3d-94f4-3d7ac12cb47c
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a71f3e14c6a8c87290de2a6204fa28f99a8cabe8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="solution-user-options-suo-file"></a>Çözüm kullanıcı seçenekleri (. Suo) dosyası
Çözüm kullanıcı seçenekleri (.suo) dosyası, kullanıcı başına çözüm seçenekleri içerir. Bu dosya için kaynak kodu denetimi denetlenmesi değil.  
  
 Çözüm kullanıcı seçenekleri (.suo) yapılandırılmış depolama veya bileşik, ikili dosya biçiminde depolanan dosya dosyasıdır. .Suo dosyasındaki bilgileri tanımlamak için kullanılan anahtar edilen Akış adı akışları kullanıcı bilgilerini kaydedin. Çözüm kullanıcı seçenekleri dosyasını kullanıcı tercih ayarlarını depolamak için kullanılır ve Visual Studio çözüm kaydettiğinde otomatik olarak oluşturulur.  
  
 Ortam .suo dosya açıldığında, tüm yüklü VSPackages numaralandırır. Bir VSPackage uyguluyorsa <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> arabirimi sonra ortamı çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.LoadUserOptions%2A> tüm verilerini .suo dosyadan yüklemek için bu isteyen VSPackage yöntemi.  
  
 Bu, ne akışları bilmeniz VSPackage'nın sorumluluk .suo dosyasına yazılan olur. Yazdığı her akış için VSPackage çağrılar geri ortamı üzerinden <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> akış adıdır anahtarı ile tanımlanan belirli bir akış yüklenemedi. Ortam sonra geri geçirme Akış adı belirli Bu akış okumayı VSPackage arar ve bir `IStream` işaretçi <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> yöntemi.  
  
 Bu noktada, başka bir çağrı yapılır `LoadUserOptions` okunacak .suo dosyaları başka bir kısmında olup olmadığını görmek için. Bu işlem, tüm veri akışlarını .suo dosyasındaki okunan ve ortamı tarafından işlenen kadar devam eder.  
  
 Ne zaman çözüm kaydedildi veya kapalı, ortam çağrıları <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.SavePackageSolutionProps%2A> gösteren bir işaretçi yöntemiyle <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.SaveUserOptions%2A> yöntemi. Bir `IStream` kaydedilecek ikili bilgi içeren iletilir <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.WriteUserOptions%2A> sonra .suo dosya ve çağrıları için bilgi Yazar yöntemi `SaveUserOptions` yeniden .suo yazma bilgilerinin başka bir akış olup olmadığını görmek için yöntemi dosya.  
  
 Bu iki yöntem `SaveUserOptions` ve `WriteUserOptions`, işaretçi geçirme .suo dosyanın kaydedileceği bilgilerinin her akış için yinelemeli olarak adlandırılır `IVsSolutionPersistence`. Bunlar birden çok akış .suo dosyaya yazmak için izin vermek için yinelemeli olarak adlandırılır. Bu şekilde, kullanıcı bilgilerini çözümle kalıcı ve çözüm bir sonraki açılışında olması garanti edilmez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 [Çözümleri](../../extensibility/internals/solutions.md)