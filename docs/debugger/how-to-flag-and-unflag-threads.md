---
title: "Nasıl yapılır: bayrak ve iş parçacıklarını bayrakla | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 489403e4ce5052cb526a361e4548ab8823a20b18
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flag-and-unflag-threads"></a>Nasıl Yapılır: İş Parçacıklarını Bayrakla İşaretleme ve İşareti Geri Alma
Bir simge ile işaretleyerek özel dikkat vermek istediğiniz bir iş parçacığı bayrak **iş parçacığı**, **Paralel Yığınlar** (iş parçacığı Görünüm), **paralel Gözcü**ve  **GPU iş parçacıkları** windows. Başkalarının bayraklı iş parçacıkları diğer iş parçacıklarından ayırt etmek ve bu simgeyi yardımcı olabilir.  
  
Bayrak eklenmiş iş parçacığı içinde özel işleme de alırsınız **iş parçacığı** listesini **hata ayıklama konumu** araç ve diğer birden çok iş parçacıklı hata ayıklama Windows. Tüm iş parçacıkları veya yalnızca bayraklı iş parçacıklarında gösterebilir **iş parçacığı** listesi veya diğer Windows.
  
### <a name="to-flag-or-unflag-a-thread"></a>Bayrak veya bir iş parçacığı bayrakla 
  
-   İçinde **iş parçacığı** veya **paralel Gözcü** penceresinde, ilgilendiğiniz iş parçacığı bulun ve seçin veya bayrağı temizlemek için bayrak simgesine tıklayın. 
-   İçinde **Paralel Yığınlar** penceresinde, bir iş parçacığı veya grup iş parçacığı seçin ve sağ **bayrağı / <thread>**  veya **Unflag / <thread>** .
  
### <a name="to-unflag-all-threads"></a>Tüm iş parçacıklarını bayrakla için  
  
-   İçinde **iş parçacığı** penceresinde herhangi bir iş parçacığı sağ tıklayın ve ardından **tüm iş parçacıklarını bayrakla**.
-   İçinde **paralel Gözcü** penceresinde, seçin, tüm işaretlenen iş parçacıkları, sonra sağ tıklatın ve seçin **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Yalnızca görüntülemek için iş parçacıklarını bayrakla  
  
-   Seçin **yalnızca iş parçacıklarını bayrakla Göster** birden çok iş parçacıklı hata ayıklama windows birinde düğmesi.  
  
### <a name="to-flag-just-my-code"></a>Sadece kendi kodumu bayrak atamak için  
  
1.  Üstündeki araç çubuğunda **iş parçacığı** penceresinde bayrak simgesine tıklayın.  
  
2.  Aşağı açılan listeye tıklayın **bayrağı sadece kendi kodumu**.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>Seçili modülleri ile ilişkili iş parçacığı bayrak atamak için  
  
1.  Araç çubuğundaki **iş parçacığı** penceresinde bayrak simgesine tıklayın.  
  
2.  Aşağı açılan listeye tıklayın **bayrağı özel modülü seçim**.  
  
3.  İçinde **seçin modülleri** iletişim kutusunda, istediğiniz modülleri seçin.  
  
4.  (İsteğe bağlı) İçinde **arama** belirli modüller için arama dizesi yazın.  
  
5.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Çok iş parçacıklı uygulamalarda hata ayıklama kullanmaya başlama](../debugger/get-started-debugging-multithreaded-apps.md)  
 [İzlenecek yol: iş parçacıkları penceresini kullanarak birden çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/how-to-use-the-threads-window.md)