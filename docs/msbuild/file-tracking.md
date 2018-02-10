---
title: Dosya izleme | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- msbuild, file tracking
ms.assetid: e6c66ac0-3464-451f-9192-3b98dca21b4a
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 98bf98493d6f45be31ef98ae0b4a98bfbd66e402
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="file-tracking"></a>Dosya İzleme
İzleme dosyası bir işlem ve alt işlemleri için Windows dosya sistemi çağrıları günlüğe kaydeder. Aşağıda listelenen işlevleri çağırarak programları bu günlüğü açıp kapatabilirsiniz ve kullanmak için günlük dosyasını belirtmek ne zaman denetleyin.  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [EndTrackingContext](../msbuild/endtrackingcontext.md)  
 Geçerli bağlam izlemeyi durdurun.  
  
 [ResumeTracking](../msbuild/resumetracking.md)  
 Çağrı sonra izleme Sürdür [SuspendTracking](../msbuild/suspendtracking.md).  
  
 [SetThreadCount](../msbuild/setthreadcount.md)  
 İzleme için kullanılacak iş parçacığı sayısını ayarlayın.  
  
 [StartTrackingContext](../msbuild/starttrackingcontext.md)  
 Yeni bir izleme bağlamı başlayın.  
  
 [StartTrackingContextWithRoot](../msbuild/starttrackingcontextwithroot.md)  
 Belirtilen kök sahip yeni bir izleme bağlamı başlayın.  
  
 [StopTrackingAndCleanup](../msbuild/stoptrackingandcleanup.md)  
 İzleme ve kullanılan yayın kaynakları sonlandırın.  
  
 [SuspendTracking](../msbuild/suspendtracking.md)  
 İzleme geçici olarak askıya alın.  
  
 [WriteAllTLogs](../msbuild/writealltlogs.md)  
 İzleme günlükleri tüm bağlamları için kullanıma yazma.  
  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)  
 Geçerli bağlam için izleme günlüğüne çıkışı yazma.