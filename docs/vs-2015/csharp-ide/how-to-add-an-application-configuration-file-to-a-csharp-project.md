---
title: 'Nasıl yapılır: bir C# projesine uygulama yapılandırma dosyası ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
ms.assetid: 9caf6bb0-c2fc-4ab6-ba69-bed3b880fbf8
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 29386381679c02d3f4c7772e79f1da4a64705e3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686464"
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Nasıl yapılır: C# Projesine Uygulama Yapılandırma Dosyası Ekleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bir C# projesine uygulama yapılandırma dosyası (app.config dosyası) ekleyerek, ortak dil çalışma zamanının nasıl bulur ve derleme dosyalarını yükler özelleştirebilirsiniz. Uygulama yapılandırma dosyaları hakkında daha fazla bilgi için bkz. [çalışma zamanı derlemeleri nasıl konumlandırır](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34).  
  
> [!NOTE]
>  Windows Store desteklemiyor <xref:System.Configuration>. Sonuç olarak, Store uygulamaları, bir app.config şablonunu içermez.  
  
 Projenizi yapılandırdığınızda, geliştirme ortamı, app.config dosyasına otomatik olarak kopyalar, yürütülebilir dosyanın eşleştirilecek kopyalama dosya adını değiştirir ve ardından kopya ait bin dizinine taşır.  
  
### <a name="to-add-an-application-configuration-file-to-your-c-project"></a>C# projenize bir uygulama yapılandırma dosyası eklemek için  
  
1.  Menü çubuğunda, **proje**, **Yeni Öğe Ekle**.  
  
     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.  
  
2.  Genişletin **yüklü**, genişletme **Visual C# öğeleri**ve ardından **uygulama yapılandırma dosyası** şablonu.  
  
3.  İçinde **adı** metin kutusuna bir ad girin ve ardından **Ekle** düğmesi.  
  
     App.config adlı bir dosyayı projenize eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama ayarları (.NET) yönetme](../ide/managing-application-settings-dotnet.md)   
 [Yapılandırma dosyası şeması](http://msdn.microsoft.com/library/69003d39-dc8a-460c-a6be-e6d93e690b38)   
 [Uygulamaları yapılandırma](http://msdn.microsoft.com/library/86bd26d3-737e-4484-9782-19b17f34cd1f)   
 [Nasıl yapılır: bir uygulamayı .NET Framework sürümünü hedefleyecek şekilde yapılandırma](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717)   
 [C# için Visual Studio Geliştirme Ortamını Kullanma](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)