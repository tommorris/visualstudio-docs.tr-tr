---
title: 'CA2003: Lifleri iş parçacığı olarak görmeyin'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 799d0d04f8620c07be0583869eeba5dd760c7f70
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915545"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Lifleri iş parçacığı olarak görmeyin
|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Kategori|Microsoft.Reliability|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Yönetilen iş parçacığı bir Win32 iş parçacığı kabul edilir.

## <a name="rule-description"></a>Kural Tanımı
 Yönetilen iş parçacığı bir Win32 iş parçacığı olduğunu varsayalım değil. Bu, bir fiber olur. Ortak dil çalışma zamanı (CLR), SQL tarafından sahip olunan gerçek iş parçacıkları bağlamında lifleri olarak yönetilen iş parçacığı çalıştırılır. Bu iş parçacıkları SQL Server işleminde appdomains oluşturuyor ve hatta veritabanları arasında paylaşılabilir. Yönetilen iş parçacığı yerel depolama çalışır kullanarak, ancak değil yönetilmeyen iş parçacığı yerel depolama kullanın veya kodunuzu geçerli işletim sistemi iş parçacığı üzerinde yeniden çalıştırılır varsayalım. İş parçacığı yerel gibi ayarlarını değiştirmeyin. Kilit girer iş parçacığı kilidi çıkmalı gerektirdiğinden CreateCriticalSection ya da P/Invoke aracılığıyla CreateMutex çağırmayın. Lifleri kullandığınızda, bu durum olmayacağından, Win32 kritik bölümler ve zaman uyumu sağlayıcılar SQL'de gereksiz olacaktır. Yönetilen bir System.Thread nesne üzerinde durumunun en güvenli bir şekilde kullanabilirsiniz. Yönetilen iş parçacığı yerel depolaması ve geçerli kullanıcı arabirimi (UI) kültürü iş parçacığının buna dahildir. Ancak, programlama modeli nedeni, SQL kullandığınızda geçerli bir iş parçacığı kültürünü değiştirmesi mümkün olmayacaktır; Bu yeni bir izin uygulanır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 İş parçacığı kullanımınızı inceleyin ve kodunuzu uygun şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kural engelleme.