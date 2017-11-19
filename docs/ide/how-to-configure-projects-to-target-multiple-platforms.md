---
title: "Nasıl yapılır: projeleri hedef birden çok platform için yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], targeting platforms
- platforms, changing target platforms
ms.assetid: affa2392-7aed-45ac-9ffa-1d8e0496d590
caps.latest.revision: "9"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6f862319d29502f1e3e242990072fbe0d2410fab
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-configure-projects-to-target-multiple-platforms"></a>Nasıl Yapılır: Projeleri Hedef Birden Çok Platform İçin Yapılandırma
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]birkaç farklı CPU mimariyi ya da platformlar, aynı anda hedeflemek bir çözüm için bir yol sağlar. Bunlar ayarlanacak özellikler erişilir **Configuration Manager** iletişim kutusu.  
  
## <a name="targeting-a-platform"></a>Bir Platform desteği  
 **Configuration Manager** iletişim kutusu oluşturun ve çözüm ve proje düzeyi yapılandırmalar ve platformlar ayarlamanıza olanak tanır. Her çözüm düzeyi yapılandırmaları ve hedefleri birleşimi özellikleri arasında kolayca, örneğin, bir yayın yapılandırma geçiş hedefleyen olanak ilişkili benzersiz bir kümesi olabilir bir [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)] platform, yayın yapılandırma x x86 hedefleyen platform ve bir x86 hedefleyen bir hata ayıklama yapılandırmasını platform.  
  
#### <a name="to-set-your-configuration-to-target-a-different-platform"></a>Farklı bir platform hedeflemek için yapılandırmayı ayarlamak için  
  
1.  Üzerinde **yapı** menüsünde tıklatın **Configuration Manager**.  
  
2.  İçinde **etkin çözüm platformu kutusunu**, hedef çözümünüze istediğiniz ya da seçin platformu seçin  **\<yeni >** yeni bir platformu oluşturmak için. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Etkin platform olarak ayarlanmış olan platform hedeflemek için uygulamanızın derlenir **Configuration Manager** iletişim kutusu.  
  
## <a name="removing-a-platform"></a>Bir Platform kaldırma  
 Bir platform için gerekli olduğunu fark ederseniz, Configuration Manager iletişim kutusunu kullanarak kaldırabilirsiniz. Bu, yapılandırma ve hedef birleşimi için yapılandırılan tüm çözüm ve proje ayarlarını kaldırır.  
  
#### <a name="to-remove-a-platform"></a>Bir platform kaldırmak için  
  
1.  Üzerinde **yapı** menüsünde tıklatın **Configuration Manager**.  
  
2.  İçinde **etkin çözüm platformu kutusunu**seçin  **\<Düzenle >**. **Düzenle çözüm platformları** iletişim kutusu açılır.  
  
3.  Kaldır öğesini tıklatıp istediğiniz platformu tıklatın **kaldırmak**.  
  
## <a name="targeting-multiple-platforms-with-one-solution"></a>Bir çözümü ile birden çok platformu hedefleme  
 Ayarlarını yapılandırma ve platform ayarları birleşimi göre değişebildiğinden, birden çok platformu hedefleyen bir çözümü oluşturan ayarlayabilirsiniz.  
  
#### <a name="to-target-multiple-platforms"></a>Hedef birden çok platform için  
  
1.  Kullanım **Configuration Manager** en az iki Hedef platformlar için çözüm eklemek için.  
  
2.  Öğesinden hedef platformu seçin **etkin çözüm platformu** listesi.  
  
3.  Çözümü oluşturun.  
  
#### <a name="to-build-multiple-solution-configurations-at-once"></a>Aynı anda birden çok çözüm yapılandırmaları oluşturmak için  
  
1.  Kullanım **Configuration Manager** en az iki Hedef platformlar için çözüm eklemek için.  
  
2.  Kullanım **Toplu derleme** birkaç çözüm yapılandırmaları aynı anda oluşturmak için penceresi.  
  
 İçin örneğin, ayarlar bir çözüm düzeyi platform olması mümkündür [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)], ve aynı platformu hedefleyen Bu çözüm içinde proje yok. Birden çok proje çözümünüzde, her farklı platformları hedefleme olması mümkündür. Bu durumlardan biri varsa, yeni bir yapılandırma Karışıklığı önlemek için açıklayıcı bir ad oluşturmanız önerilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md)   
 [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
 [Projeler ve çözümler Visual Studio'da oluşturma ve temizleme](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)