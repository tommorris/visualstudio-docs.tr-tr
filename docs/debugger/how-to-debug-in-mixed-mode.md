---
title: "Nasıl yapılır: karışık modda hata ayıklama | Microsoft Docs"
ms.custom: 
ms.date: 06/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging DLLs
- debugging [Visual Studio], mixed-mode
- mixed-mode debugging
ms.assetid: 2859067d-7fcc-46b0-a4df-8c2101500977
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e319f0e6c9ca6197930858407a2177e9fe246907
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-debug-in-mixed-mode"></a>Nasıl Yapılır: Karışık Modda Hata Ayıklama
Aşağıdaki yordamlar, karışık mod hata ayıklaması olarak da bilinen, hem yönetilen hem de yerel kodda hata ayıklama açıklar. Olup DLL ya da uygulama yerel kodda yazılır bağlı olarak bunu yapmak için iki senaryo vardır:  
  
-   DLL çağrıları çağrı yapan uygulamanın yerel kodda yazılır. Bu durumda, DLL yönetilir ve yönetilen ve yerel hata ayıklayıcıları hem de hata ayıklama için etkinleştirilmiş olması gerekir. Bunu denetleyebilirsiniz  **\<Proje > özellik sayfaları** iletişim kutusu. Bunu nasıl yapacağınız olup, DLL projesi veya arama uygulama projesi hata ayıklama başlamanıza bağlıdır.  
  
-   DLL çağrıları çağrı yapan uygulamanın yönetilen kodda yazılır ve DLL yerel kodda yazılır.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio IDE'yi kişiselleştirme](../ide/personalizing-the-visual-studio-ide.md).

Arama uygulama için proje erişim yoksa, DLL projesi DLL'den ayıklayabilirsiniz. Daha fazla bilgi için bkz: [nasıl yapılır: DLL projesinde hata ayıklama](../debugger/how-to-debug-from-a-dll-project.md). Yalnızca DLL projesinde hata ayıklamak için karma kullanmanız gerekmez.
  
### <a name="to-enable-mixed-mode-debugging-c-calling-app"></a>Karışık mod (C++ çağıran uygulama) hata ayıklamayı etkinleştirmek için  
  
1.  İçinde **Çözüm Gezgini**, yerel projesini seçin.
  
2.  Üzerinde **Görünüm** menüsünde tıklatın **özellik sayfaları**.
  
3.  İçinde  **\<Proje > özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri** düğümünü ve ardından **hata ayıklama**.  
  
4.  Ayarlama **hata ayıklayıcı türü** için **karma** veya **otomatik**.

    ![Karışık mod hata ayıklamayı etkinleştir](../debugger/media/dbg-mixed-mode-from-native.png "karışık modda hata ayıklamayı etkinleştir")

### <a name="to-enable-mixed-mode-debugging-c-or-vb-calling-app"></a>Karışık mod (C# veya VB çağıran uygulama) hata ayıklamayı etkinleştirmek için  
  
1.  İçinde **Çözüm Gezgini**, yönetilen projesini seçin.  
  
2.  Üzerinde **Görünüm** menüsünde tıklatın **özellik sayfaları**.  
  
3.  İçinde  **\<Proje > özellik sayfaları** iletişim kutusunda **hata ayıklama** sekmesini tıklatın ve ardından **yerel kod hata ayıklamayı etkinleştir**

    ![Yerel kod hata ayıklamayı etkinleştir](../debugger/media/dbg-mixed-mode-from-csharp.png "yerel kod hata ayıklamayı etkinleştir")
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: DLL projesinde hata ayıklama](../debugger/how-to-debug-from-a-dll-project.md)