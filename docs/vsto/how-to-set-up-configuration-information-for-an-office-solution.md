---
title: "Nasıl yapılır: Office çözümü için yapılandırma bilgilerini ayarlama | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
ms.assetid: f123838f-957a-4cf5-acc0-0cc0f4c2aea2
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: d7b8c8c9ca6dd964a58aa65b901d9219732179f3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>Nasıl Yapılır: Office Çözümü için Yapılandırma Bilgilerini Kurma
  Yapılandırma dosyaları, Office çözümleri için belirli ayarları yapılandırmak için kullanabilirsiniz. Derleme bağlama ilkesi, uzaktan iletişim nesneleri, hata ayıklama ve izleme ayarları gibi ayarları belirtebilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>Bir yapılandırma dosyası Office projenize eklemek için  
  
1.  Üzerinde **proje** menüsünde tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **kategorileri** bölmesinde tıklatın **genel**.  
  
3.  İçinde **şablonları** bölmesinde, **uygulama yapılandırma dosyası**.  
  
4.  İçinde **adı** derleme artı uzantı .config olarak aynı adı yazın. Örneğin, ExcelWorkbook1.dll adlı Excel projesi derleme için bir yapılandırma dosyası ExcelWorkbook1.dll.config adlı.  
  
5.  **Ekle**'yi tıklatın.  
  
6.  Uygulama yapılandırma dosyası şemasına göre yapılandırma dosyanızı oluşturun. Daha fazla bilgi için bkz: [.NET Framework için yapılandırma dosyası şeması](/dotnet/framework/configure-apps/file-schema/index).  
  
 Office projeleri ile yapılandırma dosyalarını kullanmak için özel durumlar vardır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [.NET Framework için yapılandırma dosyası şeması](/dotnet/framework/configure-apps/file-schema/index)   
 [Tasarlama ve Office çözümleri oluşturma](../vsto/designing-and-creating-office-solutions.md)   
 [Office Çözümünü Dağıtma](../vsto/deploying-an-office-solution.md)  
  
  