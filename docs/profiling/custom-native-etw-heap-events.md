---
title: "Özel yerel ETW yığın olayları | Microsoft Docs"
ms.custom: 
ms.date: 02/24/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 668a6603-5082-4c78-98e6-f3dc871aa55b
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs: C++
ms.workload: cplusplus
ms.openlocfilehash: 7d55fdb061b9cb2fcd0497b7dde8e5c4255cf5e3
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="custom-native-etw-heap-events"></a>Özel yerel ETW yığın olayları

Visual Studio içeren çeşitli [profil oluşturma ve tanılama araçları](../profiling/profiling-tools.md), yerel bellek profil oluşturucu de dahil olmak üzere.  Bu profil oluşturucu kancalarını [ETW olayları](/windows-hardware/drivers/devtest/event-tracing-for-windows--etw-) yığın sağlayıcısından ve bellek nasıl olma analizini sağlar ayrılmış ve kullanılan.  Varsayılan olarak, bu araç yalnızca standart Windows yığınından yapılan ayırmaları çözümleyebilir ve bu yerel yığın dışında tüm ayırmaları gösterilmesi.

Çoğu durumda, kendi özel yığın kullanın ve standart yığın gelen ayırma yükünü önlemek istediğiniz vardır.  Örneğin, kullanabileceğinizi [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) büyük miktarda bellek uygulama veya oyun başlangıcında ayırın ve ardından bu liste içinde kendi blok yönetmek için.  Bu senaryoda, bellek Profil Oluşturucu aracı'nı yalnızca bu ilk ayırma ve değil bellek öbek içinde yapılan, özel yönetim görürsünüz.  Ancak, özel yerel yığın ETW sağlayıcısını kullanarak, standart öbek kuran ayırmaları hakkında bilmeniz aracı izin verebilirsiniz.

Örneğin, aşağıdaki gibi bir projede nerede `MemoryPool` özel bir yığın Windows yığında yalnızca tek bir ayırma görür:

```cpp
class Foo
{
public:
    int x, y;
};

...

// MemoryPool is a custom managed heap, which allocates 8192 bytes 
// on the standard Windows Heap named "Windows NT"
MemoryPool<Foo, 8192> mPool;

// the "allocate" method requests memory from the pool created above
// and is cast to an object of type Foo, shown above
Foo* pFoo1 = (Foo*)mPool.allocate();
Foo* pFoo2 = (Foo*)mPool.allocate();
Foo* pFoo3 = (Foo*)mPool.allocate();
```

Bir anlık görüntüden [bellek kullanımı](../profiling/memory-usage.md) özel yığın izleme yalnızca tek bir 8192 bayt ayırma ve havuz tarafından yapılan özel ayırmaları hiçbiri göstermeniz olmadan aracı:

![Windows yığın ayırma](media/heap-example-windows-heap.png)

Aşağıdaki adımları gerçekleştirerek, biz bizim Özel yığın bellek usgae izlemek için aynı bu aracı kullanabilirsiniz.

## <a name="how-to-use"></a>Nasıl kullanılır

Bu kitaplık kolayca C ve C++ içinde kullanılabilir.

1. Üstbilgi özel yığın ETW sağlayıcı için şunları içerir:

   ```cpp
   #include <VSCustomNativeHeapEtwProvider.h>
   ```

1. Ekleme `__declspec(allocator)` oluşturma öğesi için bir işaretçi yeni ayrılan yığın bellek döndürür, özel yığın Yöneticisi'nde herhangi bir işlev.  Bu oluşturma öğesi doğru döndürülen bellek türünü tanımlamak için aracı sağlar.  Örneğin:

   ```cpp
   __declspec(allocator) void *MyMalloc(size_t size);
   ```
   
   > [!NOTE]
   > Bu oluşturma öğesi derleyici, bu işlev bir ayırıcı çağrısı olduğunu söyler.  Her işlev çağrısı çıkış callsite adresini, çağrı yönerge boyutunu ve yeni nesne için yeni bir TypeID `S_HEAPALLOCSITE` simgesi.  Bir çağrı yığını atandığında, Windows bu bilgilerle ETW olayı yayma.  Dönüş adresi eşleştirmek için arama çağrı yığını bellek Profil Oluşturucu aracı anlatılmaktadır bir `S_HEAPALLOCSITE` sembol ve simge TypeID bilgileri ayırma çalışma zamanı tür görüntülemek için kullanılır.
   >
   > Benzer bir çağrı kısa, yani `(B*)(A*)MyMalloc(sizeof(B))` türü olarak aracında gösterecektir `B`değil `void` veya `A`.

1. C++ için oluşturma `VSHeapTracker::CHeapTracker` nesnesi, profil oluşturma aracı gösterecektir öbek için bir ad sağlar:

   ```cpp
   auto pHeapTracker = std::make_unique<VSHeapTracker::CHeapTracker>("MyCustomHeap");
   ```

   C kullanıyorsanız `OpenHeapTracker` yerine işlev.  Bu işlev, diğer izleme işlevleri çağırma için kullanacağı bir tanıtıcı döndürür:
  
   ```C
   VSHeapTrackerHandle hHeapTracker = OpenHeapTracker("MyHeap");
   ```

1. Özel işlevini kullanarak bellek ayırırken çağrısı `AllocateEvent` (C++) veya `VSHeapTrackerAllocateEvent` işaretçinin bellek ve ayırma izlemek için boyutuna geçirme (C) yöntemi:

   ```cpp
   pHeapTracker->AllocateEvent(memPtr, size);
   ```

   veya

   ```C
   VSHeapTrackerAllocateEvent(hHeapTracker, memPtr, size);
   ```

   > [!IMPORTANT]
   > Özel ayırıcısı işleviyle etiketlemek unutmayın `__declspec(allocator)` oluşturma öğesi açıklandığı önceki.

1. Özel işlevini kullanarak bellek ayırmayı kaldırma, çağrı `DeallocateEvent` (C++) veya `VSHeapTracerDeallocateEvent` işaretçinin bellek ayırmayı kaldırma izlemek için geçirme (C) işlevi:

   ```cpp
   pHeapTracker->DeallocateEvent(memPtr);
   ```

   veya:

   ```C
   VSHeapTrackerDeallocateEvent(hHeapTracker, memPtr);
   ```

1. Özel işlevini kullanarak bellek ayrılırken çağrısı `ReallocateEvent` (C++) veya `VSHeapReallocateEvent` (C) yöntemi, bir işaretçi geçirme yeni bellek, ayırma ve eski bellek için bir işaretçi boyutu:

   ```cpp
   pHeapTracker->ReallocateEvent(memPtrNew, size, memPtrOld);
   ```

   veya:

   ```C
   VSHeapTrackerReallocateEvent(hHeapTracker, memPtrNew, size, memPtrOld);
   ```

1. Son olarak, kapatmak ve c++ özel yığın İzleyici temizlemek için kullanmak `CHeapTracker` yıkıcı, elle veya standart ölçüm kuralları aracılığıyla veya `CloseHeapTracker` c: işlevi

   ```cpp
   delete pHeapTracker;
   ```

   veya:

   ```C
   CloseHeapTracker(hHeapTracker);
   ```

## <a name="tracking-memory-usage"></a>Bellek kullanımını izleme
Bu aramaları yerinde özel yığın kullanımınızı şimdi standart kullanarak izlenebilir **bellek kullanımı** Visual Studio'da aracı.  Bu aracın nasıl kullanılacağı hakkında daha fazla bilgi için lütfen bkz [bellek kullanımı](../profiling/memory-usage.md) belgeleri. Görüntülenen özel yığın kullanımınızı görmezsiniz sahip anlık görüntüleri, aksi takdirde yığın profil etkin emin olun. 

![Yığın profil oluşturma etkinleştir](media/heap-enable-heap.png)

İzleme, özel yığın görüntülemek için kullanın **yığın** açılır sağ üst köşesinde bulunan **anlık görüntü** görünümden değiştirmek için pencere *NT yığın* kendi öbek için daha önce adı.

![Yığın seçimi](media/heap-example-custom-heap.png)

Yukarıdaki kod örneğinde ile `MemoryPool` oluşturma bir `VSHeapTracker::CHeapTracker` nesnesi ve kendi `allocate` şimdi çağırma yöntemi `AllocateEvent` yöntemi, şimdi görebilirsiniz o özel ayırma sonucunu gösteren tüm türü 24 baytı toplamda 3 örnekleri `Foo`.

Varsayılan *NT yığın* yığın arar aynı şekilde bir önceki eklenmesi ile bizim `CHeapTracker` nesnesi.

![NT yığınla İzleyicisi](media/heap-example-windows-heap.png)

Standart Windows yığınla de bu aracı ana açıklanan, özel yığınındaki sızıntıları ve Bozulması arayın ve anlık görüntüleri karşılaştırması için kullanabileceğiniz gibi [bellek kullanımı](../profiling/memory-usage.md) belgeleri.

> [!TIP]
> Visual Studio de içeren bir **bellek kullanımı** içinde aracı **performans profili oluşturma** etkinleştirildiğinden araç takımı **hata ayıklama > Performans Profil Oluşturucu** menü seçeneğini veya **Alt + F2** klavye birleşimi.  Bu özellik, yığın izleme içermez ve burada açıklandığı gibi özel yığın görüntülenmez.  Yalnızca **tanılama araçları** ile etkin penceresini **hata ayıklama > Windows > tanılama araçları Göster** menüsünde veya **Ctrl + Alt + F2** birleşimi, klavye Bu işlevselliği içerir.

## <a name="see-also"></a>Ayrıca Bkz.
[Profil Araçları](../profiling/profiling-tools.md)  
[Bellek kullanımı](../profiling/memory-usage.md)
