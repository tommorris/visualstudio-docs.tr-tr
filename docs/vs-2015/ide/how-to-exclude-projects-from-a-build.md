---
title: 'Nasıl yapılır: derlemeden projeleri hariç tutma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 569f0db1294bd7df2451c4ec496dc5064b122b73
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695866"
---
# <a name="how-to-exclude-projects-from-a-build"></a>Nasıl yapılır: Derlemeden Projeleri Hariç Tutma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: derlemeden projeleri hariç](https://docs.microsoft.com/visualstudio/ide/how-to-exclude-projects-from-a-build).  
  
İçerdiği tüm projeleri oluşturmaya gerek kalmadan, bir çözüm oluşturabilirsiniz. Örneğin, yapı sonları bir proje hariç. Sorunları araştırmak, sonra projeyi ve adresi ardından oluşturabilirsiniz.  
  
 Bir proje, aşağıdaki yaklaşımlardan yararlanarak dışlayabilirsiniz:  
  
-   Etkin çözüm yapılandırmasını geçici olarak kaldırma.  
  
-   Bir çözüm yapılandırması oluşturma, proje içermez.  
  
 Daha fazla bilgi için [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
### <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Bir projenin etkin çözüm yapılandırmasını geçici olarak kaldırmak için  
  
1.  Menü çubuğunda, **derleme**, **Configuration Manager**.  
  
2.  İçinde **proje bağlamları** tablo, derlemeden hariç tutmak istediğiniz proje bulun.  
  
3.  İçinde **derleme** sütun proje için onay kutusunu temizleyin.  
  
4.  Seçin **Kapat** düğmesini ve ardından çözümü yeniden oluşturun.  
  
### <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Bir proje dışlayan bir çözüm yapılandırmasını oluşturmak için  
  
1.  Menü çubuğunda, **derleme**, **Configuration Manager**.  
  
2.  İçinde **etkin çözüm yapılandırması** listesinde  **\<yeni >**.  
  
3.  İçinde **adı** kutusuna, çözüm yapılandırması için bir ad girin.  
  
4.  İçinde **Ayarları Şuradan Kopyala** listesinde, yeni yapılandırmayı temel almak istediğiniz çözüm yapılandırması seçin (örneğin, **hata ayıklama**) ve ardından **Tamam** düğmesi .  
  
5.  İçinde **Configuration Manager** iletişim kutusu, onay kutusunu temizleyin **derleme** sütununu hariç tutun ve ardından istediğiniz proje için **Kapat** düğmesi.  
  
6.  Üzerinde **standart** araç, yeni çözüm yapılandırması etkin yapılandırmada olduğundan emin olun **çözüm yapılandırmaları** kutusu.  
  
7.  Menü çubuğunda, **derleme**, **çözümü yeniden derle**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
 [Nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md)   
 [Nasıl yapılır: Aynı Anda Birden Fazla Yapılandırma Derleme](../ide/how-to-build-multiple-configurations-simultaneously.md)



