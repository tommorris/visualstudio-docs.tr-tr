---
title: 'Nasıl yapılır: COM istemcilerinde ve sunucularında RPC hata ayıklamasını kullanarak hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.com
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- RPC (Remote Procedure Call), debugging COM clients and servers
- COM, debugging
- RPC (Remote Procedure Call)
- RPC (Remote Procedure Call), debugging
- COM clients, debugging
- COM servers, debugging
- out-of-process remote procedure call debugging
- remote debugging, RPC (Remote Procedure Call)
- in-process remote procedure call debugging
ms.assetid: 3e8526c8-43b5-4b87-8e0d-b22c24f0a3ea
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4fe212015b381a38ed1cf110189b6e4839fdf9f1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>Nasıl Yapılır: RPC Hata Ayıklamasını Kullanarak COM İstemcilerinde ve Sunucularda Hata Ayıklama
COM istemci/sunucu uygulamalarının hata ayıklamak için uzak yordam çağrısı (RPC) hata ayıklama'ı kullanabilirsiniz. RPC kullanmak için hata ayıklama etkinleştirmeniz gerekir. RPC etkin ayıklama, ne zaman, istemci, hata ayıklayıcı sunucu çağrısından adımla sunucuya ekler ve kendi kodda hata ayıklama olanak tanır. Hata ayıklayıcı eklendiğinde, tüm hata ayıklama özellikleri ile istemci ve sunucu işlemlerini kullanabilirsiniz.  
  
### <a name="to-enable-rpc-debugging"></a>RPC hata ayıklamasını etkinleştirmek için  
  
1.  Üzerinde **Araçları** menüsünde tıklatın **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusu, tıklatın **hata ayıklama** klasör.  
  
3.  Tıklatın **yerel** sayfası.  
  
4.  Seçin **RPC hata ayıklama** onay kutusu.  
  
    > [!NOTE]
    >  RPC çağrıları hata ayıklamak için Administrator veya Power User ayrıcalıkları olmalıdır.  
  
    > [!NOTE]
    >  Yalnızca yerel bir hata ayıklayıcısı uzak sunucuya eklenmişse Microsoft Windows Vista çalıştıran bir uzak sunucuya Adımlama RPC çalışır. Aksi takdirde, RPC çağrısı bir hata iletisi başarısız olur. Aksi takdirde RPC çağrısı tamamlanır ancak step INTO RPC çağrısı çalışmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM sunucusunda ve kapsayıcısında hata ayıklama](../debugger/com-server-and-container-debugging.md)  
 [Visual Studio'da hata ayıklamayı](../debugger/index.md) [özelliği turu hata ayıklayıcı](../debugger/debugger-feature-tour.md)