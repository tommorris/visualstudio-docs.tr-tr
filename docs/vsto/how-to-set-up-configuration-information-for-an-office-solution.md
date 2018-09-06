---
title: 'Nasıl yapılır: bir Office çözümü için yapılandırma bilgilerini ayarlama'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], configuration files
- configuration files [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 87f50856439158d6d931b519fb35e98970ef7d58
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35676710"
---
# <a name="how-to-set-up-configuration-information-for-an-office-solution"></a>Nasıl yapılır: bir Office çözümü için yapılandırma bilgilerini ayarlama
  Office çözümünüzü özgü ayarları yapılandırmak için yapılandırma dosyalarını kullanabilirsiniz. Derleme bağlama ilkesi, uzaktan iletişim nesneleri, hata ayıklama ve izleme ayarları gibi ayarları belirtebilirsiniz.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-configuration-file-to-your-office-project"></a>Office projenizin bir yapılandırma dosyası eklemek için  
  
1.  Üzerinde **proje** menüsünü tıklatın **Yeni Öğe Ekle**.  
  
2.  İçinde **kategorileri** bölmesinde tıklayın **genel**.  
  
3.  İçinde **şablonları** bölmesinde **uygulama yapılandırma dosyası**.  
  
4.  İçinde **adı** derleme artı uzantısı olarak aynı adı yazın *.config*. Örneğin, bir Excel proje derlemesi için bir yapılandırma dosyası adlı *ExcelWorkbook1.dll* sayfadayken *ExcelWorkbook1.dll.config*.  
  
5.  **Ekle**'yi tıklatın.  
  
6.  Uygulama yapılandırma dosyası şeması göre yapılandırma dosyası oluşturun. Daha fazla bilgi için [.NET Framework yapılandırma dosyası şeması](/dotnet/framework/configure-apps/file-schema/index).  
  
 Yapılandırma dosyalarını kullanarak Office projeleriyle için özel durumlar vardır.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [.NET Framework yapılandırma dosyası şeması](/dotnet/framework/configure-apps/file-schema/index)   
 [Office çözümleri oluşturma ve tasarlama](../vsto/designing-and-creating-office-solutions.md)   
 [Office çözümünü dağıtma](../vsto/deploying-an-office-solution.md)  
  
  