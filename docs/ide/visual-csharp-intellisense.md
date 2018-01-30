---
title: C# IntelliSense | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- C#, IntelliSense
- IntelliSense [C#]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 9da494eaf71a02f7b46ce68b1cf9f781fe32e716
ms.sourcegitcommit: b18844078a30d59014b48a9c247848dea188b0ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="c-intellisense"></a>C# IntelliSense

C# IntelliSense olduğunda kullanılabilir düzenleyicisinde ve içinde hata ayıklama sırasında kodlama [anlık mod](../ide/reference/immediate-window.md) komut penceresi.

## <a name="completion-lists"></a>Tamamlanma listeleri

C# IntelliSense tamamlanma listeleri belirteçlerinden listesi üyeleri, tam sözcüğü ve daha fazlasını içerir. Hızlı erişim sağlar:

- Üyeleri bir türü veya ad alanı

- Değişkenleri, komutlar ve İşlevler adları

- Kod parçacıkları

- Dil anahtar sözcükleri

- Uzantı Metotları

Tamamlama C# ' de ilgisiz belirteçleri filtreleyip bağlamına dayalı bir belirteç önceden seçmek akıllı listesidir. Daha fazla bilgi için bkz: [filtrelenmiş tamamlanma listeleri](#filtered-completion-lists).

## <a name="code-snippets-in-completion-lists"></a>Tamamlanma listeleri kod parçacıkları

C# ' ta kod önceden tanımlanmış gövdeleri programınıza kolayca eklemenize yardımcı olmak için kod parçacıkları tamamlanma listesi içerir. Kod parçacıkları kod parçacığını 's tamamlama listede görünür [kısayol metni](../ide/code-snippets-schema-reference.md#shortcut). Varsayılan olarak C# dilinde kullanılabilir kod parçacıkları hakkında daha fazla bilgi için bkz: [C# kod parçacıkları](../ide/visual-csharp-code-snippets.md).

## <a name="language-keywords-in-completion-lists"></a>Dil anahtar tamamlanma listeleri

C# ' ta tamamlama liste dil anahtar sözcükleri da içerir. C# dili anahtar sözcükler hakkında daha fazla bilgi için bkz: [C# anahtar sözcükleri](/dotnet/csharp/language-reference/keywords/index).

## <a name="extension-methods-in-completion-lists"></a>Tamamlanma listeleri genişletme yöntemleri

C# ' ta tamamlanma listesi kapsamındaki genişletme yöntemleri içerir.

> [!NOTE]
> Tamamlanma listesi tüm uzantı yöntemleri için görüntülemez <xref:System.String> nesneleri.

Genişletme yöntemleri örnek yöntemleri farklı bir simge kullanın. Liste simgelerini listesi için bkz: [sınıf görünümü ve Nesne Tarayıcısı simgeleri](../ide/class-view-and-object-browser-icons.md). Bir örnek yöntemi genişletme yöntemi aynı ada sahip hem de kapsamında olması, tamamlanma listesi uzantısı yöntemi simgesi görüntüler.

## <a name="filtered-completion-lists"></a>Filtrelenmiş tamamlanma listeleri

IntelliSense filtreleri kullanarak gereksiz üyeleri tamamlama listesinden kaldırır. C# bu öğeler için görünür tamamlanma listeleri filtreler:

- **Arabirimleri ve temel sınıflar**: IntelliSense otomatik olarak kaldırır öğeleri arabirimi ve temel sınıf tamamlanma listeleri, sınıf bildirimi temel ve arabirim listeler ve kısıtlama listeler. Örneğin, numaralandırmalar temel sınıflar için kullanıldığından temel sınıflar için tamamlama listesindeki numaralandırmaları görünmez. Temel sınıflar tamamlanma listesi yalnızca arabirimleri ve ad alanlarını içerir. Listeden bir öğe seçin ve ardından virgül yazarsanız, C#, birden çok devralma desteklemediği için IntelliSense temel sınıflar tamamlama listesinden kaldırır. Aynı davranış için kısıtlama yan tümceleri de oluşur.

- **Öznitelikleri**: bir öznitelik türü için geçerli olduğunda, böylece listesi yalnızca bu türleri gibi içeren ad alanlarını Düzen bu türlerde içerir tamamlanma listesi filtrelenir <xref:System.Attribute>.

- **Catch yan tümceleri**

- **Nesne başlatıcıları**: yalnızca başlatılabilir üyeleri tamamlama listesinde görünecektir.

- **Yeni anahtar sözcük**: yazdığınızda `new` ve ardından bir tamamlanma listesi görüntülenir Ara çubuğuna basın. Bir öğe listesinde, kodunuzu bağlamda göre otomatik olarak seçilir. Örneğin, öğeleri yöntemleri return deyimleri ve bildirimler için tamamlama listesindeki otomatik olarak seçilir.

- **enum anahtar sözcüğü**: eşittir işaretinden sonra enum atama için Ara çubuğuna basın, tamamlanma listesi görüntülenir. Bir öğe listesinde, kodunuzu bağlamda göre otomatik olarak seçilir. Örneğin, öğeleri otomatik tamamlama listesinde return anahtar sözcüğü yazdıktan sonra ve bir bildirimi yaptığınızda seçilir.

- **olarak ve is işleçlerini**: yazdığınız sonra Ara çubuğu tuşlarına basın, filtrelenmiş tamamlanma listesini otomatik olarak görüntülenen `as` veya `is` anahtar sözcüğü.

- **Olayları**: anahtar sözcüğü yazdığınızda `event`, tamamlanma listesi yalnızca temsilci türleri içerir.

- **Parametre Yardım** otomatik olarak onları girerken parametrelerle eşleşen ilk yöntemi aşırı yüklemesine sıralar. Birden çok yöntem aşırı varsa, yukarı ve aşağı listesindeki sonraki olası aşırı gitmek için okları.

## <a name="most-recently-used-members"></a>En son kullanılan üyeler

IntelliSense hatırlıyor açılır pencerede yakın zamanda seçtiğiniz üyeleri [listesi üyeleri](../ide/using-intellisense.md) otomatik nesne adı tamamlama kutusunu. Üye listesi, bir sonraki kullanışınızda en son kullanılan üyeler en üstünde gösterilir. En son kullanılan üyeler geçmişini IDE içinde her oturum arasında temizlenir.

## <a name="override"></a>override

Yazdığınızda [geçersiz kılma](/dotnet/csharp/language-reference/keywords/override) ve Ara çubuğu tuşlarına basın, IntelliSense bir açılır liste kutusunda kılabilirsiniz geçerli bir taban sınıf üyelerin tümünü görüntüler. Sonraki yöntemin dönüş türünü yazarak `override` yalnızca aynı türü döndüren yöntemler göstermek için IntelliSense ister. IntelliSense eşleşmeleri bulamazsa, tüm taban sınıfı üyeleri görüntülenir.

## <a name="automatic-code-generation"></a>Otomatik Kod Oluşturma

### <a name="add-using"></a>using Ekle

**Kullanarak ekleyin** IntelliSense işlemi otomatik olarak ekler gerekli `using` kod dosyanıza yönergesi. Bu özellik, odağınız yazmak yerine, başka bir kod kısmına odağınız shift gerek kodu tutmanızı sağlar.

İşlemi kullanarak Ekle başlatmak için imleci çözümlenemeyen türü üzerinde bir başvuru getirin. Örneğin, ne zaman, bir konsol uygulaması oluşturun ve ardından ekleyin `XmlTextReader` gövdesi için `Main` yöntemi, kırmızı dalgalı görünür kod söz konusu satıra tür başvurusu çözümlenemiyor. Ardından Ekle hızlı eylemini kullanarak da çağırabilirsiniz. İmleç ilişkisiz türünde konumlandırıldığında hızlı eylem yalnızca görünür olur.

![Kullanarak, hızlı eylem genişletilmiş görüntüsü eklemek](../ide/media/addusing-quickaction.png "AddUsing QuickAction")

Ampul simgesine tıklayın ve ardından **System.Xml; kullanarak** kullanarak otomatik olarak eklenecek yönergesi.

### <a name="remove-and-sort-usings"></a>Kaldırma ve sıralama kullanımları

**Kaldır ve kullanımları sıralama** seçeneği sıralar ve kaldırır `using` ve `extern` kaynak kodunu davranışını değiştirmeden bildirimleri. Zaman içinde kaynak dosyaları bloated ve gereksiz ve düzensiz nedeniyle okunması zor hale gelebilir `using` yönergeleri. **Kaldır ve kullanımları sıralama** seçeneği sıkıştırır kaynak kodu kullanılmayan kaldırarak `using` yönergeleri ve sıralayarak okunabilirliğini artırır. Üzerinde **Düzenle** menüsünde seçin **IntelliSense**ve ardından **düzenlemek kullanımları**.

### <a name="implement-interface"></a>Arabirimi Uygulama

IntelliSense uygulamanıza yardımcı olmak için bir seçenek sunar bir [arabirimi](/dotnet/csharp/language-reference/keywords/interface) Kod düzenleyicisinde çalışırken. Normalde, bir arabirim düzgün bir şekilde uygulamak için bir yöntem bildirimi arabirimi her üyesi için sınıfınızda oluşturmanız gerekir. Sınıf bildiriminde bir arabirim adını yazdıktan sonra IntelliSense, kullanma, hızlı Eylemler ampul görüntülenir. Ampul açık veya örtülü adlandırma kullanarak arabirimi otomatik olarak uygulamak için seçeneği sunar. Açık adlandırma altında yöntem bildirimleri arabirimin adını taşıyan; örtük adlandırma altında yöntem bildirimleri ait oldukları arabirimi göstermiyor. Açık olarak adlandırılmış arabirim yöntemi yalnızca bir sınıf örneği üzerinden değil ve bir arabirim örneğinin aracılığıyla erişilebilir. Daha fazla bilgi için bkz: [açık arabirim uygulaması](/dotnet/csharp/programming-guide/interfaces/explicit-interface-implementation).

Arabirimi uygulama arabirimi karşılamak için gerekli en az sayıda yöntemi saplamalar oluşturur. Ardından bir taban sınıf arabirimi bölümlerini uyguluyorsa, bu saplamalar yeniden oluşturulmaz.

### <a name="implement-abstract-base-class"></a>Soyut taban sınıfı uygulama

IntelliSense kod düzenleyicisinde çalışırken bir soyut taban sınıfı üyeleri otomatik olarak uygulamanıza yardımcı olmak için bir seçenek sağlar. Normalde, bir soyut üyelerini uygulama için temel sınıf türetilmiş sınıfında yeni bir yöntem tanımını her yöntemi için Özet temel sınıf oluşturma gerektirir. IntelliSense, sınıf bildiriminde Özet temel sınıf adını yazdıktan sonra kullanarak, hızlı Eylemler ampul görüntülenir. Ampul taban sınıf yöntemlerini otomatik olarak uygulamak için seçeneği sunar.

Uygulama Özet temel sınıf özelliği tarafından oluşturulan yöntemi saplamalar, MethodStub.snippet dosyasında tanımlanan kod parçacığını tarafından modellenir. Kod parçacıkları değiştirilebilir. Daha fazla bilgi için bkz: [izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md).

### <a name="generate-from-usage"></a>Kullanımdan oluştur

**Kullanımından Oluştur** özelliği tanımlamadan önce sınıflar ve üyeleri kullanmanıza olanak sağlar. Herhangi bir sınıf, oluşturucusu, yöntemi, özelliği, alan veya kullanır ancak henüz tanımlanmamış istediğiniz enum için bir saplama oluşturabilir. Geçerli konumunuz kodda ayrılmadan yeni türleri ve üyeleri oluşturabilirsiniz. Bu, iş akışınızı kesintisini en aza indirir.

Kırmızı dalgalı alt çizgi her tanımlanmamış tanımlayıcı altında görüntülenir. Tanımlayıcının fare işaretçisini, bir araç ipucunda bir hata iletisi görüntülenir. Uygun seçenekleri görüntülemek için aşağıdaki yordamlardan birini kullanabilirsiniz:

- Tanımlanmamış tanımlayıcı'ı tıklatın. Hızlı Eylemler ampul tanımlayıcı altında görüntülenir. Ampul'ı tıklatın.

- Tanımlanmamış tanımlayıcı tıklayın ve sonra basın **Ctrl** + **.** (Ctrl + dönemi).

- Tanımlanmamış tanımlayıcı sağ tıklayın ve ardından **hızlı Eylemler ve yapan yeniden düzenlemeler**.

Görünen seçenekleri şunları içerebilir:

- **Özellik Oluştur**

- **Alanı oluştur**

- **Metot oluşturma**

- **Sınıf oluşturma**

- **Yeni türü oluştur...**  (için bir sınıf, yapı, arabirim veya enum)

## <a name="generate-event-handlers"></a>Olay işleyicileri oluşturma

Kod Düzenleyicisi'nde IntelliSense olay alanlarına yöntemlerini (olay işleyicileri) bağlanmanıza yardımcı olabilir.

Yazdığınızda `+=` işleci .cs dosyasında bir olay alan sonra IntelliSense sizden basın seçeneğine **sekmesini** anahtarı. Olay işleme yöntemi işaret eden temsilci yeni bir örneğini ekler.

![Düğme otomatik kanca yukarı](../ide/media/vxautohookup.gif "vxAutoHookUp")

Basarsanız **sekmesini**, IntelliSense otomatik olarak sizin için deyim tamamlandıktan ve olay işleyici başvurusu Kod Düzenleyicisi'nde seçili metin olarak görüntüler. Otomatik olay bağlantı tamamlamak için IntelliSense basın ister **sekmesini** olay işleyicisi için boş bir saplama yeniden oluşturmak için anahtar.

![Olay işleyicisi oluşturmak](../ide/media/vxgenerateeventhandler.gif "vxGenerateEventHandler")

> [!NOTE]
> IntelliSense tarafından oluşturulan yeni bir temsilci varolan bir olay işleyicisinin başvuruyorsa, bu bilgileri ipucunda IntelliSense ile iletişim kurar. Bu başvuru daha sonra değiştirebilirsiniz; metin Kod düzenleyicisinde zaten seçilir. Aksi takdirde otomatik olay bağlantı bu noktada tamamlanır.

Basarsanız **sekmesini**, IntelliSense doğru imzalı bir yöntemini yerleştirir ve imleci, olay işleyicisi gövdesinde yerleştirir.

> [!NOTE]
> Kullanım **geriye Git** komutunu **Görünüm** menü (**Ctrl** + **-**) olayı geri dönmek için bağlantı açıklaması.

## <a name="see-also"></a>Ayrıca bkz.

[IntelliSense Kullanma](../ide/using-intellisense.md)  
[Visual Studio IDE](../ide/visual-studio-ide.md)