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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 6f604fa40a9816d5e46593bc50fcb91f82d13325
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2018
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
  
  