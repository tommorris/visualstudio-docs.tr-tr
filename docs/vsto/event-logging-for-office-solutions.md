---
title: Office çözümleri için olay günlüğü
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], event viewer
- ClickOnce deployment [Office development in Visual Studio], event viewer
- deploying applications [Office development in Visual Studio], event viewer
- Office development in Visual Studio, event viewer
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ef1db4f88e13575f77a88d0e2ceee7ef0621b202
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="event-logging-for-office-solutions"></a>Office çözümleri için olay günlüğü
  Tarafından yakalanan özel durum iletilerini görmek için Windows Olay Görüntüleyicisi'ni kullanabilirsiniz [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] yüklediğinizde veya Office çözümleri kaldırın. Bu olay günlükçüsü iletilerden yükleme ve dağıtım sorunlarını gidermek için kullanabilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="read-the-event-log"></a>Olay günlüğünü okuma  
 Açık **Olay Görüntüleyicisi'ni** ve görmek istediğiniz olaylar için filtre.  
  
### <a name="to-read-the-event-log-in-windows-server-2003-and-windows-xp"></a>Windows Server 2003 ve Windows XP'de olay günlüğünü okumak için  
  
1.  Denetim Masası'nda açmak **Yönetimsel Araçlar**.  
  
2.  Başlat **Olay Görüntüleyicisi'ni**.  
  
3.  Olay günlükleri listesinde seçin **uygulama**.  
  
4.  Üzerinde **Görünüm** menüsünde tıklatın **filtre**.  
  
5.  İçinde **olay kaynağı** listesinde **VSTO 4.0**.  
  
6.  Yükleme olayları için de **olay kimliği** kutusuna **4096**.  
  
7.  Tıklatın **Tamam** filtrelenmiş görmek için.  
  
#### <a name="to-read-the-event-log-in-windows-7-windows-vista-and-windows-server-2008"></a>Windows 7, Windows Vista ve Windows Server 2008'de olay günlüğünü okumak için  
  
1.  Denetim Masası'nda açmak **Yönetimsel Araçlar**.  
  
2.  Başlat **Olay Görüntüleyicisi'ni**.  
  
3.  Genişletme **Windows Günlükleri**.  
  
4.  Olay günlükleri listesinde seçin **uygulama**.  
  
5.  Üzerinde **eylem** menüsünde tıklatın **geçerli günlüğü Filtrele**.  
  
6.  İçinde **olay kaynağı** listesinde **VSTO 4.0**.  
  
7.  Yükleme olayları için de **olay kimliği** kutusuna **4096**.  
  
8.  Tıklatın **Tamam** filtrelenmiş görmek için.  
  
 Olay Görüntüleyicisi'ni aşağıdaki bilgileri içerir:  
  
-   Çözüm için dağıtım bildirimi konumu.  
  
-   Özel durum ve hata nedenini açıklayan ileti.  
  
 Bu özel durum iletileri, güvenilmeyen bir sertifika, güvenilmeyen dosya konumu veya geçersiz dağıtım bildirimi gibi bir yükleme sorunu nedenini belirlemenize yardımcı olabilir.  
  
 Office çözümünü kaldırıldıktan sonra özel durum iletilerini olay günlüğüne kalır.  
  
 Göster veya Office çözümü çalışırken özel durum iletilerini günlüğe kaydetmek için bkz: [hata ayıklama Office projeleri](../vsto/debugging-office-projects.md) ve [hata ayıklama Office projeleri](../vsto/debugging-office-projects.md).  
  
### <a name="localization"></a>Yerelleştirme  
 Özel durum iletisi dil Office çalışma zamanı dil için Visual Studio Araçları tarafından belirlenir. Örneğin, son kullanıcının bilgisayarına yüklü Japonca dil paketi varsa, özel durum iletisi Japonca olay günlüğüne yazılır.  
  
## <a name="disable-the-event-logger"></a>Olay günlüğü devre dışı bırak  
 Yükleme veya Office çözümlerini kaldırma durumunda varsayılan olarak, olay günlükçüsü etkinleştirilir. Olay günlükçüsü VSTO_EVENTLOGDISABLED ortam değişkeni "1" (bir) ayarlayarak devre dışı bırakabilirsiniz.  
  
### <a name="to-disable-the-event-log"></a>Olay günlüğünü devre dışı bırakmak için  
  
1.  Denetim Masası'nda açmak **sistem**.  
  
2.  Üzerinde **Gelişmiş** sekmesini tıklatın, **ortam değişkenleri**.  
  
3.  İçinde **sistem değişkenleri** bölmesinde tıklatın **yeni**.  
  
4.  İçinde **yeni sistem değişkeni** iletişim kutusuna **VSTO_EVENTLOGDISABLED** içinde **değişken adı** kutusu.  
  
5.  İçinde **değişken değeri** kutusuna **1**.  
  
6.  **Tamam**'ı tıklatın.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)   
 [Office çözümleri dağıtımı sorunlarını giderme](../vsto/troubleshooting-office-solution-deployment.md)  
  
  