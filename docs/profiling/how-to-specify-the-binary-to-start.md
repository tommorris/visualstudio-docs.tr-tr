---
title: "Nasıl yapılır: başlatma için ikili dosya belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.itemlaunch
helpviewer_keywords:
- profiling tools, launching
- performance tools, launching
- performance sessions, launching
ms.assetid: ba77fcf4-8d78-49f1-b8f3-7dd0acf84306
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 363ab8f0967ec9a2f8dcdc4e9eb817586e513a8b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-specify-the-binary-to-start"></a>Nasıl yapılır: Başlatma için İkili Dosya Belirtme
Profil ikili dosyalarda, DLL'ler gibi bilgileri girmeniz gerekir  **\<hedef > özellik sayfaları** iletişim kutusu. Bu bilgiler, DLL projesi çağrı yapan uygulamanın bulabileceğiniz gösterir.  
  
 **Gereksinimler**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
### <a name="to-specify-the-executable-to-start"></a>Başlatmak için çalıştırılabilir dosyayı belirtmek için  
  
1.  İçinde **performans Gezgini**, ikili hedef sağ tıklayın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusu, tıklatın **başlatma** özellikleri.  
  
3.  Seçin **proje özelliklerini geçersiz kılma** onay kutusu.  
  
4.  İçinde **başlatmak için yürütülebilir** metin kutusunda, dosya konumunu belirtin.  
  
5.  İçinde **bağımsız değişkenleri** metin kutusunda, uygulamayı başlatmak için gerekli bağımsız değişkenleri belirtin.  
  
6.  İçinde **çalışma dizini** metin kutusunda, istediğiniz dizin konumunu belirtin.  
  
7.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)