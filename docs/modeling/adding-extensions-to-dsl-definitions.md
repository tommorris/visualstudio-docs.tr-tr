---
title: "DSL tanımları için uzantılar ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b3abe11e747db81579fb3851a1d05562d3f2fd11
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
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
