---
title: 'Nasıl yapılır: bir derlemeden projeleri hariç tutma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 17a837ca-5db9-46cd-b5a7-b14ad1d2c47d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9fcfe1170c3b5503baa1515227a954080d10ed09
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-exclude-projects-from-a-build"></a>Nasıl yapılır: Derlemeden Projeleri Hariç Tutma
İçerdiği tüm projeleri oluşturmadan bir çözüm oluşturabilirsiniz. Örneğin, yapıyı durduran bir proje hariç. Ardından, araştırmanız sonra projeyi ve adres sorunları oluşturabilir.  
  
 Aşağıdaki yaklaşımlardan gerçekleştirerek bir proje dışlayabilirsiniz:  
  
-   Geçici olarak, etkin çözüm yapılandırmasından kaldırılıyor.  
  
-   Bir çözüm yapılandırması oluşturma proje içermez.  
  
 Daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
### <a name="to-temporarily-remove-a-project-from-the-active-solution-configuration"></a>Geçici olarak bir proje etkin çözüm yapılandırmasından kaldırmak için  
  
1.  Menü çubuğunda seçin **yapı**, **Configuration Manager**.  
  
2.  İçinde **proje bağlamları** tablo, derlemeden hariç tutmak istediğiniz projeyi bulun.  
  
3.  İçinde **yapı** sütunu proje için onay kutusunu temizleyin.  
  
4.  Seçin **Kapat** düğmesine tıklayın ve ardından çözümü yeniden derleyin.  
  
### <a name="to-create-a-solution-configuration-that-excludes-a-project"></a>Bir proje dışlar bir çözüm yapılandırması oluşturmak için  
  
1.  Menü çubuğunda seçin **yapı**, **Configuration Manager**.  
  
2.  İçinde **etkin çözüm yapılandırması** listesinde, seçin  **\<yeni >**.  
  
3.  İçinde **adı** kutusunda, çözüm yapılandırması için bir ad girin.  
  
4.  İçinde **ayarları kopyalamak** listesinde, yeni yapılandırma temel almak istediğiniz çözüm yapılandırması seçin (örneğin, **hata ayıklama**) ve ardından **Tamam** düğmesi .  
  
5.  İçinde **Configuration Manager** iletişim kutusu, onay kutusunu temizleyin **yapı** sütunu dışlayın ve ardından istediğiniz proje için **Kapat** düğmesi.  
  
6.  Üzerinde **standart** araç, yeni çözüm yapılandırma etkin yapılandırmasında olduğundan emin olun **çözüm yapılandırmaları** kutusu.  
  
7.  Menü çubuğunda seçin **yapı**, **çözümü yeniden derle**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
 [Nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md)   
 [Nasıl yapılır: Aynı Anda Birden Fazla Yapılandırma Derleme](../ide/how-to-build-multiple-configurations-simultaneously.md)