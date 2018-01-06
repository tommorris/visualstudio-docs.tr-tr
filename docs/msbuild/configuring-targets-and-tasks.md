---
title: "Hedefleri ve görevleri yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aabe67a-1720-4bbf-80d3-822b3ccf75c0
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9b0f7676baa604ba301a3b600786d3ce6539f57c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-targets-and-tasks"></a>Hedefleri ve Görevleri Yapılandırma
MSBuild hedefleri ve görevleri çalıştırmak için yapılandırabilirsiniz zaman-işlem MSBuild ile böylece üzerinde çalıştığını bir farklılık bağlamları hedefleyebilirsiniz. Örneğin, geliştirme bilgisayarında .NET Framework 4.5 64-bit işletim sisteminde çalışırken 32 bitlik bir .NET Framework 2.0 uygulama hedefleyebilirsiniz. .NET Framework 4 veya önceki sürümleri çalıştıran bilgisayarlar ayrıca hedefleyebilirsiniz. 32 veya 64 bit ve belirli .NET Framework sürüm bileşimi olarak bilinen *hedef bağlamı*.  
  
## <a name="installation"></a>Yükleme  
 .NET Framework 4.5 ve 4.5.1 ortak dil çalışma zamanı (CLR), hedefler, görevleri ve araçları, .NET Framework 4 yeniden adlandırma olmadan değiştirin. .NET Framework 4.5.1'deki parçası olarak yüklenmiş [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)].  
  
 MSBuild ayrıca Visual Studio'dan yüklemek istiyorsanız, yükleme paketinden indirebilirsiniz [MSBuild karşıdan](http://go.microsoft.com/fwlink/?LinkId=309745). Ayrıca kullanmak istediğiniz .NET Framework sürümleri de yüklemeniz gerekir.  
  
## <a name="targets-and-tasks"></a>Hedefler ve Görevler  
 Derleme görevleri daha büyük bir bağlamları hedeflemek için işlem dışı belirli MSBuild çalıştırır.  Örneğin, bir 32 bit MSBuild derleme görevi bir 64-bit bilgisayarda hedeflemek için 64-bit işlem çalıştırabilirsiniz. Bu tarafından denetlenir `UsingTask` bağımsız değişkenleri ve `Task` parametreleri. Bu bağımsız değişkenleri ve parametreleri tarafından .NET Framework 4.5 yüklü hedeflerini ayarlayın ve değişiklik çeşitli hedef bağlamları için uygulamalar oluşturmak için gerekli değildir.  
  
 Kendi hedef bağlamı oluşturmak istiyorsanız, bu bağımsız değişkenleri ve parametreleri uygun şekilde ayarlamanız gerekir. .NET Framework 4.5 Microsoft.Common.targets dosyasını ve örnekler için Microsoft.Common.Tasks dosyasını bakın.  Birden çok hedef bağlamlarla çalışabilmeniz için özel bir görev oluşturma veya varolan görevleri değiştirme hakkında daha fazla bilgi için bkz: [nasıl yapılır: yapılandırma hedefleri ve görevleri](../msbuild/how-to-configure-targets-and-tasks.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çoklu sürüm desteği](../msbuild/msbuild-multitargeting-overview.md)