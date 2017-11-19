---
title: "Nasıl yapılır: bir C# projesine uygulama yapılandırma dosyası ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords: app.config files, adding to C# projects
ms.assetid: 9caf6bb0-c2fc-4ab6-ba69-bed3b880fbf8
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 097e7a2eac78fe85b2a3ab62d5cdf1fd18908d56
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Nasıl yapılır: C# Projesine Uygulama Yapılandırma Dosyası Ekleme
Bir C# projesine uygulama yapılandırma dosyasından (app.config dosyası) ekleyerek, ortak dil çalışma zamanı'nın bulur ve derleme dosyalarını yükler nasıl özelleştirebilirsiniz. Uygulama yapılandırma dosyaları hakkında daha fazla bilgi için bkz: [nasıl çalışma zamanı bulur derlemeleri](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).  
  
> [!NOTE]
>  UWP uygulamaları bir app.config şablonu hiçbirini içeremez.
  
 Projenizi yapılandırdığınızda, geliştirme ortamı, app.config dosyası otomatik olarak kopyalar, dosya adı yürütülebilir dosyanın eşleşecek şekilde kopyasının değiştirir ve ardından kopya bin dizinine taşır.  
  
### <a name="to-add-an-application-configuration-file-to-your-c-project"></a>C# projenize bir uygulama yapılandırma dosyası eklemek için  
  
1.  Menü çubuğunda seçin **proje**, **Yeni Öğe Ekle**.  
  
     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.  
  
2.  Genişletme **yüklü**, genişletin **Visual C# öğeleri**ve ardından **uygulama yapılandırma dosyası** şablonu.  
  
3.  İçinde **adı** metin kutusuna bir ad girin ve ardından **Ekle** düğmesi.  
  
     App.config adlı bir dosyayı projenize eklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulama ayarları (.NET) yönetme](../ide/managing-application-settings-dotnet.md)   
 [Yapılandırma dosyası şeması](/dotnet/framework/configure-apps/file-schema/index)   
 [Uygulamaları yapılandırma](/dotnet/framework/configure-apps/index)   
 [Nasıl yapılır: .NET Framework sürümünü hedeflemek için bir uygulamayı yapılandırma](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717)   
 [Visual Studio geliştirme ortamı C# için kullanma](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)