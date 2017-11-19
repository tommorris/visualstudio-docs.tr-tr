---
title: "Görev listesini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TaskListWindow
- VS.TaskList
- tasklist
helpviewer_keywords:
- task list
- Visual Studio, task list
ms.assetid: f46a75a8-47b3-4cb6-bb59-b72e3356a664
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a380d0e1503a0a0a0683d6088a1ca2f9c085184d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="using-the-task-list"></a>Görev Listesini Kullanma
Kullanmak **görev listesi** belirteçleri gibi kullandığınız kod açıklamaları izlemek için `TODO` ve `HACK`, ya da özel belirteçler ve kod önceden tanımlanmış bir konumda için doğrudan yönlendirir kısayolları yönetmek için. Kaynak kodundaki konumuna gitmek için listedeki bir öğeyi tıklatın.  
  
 Bu konuda:  
  
-   [Görev Listesi penceresi](../ide/using-the-task-list.md#taskListWindow)  
  
-   [Kullanıcı görevleri](../ide/using-the-task-list.md#userTasks)  
  
-   [Belirteçleri ve açıklamaları](../ide/using-the-task-list.md#tokensComments)  
  
-   [Özel belirteçler](../ide/using-the-task-list.md#customTokens)  
  
-   [C++ Yapılacaklar açıklamaları](../ide/using-the-task-list.md#cppComments)  
  
-   [Kısayolları](../ide/using-the-task-list.md#shortcuts)  
  
##  <a name="taskListWindow"></a>Görev Listesi penceresi  
 Zaman **görev listesi** olduğu açık, bu uygulama penceresinin alt kısmında görünür.  
  
#### <a name="to-open-the-task-list"></a>Görev Listesi'ni açmak için  
  
-   Üzerinde **Görünüm** menüsünde seçin **görev listesi** (klavye: Ctrl +\\, T).  
  
     ![Görev Listesi penceresi](../ide/media/vs2015_task_list.png "vs2015_task_list")  
  
#### <a name="to-change-the-sort-order-of-the-list"></a>Listenin sıralama düzenini değiştirmek için  
  
-   Herhangi bir sütunun başlığına tıklayın. Arama sonuçlarınızı iyice daraltmak için Shift tuşuna basın ve ikinci bir sütun başlığına tıklayın.  
  
     Alternatif olarak, kısayol menüsünde seçin **sıralama ölçütü**ve bir üstbilgi seçin. Arama sonuçlarınızı iyice daraltmak için Shift tuşuna basın ve ikinci bir başlık seçin.  
  
#### <a name="to-show-or-hide-columns"></a>Sütunları göstermek veya gizlemek için  
  
-   Kısayol menüsünden seçin **sütunları göster**. Göstermek veya gizlemek istediğiniz sütunları seçin.  
  
#### <a name="to-change-the-order-of-the-columns"></a>Sütunların sırasını değiştirmek için  
  
-   Herhangi bir sütun başlığını istediğiniz konuma sürükleyin.  
  
##  <a name="userTasks"></a>Kullanıcı görevleri  
 Visual Studio 2015'te kullanıcı görev özelliği kaldırılmıştır. Ne zaman Visual Studio 2013'ten kullanıcı görev verileri olan bir çözümü açın ve daha önceki Visual Studio 2015'te, .suo dosyanızdaki kullanıcı görev verileri etkilenmez, ancak kullanıcı görevleri görev listesinde görüntülenmez.  
  
 Erişim ve kullanıcı görev verilerinizi güncelleştirmek devam etmek istiyorsanız, Visual Studio 2013'te projeyi açın ve herhangi bir kullanıcı görevi içerik, tercih edilen proje yönetim aracı (örneğin, Team Foundation Server) kopyalayın.  
  
##  <a name="tokensComments"></a>Belirteçleri ve açıklamaları  
 Önceden tanımlanmış simge bir açıklama işaretçisi ile öncesinde, kodunuzda bir açıklama da görünür **görev listesi** penceresi. Örneğin, aşağıdaki C# açıklamasının üç ayrı bölümü vardır:  
  
-   Açıklama işaretçisi (`//`)  
  
-   Örneğin bir belirteç (`TODO`)  
  
-   Açıklama (metnin geri kalanı)  
  
```  
// TODO: Load state from previously suspended application  
```  
  
 Çünkü `TODO` önceden tanımlanmış olan olarak belirteç, bu açıklamanın görünür bir `TODO` listesinde görev.  
  
###  <a name="customTokens"></a>Özel belirteçler  
 Varsayılan olarak, Visual Studio aşağıdaki belirteçleri içerir: KORSAN, Yapılacaklar, UNDONE, unutmayın. Bunlar büyük küçük harfe duyarlı değildir.  
  
 Ayrıca kendi özel belirteçlerinizi de oluşturabilirsiniz.  
  
##### <a name="to-create-a-custom-token"></a>Özel bir belirteç oluşturmak için  
  
1.  Üzerinde **Araçları** menüsünde seçin **seçenekleri**.  
  
2.  Açık **ortam** klasörünü ve ardından **görev listesi**.  
  
     [Görev listesi, ortam, Seçenekler iletişim kutusu](../ide/reference/task-list-environment-options-dialog-box.md) görüntülenir.  
  
     ![Visual Studio görev listesi](../ide/media/vs2015_task_list_options.png "vs2015_task_list_options")  
  
3.  İçinde **belirteçleri** kategori, **adı** metin kutusunda, belirteç adınızı girin, örneğin "hata".  
  
4.  İçinde **öncelik** aşağı açılan listesinde, yeni bir belirteç için varsayılan öncelik seçin. Seçin **Ekle** düğmesi.  
  
###  <a name="cppComments"></a>C++ Yapılacaklar açıklamaları  
 C++ Yapılacaklar açıklamaları görüntülenen varsayılan olarak, **görev listesi** penceresi. Bu davranışı değiştirebilirsiniz.  
  
##### <a name="to-turn-off-c-todo-comments"></a>C++ Yapılacaklar yorumlarını kapatmak için  
  
1.  Üzerinde **Araçları** menüsünde, Git **Seçenekleri &#124; Metin Düzenleyici &#124; C/C++ &#124; Görünüm &#124; Açıklama görevleri listeleme** ve değeri false olarak ayarlayın.  
  
2.  İçinde **seçenekleri** açık iletişim kutusunu **metin düzenleyici**.  
  
3.  Altında **C/C++**, seçin **Görünüm**ve ardından **açıklama görevleri listeleme** için **False**.  
  
##  <a name="shortcuts"></a>Kısayolları  
 A *kısayol* izleneceğini kodda yer işareti **görev listesi**; normal bir yer işareti daha farklı bir simgesi vardır. Kısayolu **görev listesi** kodda karşılık gelen konuma gitmek için.  
  
 ![Visual Studio görev listesi kısayol simgesini](../ide/media/vs2015_task_list_bookmark.png "vs2015_task_list_bookmark")  
  
#### <a name="to-create-a-shortcut"></a>Bir kısayol oluşturmak için  
  
-   İşaretçiyi, kod içinde kısayolu yerleştirmek istediğiniz yere ekleyin. Seçin **&#124; Düzenle Yer işaretleri &#124; Görev listesi kısayolu eklemek** veya basın (klavye: Ctrl + K, Ctrl + H).  
  
     Kodda kısayolları gezinmek için listede bir kısayol seçin ve ardından **sonraki görev** veya **önceki görev** kısayol menüsünden.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görev listesi, ortam, Seçenekler iletişim kutusu](../ide/reference/task-list-environment-options-dialog-box.md)