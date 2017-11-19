---
title: "DSL tanımları için uzantılar ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: "6"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: f335db9f22392c4d0293a51111efff88c25c3145
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2017
---
# <a name="adding-extensions-to-dsl-definitions"></a>DSL Tanımlarına Uzantılar Ekleme
DSL tanımı uzantısı, bir etki alanına özgü dil (DSL) uzantıları paketi oluşturmanıza olanak sağlar. Bir Visual Studio Tümleştirme Uzantısı'na (VSIX) bulunur, DSL uzantısı bir kullanıcının bilgisayarında DSL aynı şekilde yüklenebilir. Ek özellikler dinamik olarak etkin ve çalışma zamanında devre dışı. DSL'ler açıkça uzantısı için tasarlanmış gerekmez ve uzantıları daha sonra veya üçüncü taraflar tarafından Genişletilmiş DSL değiştirmeden tasarlanabilir.  
  
 Ek özellikler şunları içerebilir:  
  
-   Model ve sunu öğelerin özellikleri  
  
-   Şekilleri ve bağlayıcıları için dekoratörler  
  
-   Sınıfları, ilişkileri, şekilleri ve bağlayıcıları  
  
-   Doğrulama kısıtlamaları  
  
-   Araç kutusu öğelerini ve sekmeleri  
  
 Genişletilmiş DSL kullanıcısı oluşturun ve ek özellikler örneklerini içeren bir model kaydedin ve bunlar uygun uzantısı yüklü diğer kullanıcılar tarafından okunabilir. Uzantısı yüklü olmayan kullanıcılar ek özellikleri kullanamaz, ancak güncelleştirin ve ek özellikler kaybetmeden bir modeli kaydedin.  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Ayrıca Bkz.  
 [İlgili blog gönderileri](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
