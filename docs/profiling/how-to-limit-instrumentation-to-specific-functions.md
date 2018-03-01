---
title: "Nasıl yapılır: belirli işlevler için araçları sınırlama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance tools, limiting instrumentation to functions
ms.assetid: bd98d6bf-2560-4eba-b063-2facb09f87c4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 69cc476dc43562e5226ebd6564dfb2733f1d57ae
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-limit-instrumentation-to-specific-functions"></a>Nasıl yapılır: Belirli İşlevler için İzlemeyi Sınırlama
Bir veya daha fazla işlevler için araçları ve veri toplama seçeneklerini ayarlayarak sınırlayabilirsiniz **Gelişmiş** sayfasında **Performans oturumunu** veya hedef ikili özellik sayfaları:  
  
-   Performans oturumu özellik sayfasında işlevleri belirtirseniz, yalnızca bu işlevleri tüm izleme eklenmiş ikili dosyalar oturumunun içinde belgelenir.  
  
-   İkili bir hedef özellik sayfasında işlevleri belirtirseniz, belirli ikili izlenmiş yalnızca bu işlevleri, bir seçenektir. Diğer ikili dosyaları performansını işlevlerde her zamanki gibi donatılmıştır.  
  
 Yalnızca izleme profili oluşturma yöntemi seçildiğinde bu şekilde veri toplama sınırlaması desteklenir.  
  
> [!NOTE]
>  Aynı zamanda **Gelişmiş** sayfasında **Performans oturumunu** profil oluşturma araçları için kullanılabilir diğer seçenekleri ayarlamak için özellik sayfaları [Vsınstr](../profiling/vsinstr.md) komut satırı izleme aracı.  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-performance-session"></a>Bir performans oturumunda belirli işlevler için araçları sınırlamak için  
  
1.  İçinde **performans Gezgini**, oturum adına sağ tıklayın ve ardından **özellikleri**.  
  
     **Özellik sayfaları** iletişim kutusu görüntülenir.  
  
2.  Üzerinde **özellik sayfaları** iletişim kutusu, tıklatın **Gelişmiş**.  
  
3.  İçinde **ek izleme seçeneklerini** metin kutusunda, istediğiniz işlevleri adını yazmanız için aşağıdaki sözdizimini kullanın gereç:  
  
     **/ içerir:** `FuncSpec` **[;** `FuncSpec` **]**`...`  
  
     `FuncSpec`ad alanı ve işlev adıdır. Biçime sahip `Namespace` **::**`FunctionName`. Birden çok işlevleri ayırmak için noktalı virgül kullanın. Bir yıldız işareti kullanın (\*) bir veya daha fazla karakter için joker karakter belirtmek için. Örneğin, **/ içerir: MyNS::\***  MyNS ad alanındaki tüm işlevleri belirtir.  
  
    > [!NOTE]
    >  Bir ikili işlevlerde listelemek için profil oluşturma araçları yükleme dizininde bir komut istemi penceresi açın (genellikle \Team Tools\Performance araçları dizini altında [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] yükleme dizini) ve ardından **vsınstr / DumpFuncs**  
  
### <a name="to-limit-instrumentation-to-specific-functions-in-a-binary"></a>Bir ikili dosyada belirli işlevlere sınırlamak için  
  
1.  İçinde **performans Gezgini**, ikili adı bulun **hedefleri** Performans oturumunu düğümünün.  
  
2.  İkili adına sağ tıklayın ve ardından **özellikleri**.  
  
     **Özellik sayfaları** iletişim kutusu görüntülenir.  
  
3.  Üzerinde **özellik sayfaları** iletişim kutusu, tıklatın **Gelişmiş**.  
  
4.  İçinde **ek izleme seçeneklerini** metin kutusunda, istediğiniz işlevleri adını yazmanız için aşağıdaki sözdizimini kullanın gereç:  
  
     **/ içerir:** `FuncSpec` **[;** `FuncSpec` **]**`...`  
  
     `FuncSpec`ad alanı ve işlev adıdır. Biçime sahip `Namespace` **::**`FunctionName`. Birden çok işlevleri ayırmak için noktalı virgül kullanın. Bir yıldız işareti kullanın (\*) bir veya daha fazla karakter için joker karakter belirtmek için. Örneğin, **/ içerir: MyNS::\***  MyNS ad alanındaki tüm işlevleri belirtir.  
  
    > [!NOTE]
    >  Bir ikili işlevlerde listelemek için profil oluşturma araçları yükleme dizininde bir komut istemi penceresi açın (genellikle \Team Tools\Performance araçları dizini altında [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] yükleme dizini) ve ardından **vsınstr / DumpFuncs**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri toplama denetimi](../profiling/controlling-data-collection.md)   
 [Nasıl yapılır: belirli DLL'ler için araçları sınırlama](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)   
 [Nasıl yapılır: ek izleme seçeneklerini belirtme](../profiling/how-to-specify-additional-instrumentation-options.md)