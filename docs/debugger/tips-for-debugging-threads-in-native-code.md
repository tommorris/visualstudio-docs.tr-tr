---
title: Yerel kod iş parçacıklarında hata ayıklama ipuçları | Microsoft Docs
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
- threading [Visual Studio], debugging
- debugging [Visual Studio], threads
ms.assetid: 0374c8c6-57a3-4cfe-8047-2effef5ff5dc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 72b913c64d78966bde96419978a066cc9921ebaa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="tips-for-debugging-threads-in-native-code"></a>Yerel Kod İş Parçacıklarında Hata Ayıklama İpuçları
Yerel kod iş parçacıklarında hata ayıklama sırasında kullanabileceğiniz bazı ipuçları şunlardır:  
  
-   İş parçacığı bilgileri bloğu içeriğini yazarak görüntüleyebilirsiniz `@TIB` içinde **izleme** penceresi veya **QuickWatch** iletişim kutusu.  
  
-   Geçerli iş parçacığı için son hata kodunu girerek görüntüleyebilirsiniz `@Err` içinde **izleme** penceresi veya **QuickWatch** iletişim kutusu.  
  
-   C çalışma zamanı kitaplıkları (CRT) işlevleri çok iş parçacıklı uygulamada hata ayıklama için yararlı olabilir. Daha fazla bilgi için bkz: [_malloc_dbg](/cpp/c-runtime-library/reference/malloc-dbg).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)