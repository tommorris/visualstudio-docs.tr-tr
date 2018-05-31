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
ms.openlocfilehash: 46a156e7f016c0966321240f5ae2362f2bc161e7
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34336077"
---
# <a name="use-the-task-list"></a>Görev listesini kullanma

Kullanmak **görev listesi** belirteçleri gibi kullandığınız kod açıklamaları izlemek için `TODO` ve `HACK`, ya da özel belirteçler ve doğrudan kod önceden tanımlanmış bir konumda için uygulamanız kısayolları yönetmek için. Kaynak kodundaki konumuna gitmek için listedeki bir öğeyi tıklatın.

## <a name="the-task-list-window"></a>Görev Listesi penceresi

Zaman **görev listesi** olduğu açık, bu uygulama penceresinin alt kısmında görünür.

Açmak için **görev listesi**seçin **Görünüm** > **görev listesi**, veya klavye Press **Ctrl** + **\\**,**T**.

![Görev Listesi penceresi](../ide/media/vs2015_task_list.png)

Listedeki sıralama düzenini değiştirmek için herhangi bir sütun başlığını seçin. Daha fazla arama sonuçlarınızı daraltmak için basın **Shift** ve ikinci bir sütun başlığını tıklatın. Alternatif olarak, kısayol menüsünden seçin **sıralama ölçütü**ve ardından bir üstbilgi seçin. Daha fazla arama sonuçlarınızı daraltmak için basın **Shift** ve ikinci üstbilgi'i seçin.

Kısayol menüsünde, sütunları göster veya gizle tercih **sütunları göster**. Göstermek veya gizlemek istediğiniz sütunları seçin.

Sütunların sırasını değiştirmek için herhangi bir sütun başlığını istediğiniz yere sürükleyin.

## <a name="user-tasks"></a>Kullanıcı görevleri

Visual Studio 2015'te kullanıcı görev özelliği kaldırıldı. Visual Studio 2013'ten ve daha önce kullanıcı görev veri bulunduğu bir çözümü açtığınızda, kullanıcı görev verilerde, *.suo* dosya etkilenmez, ancak kullanıcı görevleri görev listesinde görüntülenmez.

Erişim ve kullanıcı görev verilerinizi güncelleştirmek için Visual Studio 2013'te projeyi açın ve herhangi bir kullanıcı görevi içerik, tercih edilen proje yönetim aracı (örneğin, Team Foundation Server) kopyalayın devam etmek istiyorsanız.

## <a name="tokens-and-comments"></a>Belirteçler ve açıklamalar

Önceden tanımlanmış simge bir açıklama işaretçisi ile öncesinde, kodunuzda bir açıklama da görünür **görev listesi**. Örneğin, aşağıdaki C# açıklamasının üç ayrı bölümü vardır:

- Açıklama işaretçisi (`//`)

- Örneğin bir belirteç (`TODO`)

- Açıklama (metnin geri kalanı)

```csharp
// TODO: Load state from previously suspended application
```

Çünkü `TODO` önceden tanımlanmış olan olarak belirteç, bu açıklamanın görünür bir `TODO` listesinde görev.

### <a name="custom-tokens"></a>Özel belirteçler

Varsayılan olarak, Visual Studio aşağıdaki belirteçleri içerir: `HACK`, `TODO`, `UNDONE`, ve `NOTE`. Bunlar büyük küçük harfe duyarlı değildir.

Ayrıca kendi özel belirteçlerinizi de oluşturabilirsiniz. Özel belirteç oluşturmak için:

1. Üzerinde **Araçları** menüsünde seçin **seçenekleri**.

2. Açık **ortam** klasörünü ve ardından **görev listesi**.

   [Görev listesi seçenekleri sayfasında](../ide/reference/task-list-environment-options-dialog-box.md) görüntülenir.

   ![Visual Studio görev listesi](../ide/media/vs2015_task_list_options.png)

3. İçinde **belirteçleri** kategori, **adı** metin kutusunda, belirteç adınızı girin, örneğin **hata**.

4. İçinde **öncelik** aşağı açılan listesinde, yeni bir belirteç için varsayılan öncelik seçin. Seçin **Ekle** düğmesi.

### <a name="c-todo-comments"></a>C++ TODO açıklamaları

C++ Yapılacaklar açıklamaları görüntülenen varsayılan olarak, **görev listesi**.

C++ Yapılacaklar açıklamaları devre dışı bırakmak için **Araçları** menüsünde seçin **seçenekleri** > **metin düzenleyici** > **C/C++**  >  **Görünüm** > **açıklama görevleri listeleme**ve değeri **false**.

## <a name="shortcuts"></a>Kısayollar

A *kısayol* izleneceğini kodda yer işareti **görev listesi**. Normal bir yer işareti daha farklı bir simgesi vardır. Kısayolu **görev listesi** kodda karşılık gelen konuma gitmek için.

![Visual Studio görev listesi kısayol simgesi](../ide/media/vs2015_task_list_bookmark.png)

### <a name="create-a-shortcut"></a>Kısayol oluşturma

Kısayol oluşturmak için bir kısayol yerleştirmek istediğiniz koda işaretçinin ekleyin. Seçin **Düzenle** > **yer işaretleri** > **görev listesi kısayol Ekle** veya basın **Ctrl** + **K**, **Ctrl**+**H**.

Kodda kısayolları gezinmek için listede bir kısayol seçin ve ardından **sonraki görev** veya **önceki görev** kısayol menüsünden.

## <a name="see-also"></a>Ayrıca bkz.

- [Görev listesi, ortam, Seçenekler iletişim kutusu](../ide/reference/task-list-environment-options-dialog-box.md)