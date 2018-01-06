---
title: "Nasıl yapılır: derleme aynı anda birden çok yapılandırmaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba830937-3317-4674-8cc2-c0cd565603c5
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 86c0a9fbbfe7e4b0b38b0286cf10f06dd7eec89c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-multiple-configurations-simultaneously"></a>Nasıl yapılır: Aynı Anda Birden Fazla Yapılandırma Derleme
Kullanarak birden çok projelerle veya hatta tüm yapı yapılandırmalarına aynı anda birçok türleri oluşturabilirsiniz **Toplu derleme** iletişim kutusu. Ancak, aynı anda birden çok derleme yapılandırmaları projelerinde aşağıdaki türlerini oluşturulamıyor:  
  
1.  [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]uygulamalar JavaScript kullanan Windows için oluşturulmuştur.  
  
2.  Tüm Visual Basic projeleri.  
  
 Derleme yapılandırmaları hakkında daha fazla bilgi için bkz: [derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md).  
  
### <a name="to-build-a-project-in-multiple-build-configurations"></a>Birden çok derleme yapılandırmaları bir proje oluşturmak için  
  
1.  Menü çubuğunda seçin **yapı**, **Toplu derleme**.  
  
2.  İçinde **yapı** onay kutularını bir projeyi oluşturmak istediğiniz yapılandırmaları için sütun seçin.  
  
    > [!TIP]
    >  Düzenlemek veya bir yapı yapılandırması için bir çözüm oluşturmak için Seç **yapı**, **Configuration Manager** açmak için menü çubuğunda **Configuration Manager** iletişim kutusu. Bir çözüm için bir yapı yapılandırma düzenledikten sonra Seç **yeniden** düğmesini **Toplu derleme** derleme Çözümdeki projeler için yapılandırmaları tüm güncelleştirmek için iletişim kutusu.  
  
3.  Seçin **yapı** veya **yeniden** belirttiğiniz yapılandırmalarla Projeyi derlemek için düğmeler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: yapılandırmaları oluşturma ve düzenleme](../ide/how-to-create-and-edit-configurations.md)   
 [Derleme yapılandırmalarını anlama](../ide/understanding-build-configurations.md)   
 [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md)