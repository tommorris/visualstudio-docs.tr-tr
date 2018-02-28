---
title: "Visual Studio'da projeye bir app.config dosyası ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: d77e86599670ef04b813381da84a03ab1f238af3
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Nasıl yapılır: C# Projesine Uygulama Yapılandırma Dosyası Ekleme

Bir C# projesine uygulama yapılandırma dosyasından (app.config dosyası) ekleyerek, ortak dil çalışma zamanı'nın bulur ve derleme dosyalarını yükler nasıl özelleştirebilirsiniz. Uygulama yapılandırma dosyaları hakkında daha fazla bilgi için bkz: [nasıl çalışma zamanı derlemeleri (.NET Framework) bulur](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

> [!NOTE]
> UWP uygulamaları bir app.config dosyası hiçbirini içeremez.

Projenizi yapılandırdığınızda, geliştirme ortamı, app.config dosyası otomatik olarak kopyalar, dosya adı yürütülebilir dosyanın eşleşecek şekilde kopyasının değiştirir ve kopyaya taşır **bin** dizin.

## <a name="to-add-an-application-configuration-file-to-a-c-project"></a>Bir C# projesine uygulama yapılandırma dosyası eklemek için

1. Menü çubuğunda seçin **proje** > **Yeni Öğe Ekle**.

     **Yeni Öğe Ekle** iletişim kutusu görüntülenir.

1. Genişletme **yüklü** > **Visual C# öğeleri**ve ardından **uygulama yapılandırma dosyası** şablonu.

3. buna **adı** metin kutusuna bir ad girin ve ardından **Ekle** düğmesi.

     A file named app.config is added to your project.

## <a name="see-also"></a>Ayrıca bkz.

[Uygulama Ayarlarını Yönetme](../ide/managing-application-settings-dotnet.md)  
[Yapılandırma dosyası şeması (.NET Framework)](/dotnet/framework/configure-apps/file-schema/index)  
[Uygulamaları (.NET Framework) yapılandırma](/dotnet/framework/configure-apps/index)