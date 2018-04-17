---
title: 'Nasıl yapılır: Office çözümü için yapılandırma bilgilerini ayarlama | Microsoft Docs'
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
ms.openlocfilehash: 9659872fa6cb4e294d1757412862c10e42cde2e9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
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
  
  