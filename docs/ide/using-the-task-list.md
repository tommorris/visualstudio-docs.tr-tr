---
title: Görev listesini kullanma
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- TaskListWindow
- VS.TaskList
- tasklist
helpviewer_keywords:
- task list
- Visual Studio, task list
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a82663fe397488ee78a82d4fab5d38bfec4ae37
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="use-the-task-list"></a>Görev listesini kullanma

Kullanmak **görev listesi** belirteçleri gibi kullandığınız kod açıklamaları izlemek için `TODO` ve `HACK`, ya da özel belirteçler ve kod önceden tanımlanmış bir konumda için doğrudan yönlendirir kısayolları yönetmek için. Kaynak kodundaki konumuna gitmek için listedeki bir öğeyi tıklatın.

## <a name="the-task-list-window"></a>Görev Listesi penceresi

Zaman **görev listesi** olduğu açık, bu uygulama penceresinin alt kısmında görünür.

### <a name="open-the-task-list"></a>Görev listesi açın

- Üzerinde **Görünüm** menüsünde seçin **görev listesi** (klavye: **Ctrl**+**\\**,**T**).

    ![Görev Listesi penceresi](../ide/media/vs2015_task_list.png "vs2015_task_list")

### <a name="change-the-sort-order-of-the-list"></a>Listenin sıralama düzenini değiştirme

- Herhangi bir sütunun başlığına tıklayın. Arama sonuçlarınızı iyice daraltmak için Shift tuşuna basın ve ikinci bir sütun başlığına tıklayın.

     Alternatif olarak, kısayol menüsünde seçin **sıralama ölçütü**ve bir üstbilgi seçin. Daha fazla arama sonuçlarınızı daraltmak için basın **Shift** ve ikinci üstbilgi'i seçin.

### <a name="show-or-hide-columns"></a>Sütunları Göster veya gizle

- Kısayol menüsünden seçin **sütunları göster**. Göstermek veya gizlemek istediğiniz sütunları seçin.

### <a name="change-the-order-of-the-columns"></a>Sütunların sırasını değiştirme

- Herhangi bir sütun başlığını istediğiniz konuma sürükleyin.

## <a name="user-tasks"></a>Kullanıcı görevleri

Kullanıcı görev özelliği, Visual Studio 2015'ten başlayarak kaldırıldı. Kullanıcı, kullanıcı görev veri Visual Studio 2013'ten ve önceki sürümleri olan bir çözümü açtığınızda, verilerde görev, *.suo* dosya etkilenmez, ancak kullanıcı görevleri görev listesinde görüntülenmez.

Erişim ve kullanıcı görev verilerinizi güncelleştirmek devam etmek istiyorsanız, Visual Studio 2013'te projeyi açın ve herhangi bir kullanıcı görevi içerik, tercih edilen proje yönetim aracı (örneğin, Team Foundation Server) kopyalayın.

## <a name="tokens-and-comments"></a>Belirteçler ve açıklamalar

Önceden tanımlanmış simge bir açıklama işaretçisi ile öncesinde, kodunuzda bir açıklama da görünür **görev listesi** penceresi. Örneğin, aşağıdaki C# açıklamasının üç ayrı bölümü vardır:

- Açıklama işaretçisi (`//`)

- Örneğin bir belirteç (`TODO`)

- Açıklama (metnin geri kalanı)

```csharp
// TODO: Load state from previously suspended application
```

Çünkü `TODO` önceden tanımlanmış olan olarak belirteç, bu açıklamanın görünür bir `TODO` listesinde görev.

###  <a name="customTokens"></a> Özel belirteçler

Varsayılan olarak, Visual Studio aşağıdaki belirteçleri içerir: `HACK`, `TODO`, `UNDONE`, `NOTE`. Bunlar büyük küçük harfe duyarlı değildir.

Ayrıca kendi özel belirteçlerinizi de oluşturabilirsiniz.

#### <a name="create-a-custom-token"></a>Özel belirteç oluşturma

1. Üzerinde **Araçları** menüsünde seçin **seçenekleri**.

2. Açık **ortam** klasörünü ve ardından **görev listesi**.

     [Görev listesi seçenekleri sayfasında](../ide/reference/task-list-environment-options-dialog-box.md) görüntülenir.

     ![Visual Studio görev listesi](../ide/media/vs2015_task_list_options.png "vs2015_task_list_options")

3. İçinde **belirteçleri** kategori, **adı** metin kutusunda, belirteç adınızı girin, örneğin "hata".

4. İçinde **öncelik** aşağı açılan listesinde, yeni bir belirteç için varsayılan öncelik seçin. Seçin **Ekle** düğmesi.

###  <a name="cppComments"></a> C++ Yapılacaklar açıklamaları

C++ Yapılacaklar açıklamaları görüntülenen varsayılan olarak, **görev listesi** penceresi. Bu davranışı değiştirebilirsiniz.

#### <a name="turn-off-c-todo-comments"></a>C++ Yapılacaklar açıklamaları devre dışı bırakma

Üzerinde **Araçları** menüsünde seçin **seçenekleri** > **metin düzenleyici** > **C/C++**  >   **Görünüm** > **açıklama görevleri listeleme** ve değeri false olarak ayarlayın.

## <a name="shortcuts"></a>Kısayollar

A *kısayol* izleneceğini kodda yer işareti **görev listesi**; normal bir yer işareti daha farklı bir simgesi vardır. Kısayolu **görev listesi** kodda karşılık gelen konuma gitmek için.

![Visual Studio görev listesi kısayol simgesini](../ide/media/vs2015_task_list_bookmark.png "vs2015_task_list_bookmark")

### <a name="create-a-shortcut"></a>Kısayol oluşturma

Kısayol oluşturmak için bir kısayol yerleştirmek istediğiniz koda işaretçinin ekleyin. Seçin **Düzenle** > **yer işaretleri** > **görev listesi kısayol Ekle** veya basın **Ctrl** + **K**, **Ctrl**+**H**.

Kodda kısayolları gezinmek için listede bir kısayol seçin ve ardından **sonraki görev** veya **önceki görev** kısayol menüsünden.

## <a name="see-also"></a>Ayrıca bkz.

- [Görev listesi, ortam, Seçenekler iletişim kutusu](../ide/reference/task-list-environment-options-dialog-box.md)