---
title: Veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Data Sources Window, select controls
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- data [Visual Studio], Data Sources window
ms.assetid: 20597ff8-0c98-43ec-8fb1-05376804ba48
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5b1701b95f86f3645ea7d54a47f8b3c7b36b3fd4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="set-the-control-to-be-created-when-dragging-from-the-data-sources-window"></a>Veri kaynakları penceresinden sürüklendiğinde oluşturulacak denetimini ayarlama
Verilere bağlı denetimler konumundan öğeleri sürükleyerek oluşturabileceğiniz **veri kaynakları** WPF Tasarımcısı veya Windows Form Tasarımcısı penceresinde. Her öğe **veri kaynakları** penceresinde Designer'a sürüklediğinizde oluşturulan bir varsayılan denetim vardır. Ancak, farklı bir denetim oluşturmak seçebilirsiniz.

## <a name="set-the-controls-to-be-created-for-data-tables-or-objects"></a>Veri tabloları veya nesneler için oluşturulması için denetimleri ayarlama
Veri tabloları ya da nesneleri temsil öğeleri sürükleyin önce **veri kaynakları** penceresinde, tüm verileri bir denetimi görüntüleme ya da her bir sütun veya özelliği ayrı bir denetimi görüntüleme seçebilirsiniz.

Bu bağlamda terimi *nesne* özel iş nesnesi, bir varlığı (bir varlık veri modeli) ya da bir hizmet tarafından döndürülen nesne anlamına gelir.

### <a name="to-set-the-controls-to-be-created-for-data-tables-or-objects"></a>Veri tabloları veya nesneler için oluşturulacak denetimleri ayarlamak için

1.  WPF Tasarımcısı'nı veya Windows Form Tasarımcısı açık olduğundan emin olun.

2.  İçinde **veri kaynakları** penceresinde, veri tablosu temsil eden öğesi seçin veya ayarlamak istediğiniz nesne.

3.  Öğeyi aşağı açılan menüsüne tıklayın ve menüsünden aşağıdaki öğelerden birini tıklatın:

    -   Her veri alanı ayrı bir denetiminde görüntülemek için tıklatın **ayrıntıları**. Veri öğesi Designer'a sürüklediğinizde, bu eylem her sütun veya üst veri tablo ya da her denetim için etiket yanı sıra nesnesinin özelliği için farklı bir veri bağlama denetimi oluşturun.

    -   Tüm verileri tek bir denetim görüntülemek için farklı bir denetim listesinde, aşağıdaki gibi seçin **DataGrid** veya **listesi** bir WPF uygulamasında veya **DataGridView** Windows Forms'ta uygulama.

    Hangi designer'ı kullandığınız açık, .NET Framework'ün hangi sürümünün projenizin hedeflediği kullanılabilir denetimler listesini bağlıdır ve olup özel eklediğiniz bağlama destek verilerin denetimleri **araç**. Oluşturmak istediğiniz denetim denetim listesinde, kullanılabilir durumda değilse, denetim listesine ekleyebilirsiniz. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).

    Veri tabloları veya nesneleri için denetimler listesine eklenen özel bir Windows Forms denetiminin nasıl oluşturulacağını öğrenmek için **veri kaynakları** penceresinde görmek [karmaşık veri destekleyen bir Windows Forms kullanıcı denetimi oluşturma Bağlama](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).

## <a name="set-the-controls-to-be-created-for-data-columns-or-properties"></a>Veri sütunları veya özelliklerini oluşturulması için denetimleri ayarlama
Bir sütun ya da bir nesneden bir özelliği temsil eden bir öğesi sürükleyin önce **veri kaynakları** Tasarımcı penceresine, oluşturulacak denetim ayarlayabilirsiniz.

#### <a name="to-set-the-controls-to-be-created-for-columns-or-properties"></a>Sütun veya özellikler için oluşturulacak denetimleri ayarlamak için

1.  WPF Tasarımcısı'nı veya Windows Form Tasarımcısı açık olduğundan emin olun.

2.  İçinde **veri kaynakları** penceresinde, istenen tablosunu genişletin veya sütunları veya özelliklerini görüntülemek için nesne.

3.  Oluşturulacak denetim ayarlamak istediğiniz her sütun veya özellik seçin.

4.  Sütun veya özellik açılan menüsüne tıklayın ve ardından öğeyi Designer'a sürüklendiğinde oluşturmak istediğiniz denetimi kullanır.

     Hangi designer'ı kullandığınız açık, .NET Framework'ün hangi sürümünün projenizin hedeflediği kullanılabilir denetimler listesini bağlıdır ve veri, bağlama eklediğiniz destekleyen hangi özel denetimleri **araç**. Oluşturmak istediğiniz denetim kullanılabilir denetim listesinde, denetim listesine ekleyebilirsiniz. Daha fazla bilgi için bkz: [veri kaynakları penceresine özel denetimler ekleme](../data-tools/add-custom-controls-to-the-data-sources-window.md).

     Veri sütunları veya özelliklerinde denetimleri listesine eklenen özel bir denetim oluşturmak hakkında bilgi edinmek için **veri kaynakları** penceresinde görmek [basit veri bağlamadestekleyenbirWindowsFormskullanıcıdenetimioluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).

     Sütun veya özellik için bir denetim oluşturmak istemiyorsanız seçin **hiçbiri** açılır menüde. Bu, üst tablo veya nesne tasarımcıya sürükleyin istiyor, ancak belirli sütun veya özellik eklemek istiyor musunuz yararlıdır.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md)