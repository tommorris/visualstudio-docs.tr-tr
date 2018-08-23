---
title: Bir özel durum sonra yürütmeye devam | Microsoft Docs
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
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a71d71622809dfaeea399355e490fe4e69b52b9f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694972"
---
# <a name="continuing-execution-after-an-exception"></a>Özel Durumdan Sonra Yürütmeye Devam Etme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [devam eden yürütme sonrasında bir özel durum](https://docs.microsoft.com/visualstudio/debugger/continuing-execution-after-an-exception).  
  
Hata ayıklayıcı bir özel durum nedeniyle yürütmeyi keserse, bir iletişim kutusu görüntülenir. Visual Basic veya C# için göreceğiniz [özel durum Yardımcısı'nı](http://msdn.microsoft.com/library/992892ac-9d52-44cc-bf09-b44bfc5befeb) iletişim kutusunda, varsayılan olarak. C++ için eski görürsünüz **özel durum** iletişim kutusu. Visual Basic veya C# kullanarak ancak devre dışı bırakmış **özel durum Yardımcısı'nı** içinde **seçenekleri** iletişim kutusu görürsünüz **özel durum** iletişim kutusu.  
  
 Zaman **özel durum Yardımcısı'nı** veya **özel durum** iletişim kutusu görüntülenirse, özel duruma neden olan sorunu düzeltmeye çalışın.  
  
## <a name="managed-code"></a>Yönetilen kod  
 Yönetilen kodda, yürütme aynı iş parçacığında işlenmeyen bir özel durumdan sonra devam edebilirsiniz. **Özel durum Yardımcısı'nı** burada özel durum oluşturuldu noktasına çağrı yığınını geriye doğru izler.  
  
## <a name="native-code"></a>Yerel kod  
 Yerel C/C++'da, iki seçeneğiniz vardır:  
  
-   Tıklayabilirsiniz **sonu** ve sorunu düzeltmeye çalışın. Kesme modunda çalışırken, çağrı yığını bir çerçeveye sağ tıklayarak geriye doğru izleyebilirsiniz **çağrı yığını** penceresi ve seçerek **geriye doğru izleme bu çerçeveye** kısayol menüsünde. Hata ayıklama devam ederken **özel durum** iletişim kutusu görüntülenirse yeniden sorun sabit değil. Aksi takdirde, **özel durum** iletişim kutusu değil görünecektir.  
  
-   Tıklayabilirsiniz **devam** yürütme sorunu gidermeyi denemeye olmadan devam etmek için. **Özel durum** iletişim kutusu görüntülenir.  
  
## <a name="mixed-code"></a>Karışık kod  
 Karma bir yerel ve yönetilen kod hata ayıklama sırasında işlenmeyen özel durumu, işletim sistemi kısıtlamaları çağrı yığınını geriye doğru izleme engeller. Kısayol menüsünü kullanarak çağrı yığınını geri sarma çalışırsanız, bir hata iletisi, hata ayıklayıcı işlenmeyen bir bırakma olamaz açıklar dışındaki hata ayıklama sırasında karma kodu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durumları hata ayıklayıcısı ile yönetme](../debugger/managing-exceptions-with-the-debugger.md)





