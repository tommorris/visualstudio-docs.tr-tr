---
title: ".NET için Visual Studio veri araçları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3175080-1dfb-4ab8-a460-92dadbb844b4
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 6b48b16d33c62c2d0ca96eb1d55ce22682458029
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2017
---
# <a name="visual-studio-data-tools-for-net"></a>.NET için Visual Studio veri araçları
Visual Studio ve .NET Framework birlikte kapsamlı API ve araç veritabanlarına bağlanma, veri bellekte modelleme ve kullanıcı arabiriminde verileri görüntüleme için desteği sağlar. Veri erişimi işlevselliği sağlamak .NET Framework sınıfları olarak da bilinir [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx). Visual Studio'da tooling verilerin ADO.NET başlangıçta öncelikle ilişkisel veritabanları ve XML desteklemek üzere tasarlanmıştır. Bugünlerde, birçok NoSQL veritabanı satıcılarının ya da üçüncü tarafların ADO.NET sağlayıcıları sunar.  
  
[.NET core](https://www.dotnetfoundation.org/netcore) ADO.NET veri kümelerini ve ilgili türleri dışında destekler. .NET Core hedefleme ve bir nesne ilişkisel eşleme (ORM) katmanı gerektiren kullanın [Entity Framework Çekirdek](https://docs.microsoft.com/ef/core/).  
  
Aşağıdaki diyagramda, Basitleştirilmiş bir görünümü temel mimari gösterilmektedir:  
  
![ADO.NET mimarisi](../data-tools/media/raddata-ado-net-architecture-diagram.png "raddata ADO.NET mimarisi diyagramı")  
  
Normal iş akışı şudur:  
  
1.  Bir geliştirme veya test veritabanının yerel makinenize yükleyin. Bkz: [veritabanı sistemleri, araçları ve örnek yükleme](../data-tools/installing-database-systems-tools-and-samples.md). Bir Azure veri hizmeti kullanıyorsanız, bu adım gerekli değildir.  
  
2.  Visual Studio'da test bağlantısı veritabanı (veya hizmet veya yerel dosya). Bkz: [yeni bağlantılar eklemek](../data-tools/add-new-connections.md).  
  
3.  (İsteğe bağlı) Araçları oluşturmak ve yeni bir model yapılandırmak için kullanın. Entity Framework temel alınarak modelleri yeni uygulamalar için varsayılan öneri ' dir. Modelin hangi birini kullanın, uygulama ile etkileşime giren veri kaynağıdır. Model, veritabanı veya hizmet ve uygulama arasında mantıksal olarak bulunur.  Bkz: [yeni veri kaynakları ekleyin](../data-tools/add-new-data-sources.md).  
  
4.  Veri kaynağı'ndan sürükleyin **veri kaynakları** verileri, belirttiğiniz şekilde kullanıcıya görüntüler veri bağlama kodunu oluşturmak için bir Windows Forms, ASP.NET veya Windows Presentation Foundation tasarım yüzeyine penceresi. Bkz: [Visual Studio'da verilere denetimler bağlama](../data-tools/bind-controls-to-data-in-visual-studio.md).  
  
5.  İş kuralları, arama ve veri doğrulama gibi ya da, temel alınan veritabanı ortaya çıkaran özel işlevsellikten yararlanmak için herhangi bir şeyi özel kodu ekleyin.  
  
3. adıma geçin ve sorunu komutları doğrudan bir model kullanmak yerine bir veritabanı için bir .NET uygulaması program. Bu durumda, ilgili belgelerine burada bulabilirsiniz: [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx). Hala tasarımcıların ve veri kaynağı Yapılandırma Sihirbazı bellek ve ardından bu nesnelere veri bağlama kullanıcı Arabirimi denetimlerini kendi nesneleri doldurmak olduğunda veri bağlama kodu oluşturmak için kullanabileceğinizi unutmayın.
  
## <a name="see-also"></a>Ayrıca bkz.
[Visual Studio'da veri erişimi](../data-tools/accessing-data-in-visual-studio.md)