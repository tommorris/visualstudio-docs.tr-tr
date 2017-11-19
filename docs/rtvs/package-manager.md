---
title: "Paket Yöneticisi'nde R için Visual Studio Araçları | Microsoft Docs"
ms.custom: 
ms.date: 06/29/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-r
ms.devlang: r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93accb9a-1ef8-4806-baa4-02477c2d7ef0
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.openlocfilehash: 87f4c97941a55bd378a72681200748f28e8dd236
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="package-manager"></a>Paket Yöneticisi

R araçları Visual Studio (RTVS) Paket Yöneticisi için bir kullanıcı Arabirimi R paketlerini yönetmek için kullanılır. Açmak için seçin **R Araçlar > Windows > paketleri** veya Ctrl + 7 tuşlarına basabilirsiniz.

Paket Yöneticisi üç sekme bulunur. Her sekme sol tarafta ilgili paketlerin listesini görüntüler ve diğer ilgili bilgileri dahil paketin sürüm, açıklama, lisans, sağdaki seçilen paket için belirli Ayrıntılar konumu ve bağlantıları yükleyin. Sağ üst arama kutusuna, listeyi filtrelemek olanak tanır.

> [!Tip]
> Sekmeler arasında geçiş yapma gibi arama kutusuna terim yürürlükte kalır.

- **Kullanılabilir** paketleri yüklemek için Gözat sağlar. Paket zaten yüklediyseniz, **yükleme** sağdaki düğme değişiklikler **kaldırma**.

    ![Visual Studio Paket Yöneticisi için R araçlarında kullanılabilir paketler sekmesi](media/package-manager-available.png)

- **Yüklü** tüm yüklü ve yüklenen paketler gösterir. Bir paket yanında yeşil bir nokta R oturumuna yüklendiğini gösterir. Kırmızı X simgesi sol listesinde veya **kaldırma** sağdaki düğme, paketi kaldırmak için kullanılabilir. Yüklü bir paketle daha yeni bir sürümü kullanılabilir durumda, Yukarı Ok paket sağındaki mavi bir güncelleştirme gerçekleştirir.

    ![Visual Studio Paket Yöneticisi için R araçlarında Paketleri sekmesi yüklü](media/package-manager-installed.png)

- **Yüklenen** R oturumuna da yeşil bir nokta ile görünür yüklü olan paketleri görüntüler. Ayrıca, kaldırma ve güncelleştirme paketleri burada.

    ![Visual Studio Paket Yöneticisi için R araçları paketleri sekmesinde yüklendi](media/package-manager-loaded.png)

## <a name="package-locations"></a>Paket konumları

Paketleri aşağıdaki konumlara yüklenir:

- RTVS ile birlikte çekirdek paketleri yüklenir`C:\Program Files\Microsoft\R Client\R_SERVER\library`
- Ek paketler için yüklenir`%userprofile%\Documents\R\win-library\3.3`
