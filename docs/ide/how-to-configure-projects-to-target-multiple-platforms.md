---
title: 'Nasıl yapılır: projeleri hedef birden çok platform için yapılandırma'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio], targeting platforms
- platforms, changing target platforms
ms.assetid: affa2392-7aed-45ac-9ffa-1d8e0496d590
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cb194836f40ce599ee3509b11fc9849b6a7780ab
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-configure-projects-to-target-multiple-platforms"></a>Nasıl yapılır: projeleri hedef birden çok platform için yapılandırma

Visual Studio birkaç farklı CPU mimariyi ya da platformlar, aynı anda hedeflemek bir çözüm için bir yol sağlar. Bunlar ayarlanacak özellikler erişilir **Configuration Manager** iletişim kutusu.

## <a name="target-a-platform"></a>Hedef platform

**Configuration Manager** iletişim kutusu oluşturun ve çözüm ve proje düzeyi yapılandırmalar ve platformlar ayarlamanıza olanak tanır. Her çözüm düzeyi yapılandırmaları ve hedefleri birleşimi özellikleri arasında kolayca, örneğin, bir yayın yapılandırma geçiş hedefleyen olanak ilişkili benzersiz bir kümesi olabilir bir [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)] platform, yayın yapılandırma x x86 hedefleyen platform ve bir x86 hedefleyen bir hata ayıklama yapılandırmasını platform.

1.  Üzerinde **yapı** menüsünde tıklatın **Configuration Manager**.

2.  İçinde **etkin çözüm platformu kutusunu**, hedef çözümünüze istediğiniz ya da seçin platformu seçin  **\<yeni >** yeni bir platformu oluşturmak için. Visual Studio etkin platform olarak ayarlanmış olan platform hedeflemek için uygulamanızın derleme **Configuration Manager** iletişim kutusu.

## <a name="remove-a-platform"></a>Bir platform Kaldır

Bir platform için gerekli olduğunu fark ederseniz kullanarak kaldırabilirsiniz **Configuration Manager** iletişim kutusu. Bu, yapılandırma ve hedef birleşimi için yapılandırılan tüm çözüm ve proje ayarlarını kaldırır.

1.  Üzerinde **yapı** menüsünde tıklatın **Configuration Manager**.

2.  İçinde **etkin çözüm platformu kutusunu**seçin  **\<Düzenle >**. **Düzenle çözüm platformları** iletişim kutusu açılır.

3.  Kaldır öğesini tıklatıp istediğiniz platformu tıklatın **kaldırmak**.

## <a name="target-multiple-platforms-with-one-solution"></a>Hedef bir çözümü ile birden çok platform

Ayarlarını yapılandırma ve platform ayarları birleşimi göre değişebildiğinden, birden çok platformu hedefleyen bir çözümü oluşturan ayarlayabilirsiniz.

### <a name="to-target-multiple-platforms"></a>Hedef birden çok platform için

1.  Kullanım **Configuration Manager** en az iki Hedef platformlar için çözüm eklemek için.

2.  Öğesinden hedef platformu seçin **etkin çözüm platformu** listesi.

3.  Çözümü oluşturun.

### <a name="to-build-multiple-solution-configurations-at-once"></a>Aynı anda birden çok çözüm yapılandırmaları oluşturmak için

1.  Kullanım **Configuration Manager** en az iki Hedef platformlar için çözüm eklemek için.

2.  Kullanım **Toplu derleme** birkaç çözüm yapılandırmaları aynı anda oluşturmak için penceresi.

 İçin örneğin, ayarlar bir çözüm düzeyi platform olması mümkündür [!INCLUDE[vcprx64](../extensibility/internals/includes/vcprx64_md.md)], ve aynı platformu hedefleyen Bu çözüm içinde proje yok. Birden çok proje çözümünüzde, her farklı platformları hedefleme olması mümkündür. Bu durumlardan biri varsa, yeni bir yapılandırma Karışıklığı önlemek için açıklayıcı bir ad oluşturmanız önerilir.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: oluşturma ve düzenleme yapılandırmaları](../ide/how-to-create-and-edit-configurations.md)
- [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)
- [Derleme ve projeler ve çözümler Visual Studio'da Temizle](../ide/building-and-cleaning-projects-and-solutions-in-visual-studio.md)
