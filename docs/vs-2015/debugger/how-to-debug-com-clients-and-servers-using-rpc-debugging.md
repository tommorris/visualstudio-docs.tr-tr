---
title: 'Nasıl yapılır: RPC hata ayıklamasını kullanarak COM istemcilerinde ve sunucularda hata ayıklama | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.com
dev_langs:
- FSharp
- VB
- CSharp
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
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b64c01f502dbe4194561776f121e21475d61d43
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673974"
---
# <a name="how-to-debug-com-clients-and-servers-using-rpc-debugging"></a>Nasıl Yapılır: RPC Hata Ayıklamasını Kullanarak COM İstemcilerinde ve Sunucularda Hata Ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: hata ayıklama COM istemcilerinde ve sunucularında kullanarak RPC hata ayıklama](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-com-clients-and-servers-using-rpc-debugging).  
  
COM istemci/sunucu uygulamalarında hata ayıklamak için uzak yordam çağrısı (RPC) hata ayıklama'ı kullanabilirsiniz. RPC kullanmak için hata ayıklamayı etkinleştirmeniz gerekir. RPC hata ayıklama etkin, hata ayıklayıcı istemciden gelen sunucu çağrı geçtiğinizde sunucuya ekler ve kendi kod hatalarını ayıklamanıza olanak tanır. Hata ayıklayıcı eklendiğinde, tüm hata ayıklama özellikleri ile istemci ve sunucu işlemlerini kullanabilirsiniz.  
  
### <a name="to-enable-rpc-debugging"></a>RPC hata ayıklamasını etkinleştirmek için  
  
1.  Üzerinde **Araçları** menüsünü tıklatın **seçenekleri**.  
  
2.  İçinde **seçenekleri** iletişim kutusu, tıklayın **hata ayıklama** klasör.  
  
3.  Tıklayın **yerel** sayfası.  
  
4.  Seçin **RPC hata ayıklama** onay kutusu.  
  
    > [!NOTE]
    >  RPC çağrıları hata ayıklamak için yönetici veya İleri kullanıcı ayrıcalıkları olmalıdır.  
  
    > [!NOTE]
    >  Yalnızca yerel bir hata ayıklayıcı uzak sunucuya bağlıysa, Microsoft Windows Vista çalıştıran bir uzak sunucuya Adımlama RPC çalışır. Aksi takdirde bir hata iletisi öykünücüsüne yönelik RPC çağrısı başarısız olur. Aksi takdirde öykünücüsüne yönelik RPC çağrısı tamamlanır, ancak step INTO öykünücüsüne yönelik RPC çağrısı çalışmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COM sunucusunda ve kapsayıcısında hata ayıklama](../debugger/com-server-and-container-debugging.md)   
 [Visual Studio’da hata ayıklama](../debugger/debugging-in-visual-studio.md)



